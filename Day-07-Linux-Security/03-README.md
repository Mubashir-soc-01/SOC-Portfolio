# Day 7 — Processes, SSH Logs, Cron Jobs

## Topics Covered
- Processes & PID
- Failed SSH Login Detection
- Cron Jobs + Misuse

## Practicals Done

### 1. Processes & PID
- Viewed all running processes using ps aux
- Used top for real-time monitoring

### 2. Failed SSH Login Detection
- Created a test log file with SSH login attempts
- Used grep to find failed password attempts
- Used awk to extract IP addresses and usernames
- Used sort, uniq, sort -nr to find top attacking IPs
- Learned real SOC workflow for detecting SSH brute force

### 3. Cron Jobs
- Viewed current user's cron jobs using crontab -l
- Added a test cron job to run every 5 minutes
- Explored system cron directories (/etc/cron.d/, /etc/cron.hourly/, etc.)
- Checked cron logs in /var/log/syslog
- Learned how to remove all cron jobs using crontab -r

## Screenshots
All screenshots are in the 01-Screenshots/ folder

## Commands
All commands are in the 02-Commands/commands.txt file

## Key Learnings

### Processes
- Every running program is a process with a unique PID
- ps aux shows snapshot, top shows real-time
- Kill -9 PID forces a process to stop

### SSH Logs
- /var/log/auth.log contains all SSH login attempts
- Failed password entries indicate brute force attempts
- awk '{print $11}' extracts IP addresses from log lines

### Cron Jobs
- Cron jobs are used for persistence by attackers
- Check crontab -l regularly for unauthorized entries
- System cron directories in /etc/cron.* can also hide malware

## Time Spent
- Theory: 20 min
- Practical: 25 min

Mohammad Mubashir
April 2026
