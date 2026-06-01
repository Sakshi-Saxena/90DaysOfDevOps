| OSI Layer           | What it Handles       | Common Commands                   | Typical Issues                  | Debug Commands                          |             |
| ------------------- | --------------------- | --------------------------------- | ------------------------------- | --------------------------------------- | ----------- |
| **L7 Application**  | HTTP, DNS, APIs       | `curl`, `dig`, `nslookup`, `wget` | 500 error, DNS fail, API down   | `curl -I`, `dig domain.com`, `nslookup` |             |
| **L6 Presentation** | Encryption (SSL/TLS)  | `curl -v`, `openssl`              | SSL errors, cert issues         | `openssl s_client -connect host:443`    |             |
| **L5 Session**      | Sessions, connections | `netstat`, `ss`                   | Session drops, timeout          | `ss -s`, `netstat -an`                  |             |
| **L4 Transport**    | TCP/UDP, ports        | `ss -tulpn`, `netstat`            | Port closed, connection refused | `ss -tulpn                              | grep :port` |
| **L3 Network**      | IP, routing           | `ping`, `traceroute`, `ip route`  | No route, high latency          | `ping`, `traceroute`, `ip route`        |             |
| **L2 Data Link**    | MAC, LAN              | `ip link`, `arp -a`               | ARP issues, interface down      | `ip link show`, `arp -a`                |             |
| **L1 Physical**     | Hardware              | (no direct command)               | Cable unplugged, WiFi down      | `ethtool`, check cable/WiFi             |             |


How to Use This (Quick Mapping)
curl fails → L7
Connection refused → L4
Timeout → L3
No network → L2/L1
