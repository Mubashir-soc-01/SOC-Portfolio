# Day 10 — Splunk SIEM Basics (Failed Login Detection)

## Topics I covered
- Creating test user in Windows
- Generating failed login attempts (Event ID 4625)
- Splunk data ingestion
- Windows Security logs in Splunk
- Splunk search queries
- Dashboard and alert creation

## What I did today

1. Created a test user `testuser` in Windows
2. Tried wrong password 4-5 times to generate failed login events
3. Installed Splunk Enterprise on Windows
4. Ingested Windows Security logs into Splunk
5. Searched for Event ID 4625 (failed logins)
6. Filtered searches by host name
7. Created a simple dashboard to monitor failed logins
8. Created an alert for brute force detection

## Why I did this

This is a lab practice to understand how failed login detection works. In a real SOC, multiple failed logins can indicate a brute force attack. Splunk helps detect and alert on such activity.

## Screenshots
All screenshots in `01-Screenshots/` folder

## Splunk searches I used

Search all failed logins:
index=* EventCode=4625

Search failed logins on specific host:
index=* EventCode=4625 host=mubashir

Count failed attempts by host:
index=* EventCode=4625 | stats count by host

## Dashboard created
- Name: Soc Brute Force Monitor
- Shows failed login events

## Alert created
- Name: Brute Force Detection
- Trigger: Number of results is greater than 0
- Schedule: Weekly

## What I learned

- `net user` command creates a local user in Windows
- Event ID 4625 = failed login attempt
- Wrong password attempts generate these logs
- Splunk can ingest Windows Security logs directly
- We can search, filter, and visualize failed login data
- Dashboards help monitor security events
- Alerts can notify SOC teams automatically

## Commands
All commands in `02-Commands/commands.txt`

## Time
- Lab setup and practice: 1:50 hours because Donwload time

Mohammad Mubashir
April 2026
