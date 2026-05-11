# Linux_Privilege Escalation
- https://medium.com/@samare243/metasploitable3-walkthrough-b3cf7195c497
- https://xz.aliyun.com/news/11981
```
root@kali:~# ssh vagrant@10.0.3.5
The authenticity of host '10.0.3.5 (10.0.3.5)' can't be established.
ECDSA key fingerprint is SHA256:lFnuAD9nzxzUnxpgpUYLMYxMQWq5lh5XIePPgiVl5Vw.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added '10.0.3.5' (ECDSA) to the list of known hosts.
vagrant@10.0.3.5's password: 
Welcome to Ubuntu 14.04.6 LTS (GNU/Linux 3.13.0-170-generic x86_64)

 * Documentation:  https://help.ubuntu.com/
Last login: Mon May 11 05:39:53 2026
vagrant@metasploitable3-ub1404:~$ whoami
vagrant


vagrant@metasploitable3-ub1404:~$ sudo -l
Matching Defaults entries for vagrant on metasploitable3-ub1404:
    env_reset, mail_badpass,
    secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User vagrant may run the following commands on metasploitable3-ub1404:
    (ALL : ALL) ALL
    (ALL : ALL) NOPASSWD: ALL
vagrant@metasploitable3-ub1404:~$ sudo su
root@metasploitable3-ub1404:/home/vagrant# whoami
root
root@metasploitable3-ub1404:/home/vagrant# 

```

-----------------------------------------

# ATTACK

### 1. 建立 SSH 連線
- 指令： ssh vagrant@10.0.3.5
- 動作： 攻擊者（或使用者）從 Kali Linux 透過 SSH 登入一台 IP 為 10.0.3.5 的主機。
- 目標環境： 根據歡迎訊息，這是一台運作 Ubuntu 14.04.6 LTS 的虛擬機，主機名為 metasploitable3-ub1404（這是著名的易受攻擊測試平台 Metasploitable 3）。

### 2. 確認目前身份
- 指令： whoami
- 結果： vagrant
- 說明： 此時是以低權限的普通使用者 vagrant 登入。

### 3. 檢查 Sudo 權限 (權限列舉)
- 指令： sudo -l
- 關鍵發現： 系統顯示 (ALL : ALL) NOPASSWD: ALL。
- 安全性弱點： 這表示 vagrant 使用者在執行任何指令時，都不需要輸入密碼即可獲得 Root 權限。這是在真實環境中非常嚴重的配置錯誤（Misconfiguration）。

### 4. 執行權限提升 (Privilege Escalation)
- 指令： sudo su
- 結果： 提示字元從 $ 變成了 #，且路徑切換到了 /home/vagrant。
- 說明： 利用剛才發現的 NOPASSWD 漏洞，直接切換成超級使用者（Root）。

### 5. 最終確認
- 指令： whoami
- 結果： root

### 總結： 攻擊者已成功完全控制該系統。
- 核心概念： 這是一個典型的「配置不當導致的權限提升」範例。
```
## 如何修補此漏洞? 權限提升 (Privilege Escalation) 漏洞
- 修補的核心在於重新設定 /etc/sudoers 檔案，遵循「最小權限原則 (Principle of Least Privilege)」。

### 具體的修補步驟與建議：

### 1. 修改 sudoers 設定
- vagrant 使用者之所以能直接變身為 root，是因為設定了 NOPASSWD: ALL。
- 動作： 使用 sudo visudo 指令編輯設定檔（切記不要直接用一般編輯器改，visudo 會在儲存前檢查語法錯誤）。
- 修補方式：
  - 移除 NOPASSWD： 將 (ALL : ALL) NOPASSWD: ALL 改為 (ALL : ALL) ALL。這樣使用者在執行 sudo 指令時，系統會要求輸入密碼。
  - 限制指令範圍： 除非必要，否則不應給予 ALL 權限。應針對特定任務開放權限，例如：vagrant ALL=(ALL) /usr/bin/apt-get, /usr/bin/service
  - 移除不必要的 Sudo 權限： 如果該帳號不需要管理權限，直接將其從 sudo 或 admin 群組中移除。

### 2. 強化帳密管理
- 即便要求輸入密碼，如果密碼太簡單（例如 Metasploitable 常見的 vagrant/vagrant），攻擊者仍可輕易透過暴力破解或已知預設密碼取得權限。
- 修補方式：
  - 變更預設密碼：使用 passwd vagrant 更改為強密碼。
  - 停用密碼登入：改用 SSH Key (公私鑰) 對進行驗證，並在 /etc/ssh/sshd_config 中設定 PasswordAuthentication no。

### 3. 系統更新與弱點掃描
- 截圖顯示該系統為 Ubuntu 14.04，這是一個已經停止維護 (EOL) 的老舊版本，存在大量已知的內核漏洞（如 Dirty COW 等）。
- 修補方式：
  - 升級系統： 盡可能升級至 LTS 現行版本（如 Ubuntu 22.04 或 24.04）。
  - 核心修補： 如果無法升級系統，應至少確保安裝了所有安全性更新。

### 4. 稽核與監控
- 為了防止未來的攻擊，應建立監控機制：
  - 檢視日誌： 定期檢查 /var/log/auth.log（Ubuntu）或 /var/log/secure（CentOS），查看是否有異常的 sudo 執行記錄。
  - 權限審核： 定期執行 find / -perm -4000 檢查系統中是否存在異常的 SUID 程式，這也是另一種常見的提權路徑。


## `/etc/sudoers`
```sh
root@kali:~# cat /etc/sudoers
#
# This file MUST be edited with the 'visudo' command as root.
#
# Please consider adding local content in /etc/sudoers.d/ instead of
# directly modifying this file.
#
# See the man page for details on how to write a sudoers file.
#
Defaults	env_reset
Defaults	mail_badpass
Defaults	secure_path="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"

# Host alias specification

# User alias specification

# Cmnd alias specification

# User privilege specification
root	ALL=(ALL:ALL) ALL

# Allow members of group sudo to execute any command
%sudo	ALL=(ALL:ALL) ALL

# See sudoers(5) for more information on "#include" directives:

#includedir /etc/sudoers.d

```
