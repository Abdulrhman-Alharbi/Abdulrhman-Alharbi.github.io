---
layout: page
title: Cheat Sheet
---

# Cheat Sheet

<div>
  <button class="collapsible">Scanning Options</button>
  <div class="content">
    <h3>Nmap Scanning Options</h3>
    <table>
      <thead>
        <tr>
          <th>Nmap Option</th>
          <th>Description</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>`10.10.10.0/24`</td>
          <td>Target network range.</td>
        </tr>
        <tr>
          <td>`-sn`</td>
          <td>Disables port scanning.</td>
        </tr>
        <tr>
          <td>`-Pn`</td>
          <td>Disables ICMP Echo Requests.</td>
        </tr>
        <tr>
          <td>`-n`</td>
          <td>Disables DNS Resolution.</td>
        </tr>
        <tr>
          <td>`-PE`</td>
          <td>Performs a ping scan using ICMP Echo Requests.</td>
        </tr>
        <tr>
          <td>`--packet-trace`</td>
          <td>Shows all packets sent and received.</td>
        </tr>
        <tr>
          <td>`--reason`</td>
          <td>Displays the reason for a specific result.</td>
        </tr>
        <tr>
          <td>`--disable-arp-ping`</td>
          <td>Disables ARP Ping Requests.</td>
        </tr>
        <tr>
          <td>`--top-ports=<num>`</td>
          <td>Scans the specified top ports.</td>
        </tr>
        <tr>
          <td>`-p-`</td>
          <td>Scan all ports.</td>
        </tr>
        <tr>
          <td>`-p22-110`</td>
          <td>Scan all ports between 22 and 110.</td>
        </tr>
        <tr>
          <td>`-p22,25`</td>
          <td>Scans only ports 22 and 25.</td>
        </tr>
        <tr>
          <td>`-F`</td>
          <td>Scans top 100 ports.</td>
        </tr>
        <tr>
          <td>`-sS`</td>
          <td>Performs a TCP SYN-Scan.</td>
        </tr>
        <tr>
          <td>`-sA`</td>
          <td>Performs a TCP ACK-Scan.</td>
        </tr>
        <tr>
          <td>`-sU`</td>
          <td>Performs a UDP Scan.</td>
        </tr>
        <tr>
          <td>`-sV`</td>
          <td>Scans the discovered services for their versions.</td>
        </tr>
        <tr>
          <td>`-sC`</td>
          <td>Performs a Script Scan with default scripts.</td>
        </tr>
        <tr>
          <td>`--script <script>`</td>
          <td>Performs a Script Scan using specified scripts.</td>
        </tr>
        <tr>
          <td>`-O`</td>
          <td>Performs OS Detection.</td>
        </tr>
        <tr>
          <td>`-A`</td>
          <td>Performs OS Detection, Service Detection, and traceroute.</td>
        </tr>
        <tr>
          <td>`-D RND:5`</td>
          <td>Sets the number of random Decoys to use.</td>
        </tr>
        <tr>
          <td>`-e`</td>
          <td>Specifies the network interface for the scan.</td>
        </tr>
        <tr>
          <td>`-S 10.10.10.200`</td>
          <td>Specifies the source IP address for the scan.</td>
        </tr>
        <tr>
          <td>`-g`</td>
          <td>Specifies the source port for the scan.</td>
        </tr>
        <tr>
          <td>`--dns-server <ns>`</td>
          <td>Uses the specified DNS server for resolution.</td>
        </tr>
      </tbody>
    </table>
  </div>
</div>

<div>
  <button class="collapsible">Output Options</button>
  <div class="content">
    <h3>Nmap Output Options</h3>
    <table>
      <thead>
        <tr>
          <th>Nmap Option</th>
          <th>Description</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>`-oA filename`</td>
          <td>Stores results in all formats (normal, grepable, XML).</td>
        </tr>
        <tr>
          <td>`-oN filename`</td>
          <td>Stores results in normal format.</td>
        </tr>
        <tr>
          <td>`-oG filename`</td>
          <td>Stores results in grepable format.</td>
        </tr>
        <tr>
          <td>`-oX filename`</td>
          <td>Stores results in XML format.</td>
        </tr>
      </tbody>
    </table>
  </div>
</div>

<div>
  <button class="collapsible">Performance Options</button>
  <div class="content">
    <h3>Nmap Performance Options</h3>
    <table>
      <thead>
        <tr>
          <th>Nmap Option</th>
          <th>Description</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>`--max-retries <num>`</td>
          <td>Sets the number of retries for port scans.</td>
        </tr>
        <tr>
          <td>`--stats-every=5s`</td>
          <td>Displays scan status every 5 seconds.</td>
        </tr>
        <tr>
          <td>`-v/-vv`</td>
          <td>Displays verbose output.</td>
        </tr>
        <tr>
          <td>`--initial-rtt-timeout 50ms`</td>
          <td>Sets the initial RTT timeout.</td>
        </tr>
        <tr>
          <td>`--max-rtt-timeout 100ms`</td>
          <td>Sets the maximum RTT timeout.</td>
        </tr>
        <tr>
          <td>`--min-rate 300`</td>
          <td>Sets the number of packets sent simultaneously.</td>
        </tr>
        <tr>
          <td>`-T <0-5>`</td>
          <td>Specifies the timing template.</td>
        </tr>
      </tbody>
    </table>
  </div>
</div>

<script>
  document.querySelectorAll('.collapsible').forEach(button => {
    button.addEventListener('click', () => {
      const content = button.nextElementSibling;
      content.style.display = content.style.display === 'block' ? 'none' : 'block';
    });
  });
</script>
