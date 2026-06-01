Here’s a **clean, grouped Linux networking + system cheat sheet (commands + usage)** in **tabular form** for quick revision:

---

# 🌐 🧠 Linux Commands Cheat Sheet (Grouped)

---

## 🔍 Connectivity & Network Testing

| Command              | Usage                   | Purpose                    |
| -------------------- | ----------------------- | -------------------------- |
| `ping <host>`        | `ping google.com`       | Check if host is reachable |
| `traceroute <host>`  | `traceroute google.com` | Show path & latency        |
| `tracepath <host>`   | `tracepath google.com`  | Lightweight route trace    |
| `nc -zv <ip> <port>` | `nc -zv 10.0.0.1 80`    | Check port connectivity    |
| `telnet <ip> <port>` | `telnet 10.0.0.1 80`    | Manual port test           |

---

## 🌍 DNS Commands

| Command             | Usage                 | Purpose             |
| ------------------- | --------------------- | ------------------- |
| `dig <domain>`      | `dig google.com`      | Detailed DNS lookup |
| `nslookup <domain>` | `nslookup google.com` | Simple DNS query    |
| `host <domain>`     | `host google.com`     | Quick domain → IP   |

---

## 🌐 HTTP / API Testing

| Command         | Usage                  | Purpose           |
| --------------- | ---------------------- | ----------------- |
| `curl <url>`    | `curl http://site.com` | Fetch webpage/API |
| `curl -I <url>` | `curl -I google.com`   | Get headers only  |
| `wget <url>`    | `wget file.zip`        | Download files    |

---

## 🔌 Ports & Processes

| Command           | Usage            | Purpose                 |
| ----------------- | ---------------- | ----------------------- |
| `ss -tulpn`       | `ss -tulpn`      | Show listening ports    |
| `netstat -tulpn`  | `netstat -tulpn` | Legacy port check       |
| `lsof -i :<port>` | `lsof -i :8080`  | Find process using port |
| `ss -tpn`         | `ss -tpn`        | Show active connections |

---

## 🌐 IP & Interface Info

| Command          | Usage         | Purpose           |
| ---------------- | ------------- | ----------------- |
| `ip addr`        | `ip addr`     | Show IP addresses |
| `ip -brief addr` | `ip -br addr` | Clean IP view     |
| `hostname -I`    | `hostname -I` | Show system IP    |
| `ip link`        | `ip link`     | Interface status  |

---

## 🛣️ Routing

| Command    | Usage      | Purpose             |
| ---------- | ---------- | ------------------- |
| `ip route` | `ip route` | Show routing table  |
| `route -n` | `route -n` | Legacy routing info |

---

## 🔐 Firewall & Security

| Command                     | Usage                       | Purpose         |
| --------------------------- | --------------------------- | --------------- |
| `ufw status`                | `sudo ufw status`           | Check firewall  |
| `ufw allow <port>`          | `sudo ufw allow 80`         | Allow port      |
| `iptables -L -n`            | `sudo iptables -L -n`       | List rules      |
| `firewall-cmd --list-ports` | `firewall-cmd --list-ports` | firewalld ports |

---

## 📊 Monitoring & Debugging

| Command | Usage   | Purpose           |
| ------- | ------- | ----------------- |
| `top`   | `top`   | Live system usage |
| `iftop` | `iftop` | Network bandwidth |
| `nload` | `nload` | Traffic graph     |
| `ss -s` | `ss -s` | Socket summary    |

---

## 🔍 Advanced Networking

| Command              | Usage             | Purpose          |
| -------------------- | ----------------- | ---------------- |
| `tcpdump -i <iface>` | `tcpdump -i eth0` | Capture packets  |
| `arp -a`             | `arp -a`          | IP ↔ MAC mapping |

---

# 🚀 Quick Troubleshooting Flow

| Step | Command              | Goal               |
| ---- | -------------------- | ------------------ |
| 1    | `dig domain.com`     | Check DNS          |
| 2    | `ping <ip>`          | Check reachability |
| 3    | `traceroute <ip>`    | Check path         |
| 4    | `nc -zv <ip> <port>` | Check port         |
| 5    | `ss -tulpn`          | Check service      |
| 6    | `curl <url>`         | Check application  |

---

# 🎯 One-line Summary

> Use `dig → ping → traceroute → nc → ss → curl` to debug any network issue layer by layer.

---



