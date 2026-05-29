---------------------------------------------------Linus Commands Cheatsheet-------------------------------------------------

---

# 🧠 Linux Process States

* **R (Running)** → executing or ready for CPU
* **S (Sleeping)** → waiting (I/O/input), interruptible
* **D (Uninterruptible)** → waiting on disk/network (critical)
* **Z (Zombie)** → finished, not cleaned by parent
* **T (Stopped)** → paused (Ctrl+Z / signal)

👉 Quick: `R = CPU`, `S = normal wait`, `D = stuck`, `Z = cleanup issue`

---

# 🛠️ Process & System Monitoring

* `ps aux` → snapshot of all processes (PID, CPU, MEM)
* `top` → real-time process monitoring
* `htop` → interactive process viewer
* `uptime` → system load + uptime
* `free -h` → memory usage

---

# ⚙️ Process Management

* `kill <PID>` → terminate process
* `kill -9 <PID>` → force kill
* `pkill <name>` → kill by name
* `jobs` → list background jobs
* `fg` / `bg` → foreground/background control

---

# 🔧 Service Management (systemd)

* `systemctl status nginx` → check service status
* `systemctl start nginx` → start service
* `systemctl stop nginx` → stop service
* `systemctl restart nginx` → restart service
* `systemctl enable nginx` → enable at boot

---

# 🌐 Networking Commands

* `ping google.com` → check connectivity
* `ip addr` → show IP addresses
* `curl <url>` → fetch API/web response
* `dig google.com` → DNS lookup

---

# 🗂️ File & Directory Operations

* `ls -lh` → list files with size
* `cd <dir>` → change directory
* `pwd` → current path
* `cp -r src dest` → copy directory
* `mv src dest` → move/rename
* `rm -rf <dir>` → delete forcefully

---

# 📦 Disk & Storage

* `df -h` → disk usage (filesystem)
* `du -sh <dir>` → directory size
* `lsblk` → list disks
* `mount` → mounted filesystems

---

# 🔍 File Viewing & Search

* `cat file.txt` → display file
* `less file.txt` → scroll view
* `head -n 10 file.txt` → first lines
* `tail -f log.txt` → live logs
* `grep "text" file.txt` → search text

---

# 🔐 Permissions & Users

* `chmod +x script.sh` → make executable
* `chown user:group file` → change ownership
* `whoami` → current user
* `id` → user/group details

---

# 📁 Archives & Compression

* `tar -czf file.tar.gz dir/` → create archive
* `tar -xzf file.tar.gz` → extract archive
* `zip -r file.zip dir/` → zip folder
* `unzip file.zip` → extract zip

---

# 🚀 Practical Insight

* Use `top` → find high CPU issues
* Use `ps + grep` → quick process search
* Use `systemctl` → manage services
* Use `curl/ping` → debug networking
* Watch `D` and `Z` states → potential issues

---



