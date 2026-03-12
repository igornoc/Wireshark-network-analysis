
# Wireshark Network Traffic Analysis

![Wireshark](https://img.shields.io/badge/tool-Wireshark-blue)
![Network Analysis](https://img.shields.io/badge/focus-Network%20Analysis-green)
![Cybersecurity](https://img.shields.io/badge/domain-Cybersecurity-red)

## Project Overview

This project demonstrates practical **network traffic analysis using Wireshark**.  
Network packets were captured from a local machine and analyzed to understand the behavior of several core internet protocols.

Protocols analyzed:

- DNS
- TCP
- HTTP
- ICMP
- UDP

The goal of the project is to demonstrate **packet inspection, protocol understanding, and network troubleshooting skills**.

---

## Skills Demonstrated

- Packet capture and inspection using Wireshark
- TCP/IP protocol analysis
- DNS query and response investigation
- TCP three‑way handshake analysis
- HTTP request/response inspection
- ICMP connectivity testing
- UDP stream analysis
- Packet filtering techniques

---

## Network Traffic Analysis Workflow

1. **Traffic Capture**
Captured live network packets using Wireshark during web browsing and ping tests.

2. **Packet Filtering**
Applied Wireshark display filters to isolate specific protocols.

3. **Protocol Identification**
Examined packet headers to identify communication patterns.

4. **Session Analysis**
Observed TCP handshakes and HTTP request‑response cycles.

5. **Stream Reconstruction**
Used Wireshark’s "Follow Stream" feature to reconstruct UDP communication.

6. **Documentation**
Captured screenshots and documented observations.

---

# Protocol Analysis

## DNS Traffic

Filter used:

```
dns
```

DNS packets show how domain names are translated into IP addresses.

Example DNS queries were observed for domains such as:

- openai.com
- google services domains

Screenshot:

![DNS Query](Screenshots/dns-query.png)

Additional capture:

![DNS Capture](Screenshots/dns-capture.png)

Key observations:

- DNS requests sent to public resolver (e.g. 8.8.8.8)
- Both A and AAAA records may be returned
- DNS typically precedes HTTP communication

---

## TCP Three‑Way Handshake

Filter:

```
tcp.flags.syn == 1
```

The TCP connection process:

1 SYN  
2 SYN‑ACK  
3 ACK  

Screenshot:

![TCP Handshake](Screenshots/tcp-handshake.png)

Key observations:

- Reliable connection establishment
- Sequence numbers used to track packet order

---

## HTTP Traffic (Port 80)

Filter:

```
tcp.port == 80
```

HTTP requests and responses were captured between client and server.

Screenshots:

![HTTP Traffic](Screenshots/http-traffic.png)

![HTTP Traffic](Screenshots/http-traffic-alt.png)

Example response observed:

```
HTTP/1.1 200 OK
```

This confirms successful web server communication.

---

## UDP Stream

Filter:

```
udp
```

UDP communication was examined using **Follow UDP Stream**.

Screenshot:

![UDP Stream](Screenshots/udp-stream.png)

Key observations:

- UDP is connectionless
- No handshake or retransmission

---

## ICMP (Ping)

Filter:

```
icmp
```

ICMP packets were captured during a ping test.

Screenshot:

![ICMP Ping](Screenshots/icmp-ping.png)

Key observations:

- Echo Request sent from client
- Echo Reply returned from destination host
- Used for connectivity diagnostics

---

## Additional UDP Flow

![UDP Flow](Screenshots/udp-flow.jpg)

---

# Security Insights

Several observations relevant to cybersecurity:

- **DNS traffic is unencrypted**, which can expose browsing activity.
- **HTTP traffic on port 80 is plaintext**, meaning contents could be intercepted.
- **ICMP traffic can be used for reconnaissance** during network scanning.
- **UDP traffic lacks reliability and verification**, which can be abused for amplification attacks.

---

# Additional Documentation

More detailed technical documentation:

- `analysis/protocol_findings.md`
- `filters/wireshark_filters.md`

---

# Future Improvements

Possible next steps:

- TLS / HTTPS traffic analysis
- Packet timing and latency analysis
- Suspicious traffic detection
- Malware traffic pattern identification

---

# Portfolio Summary

This project demonstrates practical experience with **network packet capture, protocol inspection, and traffic analysis using Wireshark**, showcasing skills relevant to cybersecurity and network engineering roles.
