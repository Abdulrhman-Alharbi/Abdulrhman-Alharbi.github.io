---
layout: page
title: Cheat Sheet
---

# Cheat Sheet

## nmap

<details>
<summary>Scanning Options</summary>

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

</details>

<details>
<summary>Output Options</summary>

| Code | Description |
| :------ |:--- |
| `-oA filename` | Saves results in all formats (normal, grepable, XML). |
| `-oN filename` | Normal format. |
| `-oG filename` | Grepable format. |
| `-oX filename` | XML format. |

</details>

<details>
<summary>Performance Options</summary>

| Code | Description |
| :------ |:--- |
| `--max-retries <num>` | Sets retries for port scans. |
| `--stats-every=5s` | Displays status every 5 seconds. |
| `-v/-vv` | Verbose output. |
| `--initial-rtt-timeout 50ms` | Initial RTT timeout. |
| `--max-rtt-timeout 100ms` | Maximum RTT timeout. |
| `--min-rate 300` | Minimum packet rate. |
| `-T <0-5>` | Timing template. |

</details>

## Infrastructure-based Enumeration

<details>
<summary>Commands</summary>

| Command | Description |
| :------ |:--- |
| `curl -s https://crt.sh/?q=<target-domain>&output=json | jq .` | Certificate transparency. |
| `for i in $(cat ip-addresses.txt); do shodan host $i; done` | Scan each IP address in a list using Shodan. |

</details>

## Host-based Enumeration

<details>
<summary>FTP</summary>

| Command | Description |
| :------ |:--- |
| `ftp <FQDN/IP>` | Interact with the FTP service on the target. |
| `nc -nv <FQDN/IP> 21` | Interact with the FTP service on the target. |
| `telnet <FQDN/IP> 21` | Interact with the FTP service on the target. |
| `openssl s_client -connect <FQDN/IP>:21 -starttls ftp` | Interact with the FTP service on the target using an encrypted connection. |
| `wget -m --no-passive ftp://anonymous:anonymous@<target>` | Download all available files on the target FTP server. |

</details>

<details>
<summary>SMB</summary>

| Command | Description |
| :------ |:--- |
| `smbclient -N -L //<FQDN/IP>` | Null session authentication on SMB. |
| `smbclient //<FQDN/IP>/<share>` | Connect to a specific SMB share. |
| `rpcclient -U "" <FQDN/IP>` | Interaction with the target using RPC. |
| `samrdump.py <FQDN/IP>` | Username enumeration using Impacket scripts. |
| `smbmap -H <FQDN/IP>` | Enumerating SMB shares. |
| `crackmapexec smb <FQDN/IP> --shares -u '' -p ''` | Enumerating SMB shares using null session authentication. |
| `enum4linux-ng.py <FQDN/IP> -A` | SMB enumeration using enum4linux. |

</details>

<details>
<summary>NFS</summary>

| Command | Description |
| :------ |:--- |
| `showmount -e <FQDN/IP>` | Show available NFS shares. |
| `mount -t nfs <FQDN/IP>:/<share> ./target-NFS/ -o nolock` | Mount the specific NFS share. |
| `umount ./target-NFS` | Unmount the specific NFS share. |

</details>

<details>
<summary>DNS</summary>

| Command | Description |
| :------ |:--- |
| `dig ns <domain.tld> @<nameserver>` | NS request to the specific nameserver. |
| `dig any <domain.tld> @<nameserver>` | ANY request to the specific nameserver. |
| `dig axfr <domain.tld> @<nameserver>` | AXFR request to the specific nameserver. |
| `dnsenum --dnsserver <nameserver> --enum -p 0 -s 0 -o found_subdomains.txt -f ~/subdomains.list <domain.tld>` | Subdomain brute forcing. |

</details>

<details>
<summary>SMTP</summary>

| Command | Description |
| :------ |:--- |
| `telnet <FQDN/IP> 25` | Interact with the SMTP service on the target. |

</details>

<details>
<summary>IMAP/POP3</summary>

| Command | Description |
| :------ |:--- |
| `curl -k 'imaps://<FQDN/IP>' --user <user>:<password>` | Log in to the IMAPS service using cURL. |
| `openssl s_client -connect <FQDN/IP>:imaps` | Connect to the IMAPS service. |
| `openssl s_client -connect <FQDN/IP>:pop3s` | Connect to the POP3s service. |

</details>

<details>
<summary>SNMP</summary>

| Command | Description |
| :------ |:--- |
| `snmpwalk -v2c -c <community string> <FQDN/IP>` | Query OIDs using snmpwalk. |
| `onesixtyone -c community-strings.list <FQDN/IP>` | Brute force community strings of the SNMP service. |
| `braa <community string>@<FQDN/IP>:.1.*` | Brute force SNMP service OIDs. |

</details>

<details>
<summary>MySQL</summary>

| Command | Description |
| :------ |:--- |
| `mysql -u <user> -p<password> -h <FQDN/IP>` | Login to the MySQL server. |

</details>

<details>
<summary>MSSQL</summary>

| Command | Description |
| :------ |:--- |
| `mssqlclient.py <user>@<FQDN/IP> -windows-auth` | Log in to the MSSQL server using Windows authentication. |

</details>

<details>
<summary>IPMI</summary>

| Command | Description |
| :------ |:--- |
| `msf6 auxiliary(scanner/ipmi/ipmi_version)` | IPMI version detection. |
| `msf6 auxiliary(scanner/ipmi/ipmi_dumphashes)` | Dump IPMI hashes. |

</details>

<details>
<summary>Linux Remote Management</summary>

| Command | Description |
| :------ |:--- |
| `ssh-audit.py <FQDN/IP>` | Remote security audit against the target SSH service. |
| `ssh <user>@<FQDN/IP>` | Log in to the SSH server using the SSH client. |
| `ssh -i private.key <user>@<FQDN/IP>` | Log in to the SSH server using a private key. |
| `ssh <user>@<FQDN/IP> -o PreferredAuthentications=password` | Enforce password-based authentication. |

</details>

<details>
<summary>Windows Remote Management</summary>

| Command
