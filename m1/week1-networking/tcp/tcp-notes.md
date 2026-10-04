# TCP 3-Way Handshake

## Objective

Capture and identify the TCP 3-way handshake using Wireshark.

## What I Did

1. Started a Wireshark capture on the active network interface.
2. Generated a TCP connection using:
   `curl http://example.com`
3. Applied the Wireshark display filter:
   `tcp`
4. Identified the three packets that establish the TCP connection.

## TCP 3-Way Handshake Observed

The capture showed the following sequence:

1. **SYN** — Packet 59
   - Source: `192.168.0.112`
   - Destination: `142.250.134.139`
   - Destination port: `443`
   - Flags: `SYN`

2. **SYN-ACK** — Packet 60
   - Source: `142.250.134.139`
   - Destination: `192.168.0.112`
   - Source port: `443`
   - Destination port: `47650`
   - Flags: `SYN, ACK`

3. **ACK** — Packet 61
   - Source: `192.168.0.112`
   - Destination: `142.250.134.139`
   - Source port: `47650`
   - Destination port: `443`
   - Flags: `ACK`

## Observation

The capture demonstrates the TCP connection-establishment sequence:

`SYN → SYN-ACK → ACK`

The client first sends a SYN, the server responds with SYN-ACK, and the client sends the final ACK.

## Evidence

- `tcp-handshake.png`

## Tool Used

- Wireshark
- curl

## Notes

This was performed as part of the Month 1 Week 1 networking lab.
