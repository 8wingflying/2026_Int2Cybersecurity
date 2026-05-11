#
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
