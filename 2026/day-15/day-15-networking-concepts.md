----------------------------------------------------------Task 1: DNS – How Names Become IPs--------------------------------------------------------------------


Explain in 3–4 lines: what happens when you type google.com in a browser?

When you type **google.com**, your system first performs a **DNS lookup** to convert the domain into an IP address.
Then, it establishes a **TCP connection (and TLS for HTTPS)** with Google’s server using that IP.
Your browser sends an **HTTP/HTTPS request**, and the server responds with the webpage data.
Finally, the browser **renders the HTML, CSS, and JavaScript** to display the page.



What are these record types? Write one line each:
A, AAAA, CNAME, MX, NS


Here are **one-line explanations** for each DNS record type:

* **A** → Maps a domain to an **IPv4 address** (e.g., google.com → 142.250.x.x)
* **AAAA** → Maps a domain to an **IPv6 address**
* **CNAME** → Alias of one domain to another domain (e.g., www → main domain)
* **MX** → Specifies **mail servers** for receiving emails for a domain
* **NS** → Defines **authoritative DNS servers** for the domain

---

# 🎯 Quick Memory Trick

* A = ipv4 Address
* AAAA = IPv6 Address
* CNAME = Canonical name (alias)
* MX = Mail
* NS = Name Server



Run: dig google.com — identify the A record and TTL from the output


How to read it (format)
<domain>  <TTL>  IN  A  <IP>


;; ANSWER SECTION:
google.com.		152	IN	A	142.251.223.206

A record → 142.251.223.206 (IPv4 address of google.com)
TTL → 152 (time in seconds the result is cached)


-------------------------------------------------------------------------------------Task 2: IP Addressing------------------------------------------------------------------------------


What is an IPv4 address? How is it structured? (e.g., 192.168.1.10)?
IPv4 is a 32-bit address written as four numbers (0–255) that uniquely identifies devices on a network.




Difference between public and private IPs — give one example of each

# 🧠 Public vs Private IP

## 🌐 Public IP

* Used on the **internet**, globally unique
* Assigned by ISP, accessible from anywhere

👉 Example:
`8.8.8.8` (Google DNS)

---

## 🏠 Private IP

* Used inside **local networks (LAN)**
* Not accessible directly from the internet

👉 Example:
`192.168.1.1`

---

# 🎯 One-line Summary

> Public IP = internet-facing, Private IP = internal network only.



What are the private IP ranges?

Here are the private IPv4 ranges (RFC 1918) — important for interviews:

🧠 Private IP Ranges
10.0.0.0 – 10.255.255.255
→ Large networks (Class A)
172.16.0.0 – 172.31.255.255
→ Medium networks (Class B)
192.168.0.0 – 192.168.255.255
→ Small/home networks (Class C)
🎯 Quick Memory Trick
10.x.x.x
172.16–31.x.x
192.168.x.x
🚀 One-line Summary

Private IPs are reserved for internal networks and are not routable on the public internet.




-------------------------------------------------------Task 3: CIDR & Subnetting------------------------------------------------------------------------------------


What does /24 mean in 192.168.1.0/24?

In 192.168.1.0/24
Total bits in IPv4 = 32
/24 → 24 bits = network
Remaining 8 bits = host

Number of hosts
8 bits for hosts → 2⁸ = 256 addresses
Usable hosts = 254 (excluding network + broadcast)


How many usable hosts in a /24? A /16? A /28?

🔹 /24
Host bits = 8
2⁸ - 2 = 254 usable hosts
🔹 /16
Host bits = 16
2¹⁶ - 2 = 65,534 usable hosts
🔹 /28
Host bits = 4
2⁴ - 2 = 14 usable hosts
🎯 One-line Summary

/24 → 254, /16 → 65,534, /28 → 14 usable hosts.


Explain in your own words: why do we subnet?

We subnet to divide a large network into smaller, manageable, secure, and efficient networks.


Quick exercise — fill in:

| CIDR | Subnet Mask     | Total IPs | Usable Hosts |
| ---- | --------------- | --------- | ------------ |
| /24  | 255.255.255.0   | 256       | 254          |
| /16  | 255.255.0.0     | 65,536    | 65,534       |
| /28  | 255.255.255.240 | 16        | 14           |


------------------------------------------------------------------------Task 4: Ports – The Doors to Services------------------------------------------------------

What is a port? Why do we need them?
A port is a logical number (0–65535) used to identify a specific service or process on a device
It works with an IP address to ensure data reaches the correct application

Why do we need ports?
A single system runs multiple services (web, SSH, database, etc.)
Ports help the system differentiate traffic

👉 Example:

192.168.1.10:80   → Web server (HTTP)
192.168.1.10:22   → SSH access

Without ports:
❌ System wouldn’t know whether data is for web, SSH, or database




Port	Service
22	SSH (Secure Shell)
80	HTTP
443	HTTPS
53	DNS
3306	MySQL
6379	Redis
27017	MongoDB






------------------------------------------------------------------------Task 5: Putting it together---------------------------------------------------------------------

You run curl http://myapp.com:8080 — what networking concepts from today are involved?

# 🧠 `curl http://myapp.com:8080` Flow

* **DNS (L7)** → domain → IP (`dig`)
* **Network (L3)** → route to IP (`ping`, `ip route`)
* **Transport (L4)** → TCP connection on port **8080**
* **TCP handshake** → connection established
* **Application (L7)** → HTTP request sent (`curl`)
* **Port** → `8080` selects correct service

---

# 🎯 One-line

> DNS → TCP → Port 8080 → HTTP request → response

Your app can't reach a database at 10.0.1.50:3306 — what would you check first?

I first check network connectivity (ping), then port reachability (nc/telnet), verify the DB service is listening, and finally check firewall rules.

🚀 Insight
Ping fails → network issue
Port fails → service/firewall issue
Both work → app/config issue



