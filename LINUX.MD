Below is the **Beginner-Friendly Linux Interview Q&A Set (30 Questions)** with
✔ **Proper interview-style responses**
✔ **Short examples**
✔ **Easy explanations**

This is PERFECT for freshers preparing for Linux interviews.

---

# 🐧 **Linux Interview – 30 Beginner Questions with Example Answers**

---

## ✅ **1. What is Linux?**

**Answer:**
Linux is an open-source operating system based on UNIX. It is widely used in servers, cloud systems, and embedded devices.

**Example:**
Ubuntu, CentOS, Red Hat are Linux distributions.

---

## ✅ **2. What is a shell?**

**Answer:**
A shell is a program that interprets user commands and communicates with the kernel.

**Example:**
Bash shell is the most commonly used shell.

---

## ✅ **3. What is a terminal?**

**Answer:**
A terminal is the interface where you type commands to interact with the shell.

**Example:**
The black command window you open using **Ctrl+Alt+T**.

---

## ✅ **4. What does the `ls` command do?**

**Answer:**
It lists all files and directories in the current folder.

**Example:**
`ls -l` → shows detailed info (permissions, size, owner).

---

## ✅ **5. What does `pwd` do?**

**Answer:**
It prints the current working directory.

**Example:**
`/home/pratham/Documents`

---

## ✅ **6. How do you change directories?**

**Answer:**
Use the `cd` command to move to another folder.

**Example:**
`cd /var/log`

---

## ✅ **7. How do you create a file?**

**Answer:**
Use the `touch` command.

**Example:**
`touch notes.txt` → creates an empty file.

---

## ✅ **8. How do you create a directory?**

**Answer:**
Use the `mkdir` command.

**Example:**
`mkdir projects`

---

## ✅ **9. How do you delete a file?**

**Answer:**
Use the `rm` command.

**Example:**
`rm oldfile.txt`

---

## ✅ **10. How do you delete a directory?**

**Answer:**
Use `rm -r` to delete a directory with all contents.

**Example:**
`rm -r myfolder`

---

# 📄 **Viewing & Editing Files**

## ✅ **11. How do you view the content of a file?**

**Answer:**
Use `cat`, `less`, or `more`.

**Example:**
`less logfile.txt` → scroll through logs.

---

## ✅ **12. Difference between `cat` and `less`?**

**Answer:**
`cat` shows the whole file at once.
`less` shows content page-by-page.

**Example:**
Large files → `less` is preferred.

---

# 🗂 **File Management**

## ✅ **13. How to copy a file?**

**Answer:**
Use the `cp` command.

**Example:**
`cp file1.txt backup.txt`

---

## ✅ **14. How to move or rename a file?**

**Answer:**
Use the `mv` command.

**Example:**
`mv oldname.txt newname.txt`

---

## ✅ **15. How to search for text inside a file?**

**Answer:**
Use the `grep` command.

**Example:**
`grep "error" /var/log/messages`

---

# 🔐 **Permissions & Ownership**

## ✅ **16. What does `chmod` do?**

**Answer:**
Changes the permissions of a file or folder.

**Example:**
`chmod 755 script.sh` → gives execute access.

---

## ✅ **17. What does `chown` do?**

**Answer:**
Changes the owner or group of a file.

**Example:**
`chown root:root config.txt`

---

# 🖥 **System Information & Processes**

## ✅ **18. What does `top` show?**

**Answer:**
It displays real-time system processes and resource usage.

**Example:**
CPU usage, memory, running processes.

---

## ✅ **19. What does `ps` show?**

**Answer:**
It lists active processes (snapshot).

**Example:**
`ps aux` → shows all processes.

---

## ✅ **20. How do you check disk usage?**

**Answer:**
Use `df -h` for disk size and usage.

**Example:**
`df -h` shows disk partitions with human-readable sizes.

---

## ✅ **21. How do you check folder size?**

**Answer:**
Use `du -sh foldername`.

**Example:**
`du -sh /var/log` → shows total log directory size.

---

# 🌐 **Networking Basics**

## ✅ **22. How do you check your current user?**

**Answer:**
Use the `whoami` command.

**Example:**
Output → `pratham`

---

## ✅ **23. How do you check who is logged in?**

**Answer:**
Use `who`.

---

## ✅ **24. How do you check network connectivity?**

**Answer:**
Use `ping`.

**Example:**
`ping google.com` → checks internet connection.

---

## ✅ **25. How to check your IP address?**

**Answer:**
`ifconfig` or `ip addr`

**Example:**
`ip addr show eth0`

---

## ✅ **26. How to download a file from the internet?**

**Answer:**
Use `wget` or `curl`.

**Example:**
`wget https://example.com/file.zip`

---

# 👥 **User & Group Management**

## ✅ **27. How do you add a user?**

**Answer:**
Use `useradd`.

**Example:**
`useradd student1`

---

## ✅ **28. How do you set a user password?**

**Answer:**
Use `passwd`.

**Example:**
`passwd student1`

---

## ✅ **29. What is the root user?**

**Answer:**
Root is the superuser with full system access.

**Example:**
Root can install/remove any software.

---

## ✅ **30. What is a package manager?**

**Answer:**
It installs, updates, and removes software.

**Examples:**

* Ubuntu → `apt`
* RedHat/CentOS → `yum` or `dnf`

