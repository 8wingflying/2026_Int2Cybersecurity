# Regular Reports and Grades
## Network analysis and Network Forensics
- Network protocols
  - OSI Model
  - TCP/IP
- Network Tools: Wireshark Network Miner
- protocol analysis ==> Format
  - DNS
    - DNS Format
  - TCP three-way handshking (HTTP(S)--> TCP --> IP)
    - TCP　Format
    - TCP Syn flood attack 
  - UDP(DNS--> UDP --> IP)
  - IP
    - IP Format
    - TTL 
  - icmp ==> ping
    - ICMP Format 
- Network Forensics(Traffic with malware ==> FIND out the malware)

-----------------------------------------------------------------------------------
 
## Network Forensics
- see 20260603_NetworkForensics
- Analysis:
  - `1`.Wireshark analysis
  - `2`.Network Miner
  - `3`.online pcap analysis: https://apackets.com/
- Questions:
  - Q1. What’s the private IP of the infected host?
  - Q2. What’s the malware binary that the macro document is trying to retrieve?
  - Q3. From what domain HTTP requests with GET /images/ are coming from? (4 points)
  - Q4. The SOC Team found Dridex, a follow-up malware from Ursnif infection, to be the culprit. The customer who sent her the macro file is compromised. What’s the full URI ending in .rar where Ursnif retrieves the follow-up malware from? (4 points)
  - Q5. What is the Dridex post-infection traffic IP addresses beginning with 185.?
- References:
  - https://medium.com/@luke.ed.holmes/btlo-network-analysis-malware-compromise-challenge-488764e42c28
  - https://github.com/olustella/Dridex-Forensic-Analysis
