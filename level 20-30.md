# OverTheWire Bandit Write-ups (Levels 20–30)

---

## Level 20-21

In this level, we are given a **setuid binary** called `suconnect`.  
This program allows us to connect to a port and send a password to retrieve the next one.

We need to open **two terminals**:
- One to listen on a port
- Another to execute the `suconnect` binary

### 🔹 Commands Used
# Terminal 1 (listener)
nc -lvp 1234

# Terminal 2
./suconnect 1234

### 🔹 Screenshot
![Level 20 Output](images/bandit20.png)

---

## Level 21-22

The password for this level is stored inside a **cron job script**.  
Cron jobs are scheduled tasks in Linux, usually found in `/etc/cron.d/`.

### 🔹 Commands Used
ls /etc/cron.d/
cat /etc/cron.d/cronjob_bandit22
cat /usr/bin/cronjob_bandit22.sh

### 🔹 Screenshot
![Level 21 Output](images/bandit21.png)

---

## Level 22-23

In this level, the cron job dynamically creates a file with a **hashed filename**.  
We need to understand how the filename is generated.

### 🔹 Commands Used
cat /etc/cron.d/cronjob_bandit23
cat /usr/bin/cronjob_bandit23.sh
ls /tmp
cat /tmp/<generated_filename>

### 🔹 Screenshot
![Level 22 Output](images/bandit22.png)

---

## Level 23-24

This level allows us to **create our own script** that will be executed by cron.  
We write a script that copies the password to a file we control.

### 🔹 Commands Used
mkdir /tmp/myfolder
nano /tmp/myfolder/script.sh
chmod +x /tmp/myfolder/script.sh
echo "/tmp/myfolder/script.sh" > /var/spool/bandit24/cronjob

# After waiting for cron
cat /tmp/myfolder/password.txt

### 🔹 Screenshot
![Level 23 Output](images/bandit23.png)

---

## Level 24-25

The password for this level is protected by a **PIN brute-force challenge**.  
We must send all possible PIN combinations to a local service.

### 🔹 Commands Used
for i in {0000..9999}; do
  echo "password $i" | nc localhost 30002
done

### 🔹 Screenshot
![Level 24 Output](images/bandit24.png)

---

## Level 25-26

In this level, we are given an **SSH private key**, but the shell immediately logs us out.  
We bypass this by forcing a different shell.

### 🔹 Commands Used
ssh bandit26@bandit.labs.overthewire.org -p 2220 -i bandit26.key -t "bash --noprofile"

### 🔹 Screenshot
![Level 25 Output](images/bandit25.png)

---

## Level 26-27

This level involves escaping from a **restricted shell** using `vim`.

### 🔹 Commands Used
vim
:set shell=/bin/bash
:shell

cat /etc/bandit_pass/bandit27

### 🔹 Screenshot
![Level 26 Output](images/bandit26.png)

---

## Level 27-28

The password is stored inside a **Git repository**.  
We need to clone it and inspect the commit history.

### 🔹 Commands Used
git clone ssh://bandit27-git@localhost/home/bandit27-git/repo
cd repo
ls
cat README

### 🔹 Screenshot
![Level 27 Output](images/bandit27.png)

---

## Level 28-29

In this level, the password was **removed in the latest commit**.  
We need to look at previous commits.

### 🔹 Commands Used
git log
git checkout <previous_commit_hash>
cat README.md

### 🔹 Screenshot
![Level 28 Output](images/bandit28.png)

---

## Level 29-30

The password is hidden in a **branch other than master**.

### 🔹 Commands Used
git branch -a
git checkout dev
cat README.md

### 🔹 Screenshot
![Level 29 Output](images/bandit29.png)

---

