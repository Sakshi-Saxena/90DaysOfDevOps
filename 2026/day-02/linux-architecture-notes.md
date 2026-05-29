-------------------------------------------------------------Architecture of Linux--------------------------------------------------

Linux architecture refers to the layered structure of the Linux operating system that defines how its components - such as the kernel, shell, system libraries, and hardware - 
interact with each other to manage system resources and execute user programs efficiently. It has the following components: 

----Diagram refer from hand written notes----------

Layers of a working computer
1. Kernel
The kernel is the core of the Linux operating system that manages hardware resources and controls communication between software and hardware.

Handles process management, memory, and device control.
Prevents conflicts between multiple running programs.
Types of Kernels: Monolithic, Microkernel, Hybrid, Exokernel

2. System Libraries
System libraries provide essential functions that allow applications to interact with the kernel without needing to access it directly.

Contain reusable pre-written code for common system operations.
Act as an interface between applications and the Linux kernel.
3. Shell
The shell is the command-line interface that allows users to communicate with the operating system by entering commands.

Interprets and executes user commands.
Acts as a bridge between user actions and kernel processing.
4. Hardware Layer
The hardware layer consists of physical components that execute commands and provide system resources.

Includes CPU, RAM, storage, and input/output devices.
Communicates with the OS using device drivers and kernel services.
5. System Utilities
System utilities are built-in tools that help users manage, configure, and maintain the operating system.

Used for tasks like software installation, user management, and monitoring.
Simplify system administration processes for both beginners and administrators.


==================================================================================================================================================

# 🧠 Linux Process States

## 🔵 Running (R)

* Process is **executing or ready for CPU**

## 🟡 Sleeping (S)

* Waiting for event (I/O, input)
* **Interruptible**, wakes easily

## 🔴 Uninterruptible Sleep (D)

* Waiting for **disk/network I/O**
* Cannot be interrupted → watch carefully

## ⚫ Zombie (Z)

* Process finished but **not cleaned by parent**
* Only PID remains

## ⚪ Stopped (T)

* Process **paused** (Ctrl+Z / signals)

---

# 🛠️ Daily Useful Commands

## 1. `ps`

```bash
ps aux
```

* Snapshot of all processes
* Shows PID, CPU, memory, state

---

## 2. `top` / `htop`

```bash
top
```

* Real-time monitoring
* Identify high CPU/memory processes

---

## 3. `systemctl`

```bash
systemctl status nginx
```

* Manage services (start/stop/restart/status)
* Used for systemd services

---

## 4. `kill`

```bash
kill -9 <PID>
```

* Stop/terminate a process
* `-9` = force kill

---

## 5. `jobs`

```bash
jobs
```

* Shows background/stopped jobs in current shell

---

## 6. `bg` / `fg`

```bash
bg
fg
```

* Resume stopped processes
* Run in background / foreground

---

# 🚀 Quick Insight

* `R` → running
* `S` → normal wait
* `D` → system-level wait (danger)
* `Z` → cleanup issue
* `T` → paused

---

🔍 Quick Summary Table
State	Code	Meaning
Running	R	Executing / ready
Sleeping	S	Waiting (interruptible)
Uninterruptible	D	Waiting (cannot interrupt)
Zombie	Z	Finished but not cleaned
Stopped	T	Paused
Idle	I	Kernel idle
Dead	X	Terminated

