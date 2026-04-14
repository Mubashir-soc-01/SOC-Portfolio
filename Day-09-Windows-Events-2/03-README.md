# Day 9 — Windows Event IDs Part 2

## Topics I covered
- Event ID 4720 (User Created)
- Event ID 1102 (Log Cleared)
- Logon Types (2, 3, 10)
- PowerShell Logging

## What I did today
1. Created a new user and saw Event ID 4720
2. Cleared event logs and saw Event ID 1102
3. Tested different logon types
4. Enabled PowerShell logging

## Event ID 4720 — User Created
This event logs when a new user account is created.

How to generate:
net user testuser2 Test123@ /add

Check in Event Viewer:
Windows Logs → Security → Filter Event ID: 4720

## Event ID 1102 — Log Cleared
This event logs when someone clears the audit log. Attackers do this to hide their tracks.

How to generate:
1. Event Viewer → Windows Logs → Security
2. Right click → Clear Log → Click "Clear"

Check Event ID: 1102 in Security log

## Logon Types
Type 2 — Interactive (logging on at physical console)
Type 3 — Network (accessing shared folders or printers)
Type 10 — RemoteInteractive (RDP login)

How to check:
Filter Event ID 4624 → Look at "Logon Type" field

## PowerShell Logging
PowerShell logging captures all PowerShell commands. Even obfuscated commands are logged in plain text.

Enable logging:
New-Item -Path "HKLM:\SOFTWARE\Policies\Microsoft\Windows\PowerShell" -Name "ScriptBlockLogging" -Force
Set-ItemProperty -Path "HKLM:\SOFTWARE\Policies\Microsoft\Windows\PowerShell\ScriptBlockLogging" -Name "EnableScriptBlockLogging" -Value 1

Check Event ID 4104:
Applications and Services Logs → Microsoft → Windows → PowerShell → Operational → Filter Event ID: 4104

## What I learned
- Event 4720 helps track who created users
- Event 1102 is a red flag — attacker is covering tracks
- Logon Type 10 = RDP login
- PowerShell logging shows decoded commands even when obfuscated
- Always monitor Event ID 4104 for suspicious PowerShell activity

## Time
Theory: 20 min | Practical: 25 min

Mohammad Mubashir
April 2026
