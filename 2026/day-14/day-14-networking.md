----------------------------------------------------Identify---------------------------------------------------------------------------------------------------

sakshi@sakshi-B450M-S2H-V2:~/Desktop/sakshi_devops/sakshi-udaan/90DaysOfDevOps/2026/day-14$ ip -brief addr
lo               UNKNOWN        127.0.0.1/8 ::1/128 
enp8s0           UP             192.168.1.9/24 2401:4900:88f3:d9e2:b0d2:fbf4:838c:d15d/64 2401:4900:88f3:d9e2:a396:a785:a43c:594b/64 fe80::a78a:233f:1f5:6c31/64 
docker0          DOWN           172.17.0.1/16 
br-c8cdf98534db  DOWN           172.18.0.1/16 
sakshi@sakshi-B450M-S2H-V2:~/Desktop/sakshi_devops/sakshi-udaan/90DaysOfDevOps/2026/day-14$ hostname -I
192.168.1.9 172.17.0.1 172.18.0.1 2401:4900:88f3:d9e2:b0d2:fbf4:838c:d15d 2401:4900:88f3:d9e2:a396:a785:a43c:594b 
sakshi@sakshi-B450M-S2H-V2:~/Desktop/sakshi_devops/sakshi-udaan/90DaysOfDevOps/2026/day-14$ 


Quick rule
Command	Input
ping	hostname/IP ✅
curl	full URL ✅
wget	full URL ✅
dig	hostname ✅



-----------------------------------------------------Reachability----------------------------------------------------------------------------------------------

sakshi@sakshi-B450M-S2H-V2:~/Desktop/sakshi_devops/sakshi-udaan/90DaysOfDevOps/2026/day-14$ ping trainwithshubham.playground.utho.com
PING trainwithshubham.playground.utho.com (150.241.244.103) 56(84) bytes of data.
64 bytes from 150.241.244.103 (150.241.244.103): icmp_seq=1 ttl=55 time=26.5 ms
64 bytes from 150.241.244.103 (150.241.244.103): icmp_seq=2 ttl=55 time=20.9 ms
64 bytes from 150.241.244.103 (150.241.244.103): icmp_seq=3 ttl=55 time=20.2 ms
64 bytes from 150.241.244.103 (150.241.244.103): icmp_seq=4 ttl=55 time=21.0 ms
64 bytes from 150.241.244.103 (150.241.244.103): icmp_seq=5 ttl=55 time=19.7 ms
64 bytes from 150.241.244.103 (150.241.244.103): icmp_seq=6 ttl=55 time=19.8 ms
64 bytes from 150.241.244.103 (150.241.244.103): icmp_seq=7 ttl=55 time=22.4 ms
64 bytes from 150.241.244.103 (150.241.244.103): icmp_seq=8 ttl=55 time=19.4 ms
64 bytes from 150.241.244.103 (150.241.244.103): icmp_seq=9 ttl=55 time=17.8 ms
64 bytes from 150.241.244.103 (150.241.244.103): icmp_seq=10 ttl=55 time=19.0 ms
64 bytes from 150.241.244.103 (150.241.244.103): icmp_seq=11 ttl=55 time=23.8 ms
^C
--- trainwithshubham.playground.utho.com ping statistics ---
11 packets transmitted, 11 received, 0% packet loss, time 10014ms
rtt min/avg/max/mdev = 17.753/20.946/26.460/2.343 ms


The server is reachable with 0% packet loss and stable latency (~20 ms), indicating a healthy network connection.
Response times are consistent with minor variation (17–26 ms), showing good and reliable performance


-------------------------------------------------------traceroute/tracepath-------------------------------------------------------------------------------------------------------------

akshi@sakshi-B450M-S2H-V2:~/Desktop/sakshi_devops/sakshi-udaan/90DaysOfDevOps/2026/day-14$ traceroute trainwithshubham.playground.utho.com
traceroute to trainwithshubham.playground.utho.com (150.241.244.103), 30 hops max, 60 byte packets
 1  _gateway (192.168.1.1)  0.436 ms  1.210 ms  1.168 ms
 2  10.240.12.64 (10.240.12.64)  2.091 ms  2.088 ms  2.165 ms
 3  * * *
 4  59.145.43.121 (59.145.43.121)  2.081 ms 59.145.43.125 (59.145.43.125)  1.976 ms 59.145.43.121 (59.145.43.121)  1.975 ms
 5  182.79.211.35 (182.79.211.35)  53.117 ms  15.707 ms  15.949 ms
 6  aes-static-138.178.22.125.airtel.in (125.22.178.138)  18.561 ms  19.804 ms  22.176 ms
 7  182.255.57.190 (182.255.57.190)  17.853 ms  19.505 ms  17.875 ms
 8  103.216.95.50 (103.216.95.50)  17.736 ms  20.551 ms  19.433 ms
 9  103.15.80.138 (103.15.80.138)  17.914 ms  24.681 ms  17.738 ms
10  150.241.244.103 (150.241.244.103)  19.657 ms  19.837 ms  18.420 ms
11  * * *
12  * * *
13  * * *
14  * * *
15  * * *
16  * * *
17  * * *
18  * * *
19  * * *
20  * * *
21  * * *
22  * * *
23  * * *
24  * * *
25  * * *
26  * * *
27  * * *
28  * * *
29  * * *
30  * * *


Traffic reaches the destination at hop 10 with stable latency (~18–20 ms), indicating a healthy network path.
A temporary spike at hop 5 is observed but does not persist, so it’s not a real bottleneck.



----------------------------------------------------------------------------PORTS---------------------------------------------------------------------------------------------------


sakshi@sakshi-B450M-S2H-V2:~/Desktop/sakshi_devops/sakshi-udaan/90DaysOfDevOps/2026/day-14$ netstat -tulpn
(Not all processes could be identified, non-owned process info
 will not be shown, you would have to be root to see it all.)
Active Internet connections (only servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name    
tcp        0      0 0.0.0.0:5000            0.0.0.0:*               LISTEN      20557/python3       
tcp        0      0 127.0.0.1:45087         0.0.0.0:*               LISTEN      10178/code          
tcp        0      0 127.0.0.1:42927         0.0.0.0:*               LISTEN      -                   
tcp        0      0 127.0.0.53:53           0.0.0.0:*               LISTEN      -                   
tcp        0      0 127.0.0.1:631           0.0.0.0:*               LISTEN      -                   
tcp6       0      0 ::1:631                 :::*                    LISTEN      -                   
udp        0      0 224.0.0.251:5353        0.0.0.0:*                           2989/chrome         
udp        0      0 224.0.0.251:5353        0.0.0.0:*                           3070/renderD128 --c 
udp        0      0 0.0.0.0:5353            0.0.0.0:*                           -                   
udp        0      0 127.0.0.53:53           0.0.0.0:*                           -                   
udp        0      0 0.0.0.0:42223           0.0.0.0:*                           -                   
udp6       0      0 :::5353                 :::*                                -                   
udp6       0      0 fe80::a78a:233f:1f5:546 :::*                                -                   
udp6       0      0 :::50269                :::*          



The system is running multiple services listening on different ports (e.g., Python on port 5000, VS Code, DNS, printing service), with some only accessible locally (127.0.0.1) and others open to all (0.0.0.0).
The warning indicates you’re not running as root, so some process details (PID/program names) are hidden.


netstat and ss both show listening ports and services, but ss is faster and the modern preferred tool.

🔍 Meaning of flags
-t → TCP connections
-u → UDP connections
-l → listening ports only
-p → show PID/program name
-n → numeric (no DNS resolution)


---------------------------------------------------------------------------------DIG/NSLOOKUP---------------------------------------------------------------------------------------------------


sakshi@sakshi-B450M-S2H-V2:~/Desktop/sakshi_devops/sakshi-udaan/90DaysOfDevOps/2026/day-14$ dig trainwithshubham.playground.utho.com

; <<>> DiG 9.18.39-0ubuntu0.22.04.4-Ubuntu <<>> trainwithshubham.playground.utho.com
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 25322
;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 65494
;; QUESTION SECTION:
;trainwithshubham.playground.utho.com. IN A

;; ANSWER SECTION:
trainwithshubham.playground.utho.com. 300 IN A	150.241.244.103

;; Query time: 183 msec
;; SERVER: 127.0.0.53#53(127.0.0.53) (UDP)
;; WHEN: Mon Jun 01 17:31:30 IST 2026
;; MSG SIZE  rcvd: 81

sakshi@sakshi-B450M-S2H-V2:~/Desktop/sakshi_devops/sakshi-udaan/90DaysOfDevOps/2026/day-14$ nslookup trainwithshubham.playground.utho.com
Server:		127.0.0.53
Address:	127.0.0.53#53

Non-authoritative answer:
Name:	trainwithshubham.playground.utho.com
Address: 150.241.244.103


Both commands successfully resolve the domain to 150.241.244.103, confirming DNS is working, with dig providing detailed info and nslookup giving a simplified output.


----------------------------------------------------------HTTP Status code---------------------------------------------------------------------------------------------------------------------------------


sakshi@sakshi-B450M-S2H-V2:~/Desktop/sakshi_devops/sakshi-udaan/90DaysOfDevOps/2026/day-14$ curl -I https://trainwithshubham.playground.utho.com/
HTTP/2 200 
server: nginx/1.25.5
date: Mon, 01 Jun 2026 12:09:15 GMT
content-type: text/html
content-length: 28055
last-modified: Fri, 08 May 2026 11:24:30 GMT
etag: "69fdc7ee-6d97"
accept-ranges: bytes


It returns http status code 200.

----------------------------------------------------------------------Connections snapshot------------------------------------------------------------------------------------------------------


sakshi@sakshi-B450M-S2H-V2:~/Desktop/sakshi_devops/sakshi-udaan/90DaysOfDevOps/2026/day-14$ netstat -an | head
Active Internet connections (servers and established)
Proto Recv-Q Send-Q Local Address           Foreign Address         State      
tcp        0      0 0.0.0.0:5000            0.0.0.0:*               LISTEN     
tcp        0      0 127.0.0.1:45087         0.0.0.0:*               LISTEN     
tcp        0      0 127.0.0.1:42927         0.0.0.0:*               LISTEN     
tcp        0      0 127.0.0.53:53           0.0.0.0:*               LISTEN     
tcp        0      0 127.0.0.1:631           0.0.0.0:*               LISTEN     
tcp        0      0 192.168.1.9:41354       140.82.114.25:443       ESTABLISHED
tcp        0      0 192.168.1.9:41142       20.207.73.82:443        ESTABLISHED
tcp        0      0 192.168.1.9:44706       162.159.136.234:443     ESTABLISHED

netstat -an | head
-a → all connections (listening + established)
-n → show IPs/ports (no DNS resolution)
head → first few lines only


------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


Ports tell you where, PIDs tell you who, and tools like ss/lsof connect both.



----------------------------------------------------------------------------------------TASK-------------------------------------------------------------------------------------------

0.0.0.0:5000               0.0.0.0:*        users:(("python3",pid=20561,fd=4),("python3",pid=20561,fd=3),("python3",pid=20557,fd=3)) IS RUNNING:

akshi@sakshi-B450M-S2H-V2:~/Desktop/sakshi_devops/sakshi-udaan/90DaysOfDevOps/2026/day-14$ ss -tulpn
Netid    State     Recv-Q    Send-Q                           Local Address:Port          Peer Address:Port    Process                                                                                      
udp      UNCONN    0         0                                  224.0.0.251:5353               0.0.0.0:*        users:(("chrome",pid=2989,fd=594))                                                          
udp      UNCONN    0         0                                  224.0.0.251:5353               0.0.0.0:*        users:(("chrome",pid=3070,fd=124))                                                          
udp      UNCONN    0         0                                      0.0.0.0:5353               0.0.0.0:*                                                                                                    
udp      UNCONN    0         0                                127.0.0.53%lo:53                 0.0.0.0:*                                                                                                    
udp      UNCONN    0         0                                      0.0.0.0:42223              0.0.0.0:*                                                                                                    
udp      UNCONN    0         0                                         [::]:5353                  [::]:*                                                                                                    
udp      UNCONN    0         0            [fe80::a78a:233f:1f5:6c31]%enp8s0:546                   [::]:*                                                                                                    
udp      UNCONN    0         0                                         [::]:50269                 [::]:*                                                                                                    
tcp      LISTEN    0         128                                    0.0.0.0:5000               0.0.0.0:*        users:(("python3",pid=20561,fd=4),("python3",pid=20561,fd=3),("python3",pid=20557,fd=3))    
tcp      LISTEN    0         511                                  127.0.0.1:45087              0.0.0.0:*        users:(("code",pid=10178,fd=36))                                                            
tcp      LISTEN    0         4096                                 127.0.0.1:42927              0.0.0.0:*                                                                                                    
tcp      LISTEN    0         4096                             127.0.0.53%lo:53                 0.0.0.0:*                                                                                                    
tcp      LISTEN    0         128                                  127.0.0.1:631                0.0.0.0:*                                                                                                    
tcp      LISTEN    0         128                                      [::1]:631                   [::]:*                                                                                                    
sakshi@sakshi-B450M-S2H-V2:~/Desktop/sakshi_devops/sakshi-udaan/90DaysOfDevOps/2026/day-14$ curl -I 0.0.0.0:5000
HTTP/1.0 200 OK
Content-Type: text/html; charset=utf-8
Content-Length: 4270
Server: Werkzeug/2.0.2 Python/3.10.12
Date: Mon, 01 Jun 2026 12:23:48 GMT

sakshi@sakshi-B450M-S2H-V2:~/Desktop/sakshi_devops/sakshi-udaan/90DaysOfDevOps/2026/day-14$ nc -zv localhost 5000
Connection to localhost (127.0.0.1) 5000 port [tcp/*] succeeded!


0.0.0.0:5000               0.0.0.0:*        users:(("python3",pid=20561,fd=4),("python3",pid=20561,fd=3),("python3",pid=20557,fd=3)) IS NOT RUNNING:

sakshi@sakshi-B450M-S2H-V2:~/Desktop/sakshi_devops/sakshi-udaan/90DaysOfDevOps/2026/day-14$ ss -tulpn
Netid          State           Recv-Q          Send-Q                                       Local Address:Port                      Peer Address:Port          Process                                      
udp            UNCONN          0               0                                              224.0.0.251:5353                           0.0.0.0:*              users:(("chrome",pid=2989,fd=594))          
udp            UNCONN          0               0                                              224.0.0.251:5353                           0.0.0.0:*              users:(("chrome",pid=3070,fd=124))          
udp            UNCONN          0               0                                                  0.0.0.0:5353                           0.0.0.0:*                                                          
udp            UNCONN          0               0                                            127.0.0.53%lo:53                             0.0.0.0:*                                                          
udp            UNCONN          0               0                                                  0.0.0.0:42223                          0.0.0.0:*                                                          
udp            UNCONN          0               0                                                     [::]:5353                              [::]:*                                                          
udp            UNCONN          0               0                        [fe80::a78a:233f:1f5:6c31]%enp8s0:546                               [::]:*                                                          
udp            UNCONN          0               0                                                     [::]:50269                             [::]:*                                                          
tcp            LISTEN          0               511                                              127.0.0.1:45087                          0.0.0.0:*              users:(("code",pid=10178,fd=36))            
tcp            LISTEN          0               4096                                             127.0.0.1:42927                          0.0.0.0:*                                                          
tcp            LISTEN          0               4096                                         127.0.0.53%lo:53                             0.0.0.0:*                                                          
tcp            LISTEN          0               128                                              127.0.0.1:631                            0.0.0.0:*                                                          
tcp            LISTEN          0               128                                                  [::1]:631                               [::]:*                                                          
sakshi@sakshi-B450M-S2H-V2:~/Desktop/sakshi_devops/sakshi-udaan/90DaysOfDevOps/2026/day-14$ nc -zv localhost 5000
nc: connect to localhost (127.0.0.1) port 5000 (tcp) failed: Connection refused
sakshi@sakshi-B450M-S2H-V2:~/Desktop/sakshi_devops/sakshi-udaan/90DaysOfDevOps/2026/day-14$ curl -I 0.0.0.0:5000
curl: (7) Failed to connect to 0.0.0.0 port 5000 after 0 ms: Connection refused


since it is not running, we checked the service status and found it to be not running.

“If a service works locally but not remotely, I check if it’s bound to 0.0.0.0 and then verify firewall rules using UFW or iptables. If the port is blocked, I allow it and retest.”

🧠 One-line Insight

Firewall issues = works locally but not from outside


-----------------------------------------------------------IMP TIPS:--------------------------------------------------------------------------------------------------------------------------


Final Mental Model (VERY IMPORTANT)
DNS → Network → Port → Service → Application

👉 Always debug in this order

🧠 Perfect Interview Answer (30 sec)


“I start with curl for a quick signal (curl -I http://service), then follow a layered approach:
DNS resolution (dig domain.com),
network connectivity (ping <ip> / traceroute <ip>),
port availability (ss -tulpn | grep :port),
service status (systemctl status <service>),
and finally application logs (journalctl -u <service> / tail -f /var/log/...).
This helps quickly isolate whether the issue is network, system, or application related.”












Here’s a **clean, interview-ready quick concepts summary**:

---

# 🧠 OSI vs TCP/IP Stack

* **OSI (7 layers)** → Conceptual model (L1 Physical → L7 Application)
* **TCP/IP (4 layers)** → Practical model (Link → Internet → Transport → Application)
* TCP/IP is what actually runs on the internet; OSI is for understanding

---

# 📍 Where protocols sit

* **IP** → Internet layer (routing, addressing)
* **TCP/UDP** → Transport layer (reliable vs fast communication)
* **HTTP/HTTPS** → Application layer (web communication)
* **DNS** → Application layer (domain → IP resolution)

---

# 🌐 Real Example

* `curl https://example.com`
  → Application (HTTP/HTTPS)
  → runs over **TCP (Transport)**
  → which runs over **IP (Internet layer)**

👉 Full flow:

```text
HTTP (App) → TCP (Transport) → IP (Internet) → Network
```

---

# 🎯 One-line Summary

> OSI explains layers, TCP/IP implements them; protocols like HTTP, TCP, and IP stack together to deliver data across networks.

---

If you want, I can give you a **memory trick to recall all 7 OSI layers in 5 seconds (interview hack)**.


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


