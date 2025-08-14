# 🧩 Troubleshooting Ticket Simulation

**Scenario:** A user reports intermittent internet access and slow application logins on a Windows laptop.

## Goals
- Identify root cause
- Restore stable connectivity
- Document steps for handoff

## Environment
- Windows 10/11
- Office Wi-Fi (WPA2)
- Router: 192.168.1.1
- DNS: 1.1.1.1 / 8.8.8.8

## Steps Taken
1. Gathered facts (scope, recent changes, error messages)
2. Network triage: `ipconfig`, `ping`, `tracert`, `nslookup`
3. Reset Winsock & TCP/IP stack, updated NIC driver
4. Switched to public DNS, flushed cache
5. Resynced NTP to fix Kerberos/SSO delay

## Commands
```bat
ipconfig /all
ipconfig /flushdns
netsh winsock reset
netsh int ip reset
w32tm /resync
```
```powershell
Test-NetConnection -ComputerName contoso.com -Port 443
```
```bash
ping -c 4 8.8.8.8
traceroute 8.8.8.8
```

## Outcome
- Restored stable connectivity
- Reduced login time from 45s to 8s
