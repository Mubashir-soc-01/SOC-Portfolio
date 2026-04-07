# Day 5 — SQL Injection, MITRE ATT&CK, Social Engineering

## Topics I covered
- SQL Injection
- MITRE ATT&CK Framework
- Social Engineering

## SQL Injection

I practiced SQL injection on DVWA (Damn Vulnerable Web Application).

*Payloads I used:*

1. Login bypass:
1' OR '1'='1' #

This payload bypassed the login page and showed all users data.

2. Dump passwords:
1' UNION SELECT 1,user,password FROM users #

This payload extracted usernames and password hashes from the database.

*What I learned:*
- SQL injection happens when user input is not filtered properly
- Attacker can bypass login, steal data, or delete database
- Use prepared statements to prevent SQL injection

## MITRE ATT&CK

I explored the MITRE ATT&CK framework and searched for PowerShell technique.

*Technique details:*
- Technique ID: T1059.001
- Sub-technique of: T1059
- Tactic: Execution
- Platforms: Windows

*Description from MITRE:*
Adversaries may abuse PowerShell commands and scripts for execution. PowerShell can be used for discovery of information and execution of code. Examples include Start-Process cmdlet (run executables) and Invoke-Command cmdlet (run locally or remotely).

*Real attacker example:*
Sandworm Team used PowerShell to run a credential harvesting tool in memory to evade defenses.

*How SOC analysts detect PowerShell attacks:*
- Monitor Event ID 4104 (PowerShell Script Block Logging)
- Monitor Event ID 4688 (Process creation)
- Look for PowerShell with -ep bypass (bypasses execution policy)

## Social Engineering

Social engineering is tricking people, not computers.

*Real world example — Twitter Hack 2020:*
Attackers called Twitter employees pretending to be from IT support. They asked for passwords. Employees gave their passwords. Hackers took over celebrity accounts like Elon Musk and Bill Gates.

*Red flags to remember:*
1. Someone calling and asking for password
2. Urgency created by caller ("Do it now")
3. Authority trick ("I'm from IT department")
4. Asking for sensitive information

*How to protect:*
- Never share passwords on phone or email
- Always verify caller identity by calling back
- Security awareness training for employees

## What I learned today

- SQL injection can bypass login and steal database data
- MITRE ATT&CK helps understand attacker behavior
- PowerShell is commonly abused by attackers (T1059.001)
- Social engineering targets humans, not computers
- Always verify before giving access to anyone

## Screenshots
All screenshots in 01-Screenshots folder

## Commands
All commands in 02-Commands folder

## Time spent
- Theory: 45 minutes
- Practical: 55 minutes
- Documentation: 15 minutes

Mohammad Mubashir — SOC Analyst L1
7 April 2026
