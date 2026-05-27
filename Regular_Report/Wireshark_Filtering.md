
# Wireshark 常見過濾指令速查表 (Common Filtering Commands Cheat Sheet)

本文件整理了常用的 Wireshark 封包過濾語法（Filter Syntax），便於在網路分析、流量監控與資安鑑識中快速檢索與使用。

---

## 1. IP 位址過濾 (IP Address Filtering)

| 功能描述 (Usage) | 過濾語法 (Filter Syntax) | 說明 |
| :--- | :--- | :--- |
| **Wireshark Filter by IP** | `ip.addr == 10.10.50.1` | 篩選來源或目的為該 IP 的所有封包 |
| **Filter by Destination IP** | `ip.dest == 10.10.50.1` | 僅篩選目的（Destination）為該 IP 的封包 |
| **Filter by Source IP** | `ip.src == 10.10.50.1` | 僅篩選來源（Source）為該 IP 的封包 |
| **Filter by IP range** | `ip.addr >= 10.10.50.1 and ip.addr <= 10.10.50.100` | 篩選落在指定 IP 範圍內的所有封包 |
| **Filter by Multiple Ips** | `ip.addr == 10.10.50.1 and ip.addr == 10.10.50.100` | 同時滿足多個 IP 條件（註：多用於特定複合邏輯） |
| **Filter out IP address** | `!(ip.addr == 10.10.50.1)` | 排除特定 IP 位址的封包 |
| **Filter subnet** | `ip.addr == 10.10.50.1/24` | 篩選特定 CIDR 網段（C Class）的所有封包 |

---

## 2. 埠口與傳輸協定過濾 (Port & Protocol Filtering)

| 功能描述 (Usage) | 過濾語法 (Filter Syntax) | 說明 |
| :--- | :--- | :--- |
| **Filter by port** | `tcp.port == 25` | 篩選 TCP 埠口為 25 (SMTP) 的封包 |
| **Filter by destination port** | `tcp.dstport == 23` | 篩選目的 TCP 埠口為 23 (Telnet) 的封包 |
| **Filter by ip address and port** | `ip.addr == 10.10.50.1 and Tcp.port == 25` | 複合條件：特定 IP 且 TCP 埠口為 25 |

---

## 3. TCP 旗標過濾 (TCP Flags Filtering)

| 功能描述 (Usage) | 過濾語法 (Filter Syntax) | 說明 |
| :--- | :--- | :--- |
| **Filter SYN flag** | `tcp.flags.syn == 1` | 篩選含有 SYN 旗標的連線請求封包 |
| **Filter SYN-ACK check** | `tcp.flags.syn == 1 and tcp.flags.ack == 0` | 篩選純 SYN 請求（排除確認連線的 SYN-ACK） |
| **RST flag filter** | `tcp.flags.reset == 1` | 篩選含有 RST 旗標的連線重置/中斷封包 |

---

## 4. 應用層與主機名稱過濾 (Application & Hostname Filtering)

| 功能描述 (Usage) | 過濾語法 (Filter Syntax) | 說明 |
| :--- | :--- | :--- |
| **Filter by URL** | `http.host == "host name"` | 篩選指定 HTTP 網域/主機名的流量 |
| **Host name filter** | `ip.host == hostname` | 依據主機名稱進行網路層篩選 |

---

## 5. 資料連結層與無線網路過濾 (Layer 2 & Wireless Filtering)

| 功能描述 (Usage) | 過濾語法 (Filter Syntax) | 說明 |
| :--- | :--- | :--- |
| **Wireshark Beacon Filter** | `wlan.fc.type_subtype == 0x08` | 篩選 802.11 Wi-Fi 的 Beacon 廣播訊框 |
| **Wireshark broadcast filter** | `eth.dst == ff:ff:ff:ff:ff:ff` | 篩選乙太網路廣播封包 |
| **Wireshark multicast filter** | `(eth.dst[0] & 1)` | 使用位元運算篩選乙太網路多播 (Multicast) 封包 |
| **MAC address filter** | `eth.addr == 00:70:f4:23:18:c4` | 篩選特定網卡 MAC 位址的流量 |

---

## 6. 時間戳記過濾 (Timestamp Filtering)

| 功能描述 (Usage) | 過濾語法 (Filter Syntax) | 說明 |
| :--- | :--- | :--- |
| **Filter by time stamp** | `frame.time >= "June 02, 2019 18:04:00"` | 篩選在指定時間點之後所捕獲的封包 |

---
*備註：以上語法保留了部分原始圖片中的特定大小寫特徵（如 `Tcp.port`、`ip.dest`、Multiple `Ips`），於實際新版 Wireshark 中使用時，通常全面採用小寫標準語法（如 `tcp.port`、`ip.dst`）。*
wireshark_common_filters.md
目前顯示的是「wireshark_common_filters.md」。
