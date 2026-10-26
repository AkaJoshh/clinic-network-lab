# Day 1: Setup (Oct 26, 2026)


## What I installed
- Git, VS Code, Wireshark (with Npcap), Cisco Packet Tracer

## Issue 1: Packet Tracer opened a firewall rule
- Multi-user "Listen" opened port 38000 with an inbound Allow rule on Public networks.
- **Found it:** `Get-NetFirewallRule -DisplayName "*packet*"`
- **Fix:** Stopped listening, then `Disable-NetFirewallRule -DisplayName "Packet Tracer Executable"`

## What I learned 
- Read the **first** error, not the last. The others are usually side efffects of the first.
- Open ports = attack surface; disable what you don't use 
- Application allowlisting (Smart App Control / WDAC)
- Least privilege: only use an admin window when needed
- PowerShell: Verb-Noun commands and the `|` pipe
