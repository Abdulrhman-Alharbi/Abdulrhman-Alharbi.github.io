---
layout: page
title: Cheat Sheet
---

# Cheat Sheet

<details>
<summary>Scanning Options</summary>

### Nmap Scanning Options

| Nmap Option | Description |
| :----------- | :---------- |
| `10.10.10.0/24` | Target network range. |
| `-sn` | Disables port scanning. |
| `-Pn` | Disables ICMP Echo Requests. |
| `-n` | Disables DNS Resolution. |
| `-PE` | Performs a ping scan using ICMP Echo Requests. |
| `--packet-trace` | Shows all packets sent and received. |
| `--reason` | Displays the reason for a specific result. |
| `--disable-arp-ping` | Disables ARP Ping Requests. |
| `--top-ports=<num>` | Scans the specified top ports. |
| `-p-` | Scan all ports. |
| `-p22-110` | Scan all ports between 22 and 110. |
| `-p22,25` | Scans only the specified ports 22 and 25. |
| `-F` | Scans top 100 ports. |
| `-sS` | Performs a TCP SYN-Scan. |
| `-sA` | Performs a TCP ACK-Scan. |
| `-sU` | Performs a UDP Scan. |
| `-sV` | Scans the discovered services for their versions. |
| `-sC` | Performs a Script Scan with default scripts. |
| `--script <script>` | Performs a Script Scan using specified scripts. |
| `-O` | Performs OS Detection. |
| `-A` | Performs OS Detection, Service Detection, and traceroute. |
| `-D RND:5` | Sets the number of random Decoys to use. |
| `-e` | Specifies the network interface for the scan. |
| `-S 10.10.10.200` | Specifies the source IP address for the scan. |
| `-g` | Specifies the source port for the scan. |
| `--dns-server <ns>` | Uses the specified DNS server for resolution. |

</details>

<details>
<summary>Output Options</summary>

### Nmap Output Options

| Nmap Option | Description |
| :----------- | :---------- |
| `-oA filename` | Stores the results in all formats (normal, grepable, XML). |
| `-oN filename` | Stores results in normal format. |
| `-oG filename` | Stores results in grepable format. |
| `-oX filename` | Stores results in XML format. |

</details>

<details>
<summary>Performance Options</summary>

### Nmap Performance Options

| Nmap Option | Description |
| :----------- | :---------- |
| `--max-retries <num>` | Sets the number of retries for port scans. |
| `--stats-every=5s` | Displays scan status every 5 seconds. |
| `-v/-vv` | Displays verbose output. |
| `--initial-rtt-timeout 50ms` | Sets the initial RTT timeout. |
| `--max-rtt-timeout 100ms` | Sets the maximum RTT timeout. |
| `--min-rate 300` | Sets the number of packets sent simultaneously. |
| `-T <0-5>` | Specifies the timing template. |

</details>
