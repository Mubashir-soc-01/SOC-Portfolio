# Day 8 — Windows Event Logs

Today I learned about Windows Event Logs. I practically checked three important Event IDs.

## Topics I Covered
- Event ID 4624 (Successful Logon)
- Event ID 4625 (Failed Logon)
- Event ID 4688 (Process Creation)

## What I Did

*Event ID 4624*
I restarted my computer and logged in. Opened Event Viewer, went to Security log, and applied filter 4624. I saw my login event. Logon Type was 2 (local login).

*Event ID 4625*
I locked my computer (Windows + L). Typed wrong password 2-3 times. In Event Viewer, I applied filter 4625. I saw failed login events. Status code was 0xC000006D (wrong password).

*Event ID 4688*
I opened Admin Command Prompt and ran the auditpol command. Then I opened Notepad. In Event Viewer, I applied filter 4688. I saw notepad.exe process creation event.

## Commands I Used

In Admin Command Prompt:
auditpol /set /subcategory:"Process Creation" /success:enable

## Where to Find Logs
Event Viewer → Windows Logs → Security

## What I Learned

*Event ID 4624 — Successful Logon*
- Account Name: who logged in
- Logon Type: how they logged in (2=local, 3=network, 10=RDP)
- Source Network Address: IP for remote login

*Event ID 4625 — Failed Logon*
Status codes:
- 0xC0000064 = user does not exist
- 0xC000006A = valid user, wrong password
- 0xC000006D = wrong password (general)
- 0xC000006F = account locked

*Event ID 4688 — Process Creation*
- Process Name: which program ran
- Parent Process: who started it
- Command Line: full command

*Logon Types (Remember These)*
- Type 2 = local login
- Type 3 = network / file share
- Type 10 = RDP (attacker favorite)

## What to Monitor

For brute force (4625):
- Many failed logins from same IP
- Logon Type 10 with external IP
- Status code 0xC0000064

For malware (4688):
- powershell.exe with -ep bypass or -enc
- Unknown .exe from Temp folder
- Office apps spawning cmd or PowerShell

## Time Spent
- Theory: 20 min
- Practical: 50 min

Mohammad Mubashir
11 April 2026
