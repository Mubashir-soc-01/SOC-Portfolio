# Day 6 — Linux Basics

## Topics Covered
- Linux File Permissions (chmod, chown)
- Linux Log Locations
- grep, awk, commands

## Practicals Done

### 1. File Permissions
- Created test file and changed permissions using chmod 755
- Created a script and added execute permission
- Changed file owner using chown

### 2. Log Locations
- Listed all logs in /var/log/ directory
- Viewed auth.log and syslog using head and tail

### 3. grep, awk, tail, sed
- Created a test log file with SSH login attempts
- Used grep to find failed passwords
- Used awk to extract IP addresses and usernames
- Used sort, uniq, sort -nr to find top attacking IPs
- Used sed to replace text

## Screenshots
All screenshots in 01-Screenshots folder

## Commands
All commands in 02-Commands folder

## Key Learnings
- chmod 755 is common for scripts, 644 for normal files
- /var/log/auth.log is first place to check for SSH brute force
- grep + awk can extract attacking IPs from logs
- tail -f is useful for real-time monitoring

## Time Spent
- Theory: 1 hrs.
- Practical: 35 min

Mohammad Mubashir
8 April 2026
