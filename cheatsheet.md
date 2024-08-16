### Scanning Options

| Code | Description |
| :------ |:--- |
| `10.10.10.0/24` | Target network range. |
| `-sn` | Disables port scanning (host discovery only). |
| `-Pn` | Disables ICMP Echo Requests (assumes all hosts are up). |
| `-n` | Disables DNS Resolution. |
| `-PE` | Uses ICMP Echo Requests for ping scanning. |
| `--disable-arp-ping` | Disables ARP Ping Requests. |
| `--packet-trace` | Shows all packets sent and received. |
| `--reason` | Displays reasons for scan results. |
| `--top-ports=<num>` | Scans the specified top ports. |
| `-p-` | Scans all ports. |
| `-p22-110` | Scans ports between 22 and 110. |
| `-p22,25` | Scans only ports 22 and 25. |
| `-F` | Scans top 100 ports. |
| `-sS` | TCP SYN Scan. |
| `-sA` | TCP ACK Scan. |
| `-sU` | UDP Scan. |
| `-sV` | Service version detection. |
| `-sC` | Script Scan with default scripts. |
| `--script <script>` | Script Scan with specified scripts. |
| `-O` | OS Detection. |
| `-A` | OS Detection, Service Detection, and traceroute. |
| `-D RND:5` | Uses 5 random Decoys. |
| `-e` | Specifies network interface. |
| `-S 10.10.10.200` | Specifies source IP address. |
| `-g` | Specifies source port. |
| `--dns-server <ns>` | Uses specified DNS server for resolution. |

### Output Options

| Code | Description |
| :------ |:--- |
| `-oA filename` | Saves results in all formats (normal, grepable, XML). |
| `-oN filename` | Normal format. |
| `-oG filename` | Grepable format. |
| `-oX filename` | XML format. |

### Performance Options

| Code | Description |
| :------ |:--- |
| `--max-retries <num>` | Sets retries for port scans. |
| `--stats-every=5s` | Displays status every 5 seconds. |
| `-v/-vv` | Verbose output. |
| `--initial-rtt-timeout 50ms` | Initial RTT timeout. |
| `--max-rtt-timeout 100ms` | Maximum RTT timeout. |
| `--min-rate 300` | Minimum packet rate. |
| `-T <0-5>` | Timing template. |
