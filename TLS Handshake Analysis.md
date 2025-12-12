# TLS Handshake Analysis — Client Hello

This document explains the TLS handshake process based on a captured Client Hello packet.

# 1. What Is the TLS Handshake?
TLS (Transport Layer Security) protects communication between a client and a web server.
During the handshake:
- The client and server agree on encryption
- Keys are securely exchanged
- The server proves its identity with certificates
- An encrypted tunnel is created for all further traffic
The Client Hello message initiates this process.

# 2. Packet Overview
**TLS Record Layer**
TLSv1.3 Record Layer: Handshake Protocol: Client Hello
Content Type: Handshake (22)
Version: TLS 1.0 (0x0301)
Length: 1900

**Handshake Fields**
TLS Version: TLS 1.2 (0x0303)
Random: eb208f5dad56faa5e8794fc16a765bf93d740f93f457a4897d4d7f35307765
Session ID Length: 32
Session ID: 4565f451fe544ef8532ab302c32da3fef734a8b74a3e9539c23f8c0b4070e74c
Cipher Suites Offered: 17 total

**SNI (Server Name Indication)**
This extension reveals the hostname requested by the client:
"collector.github.com"
    
    SNI is critical for SOC analysts because it identifies the destination domain even when the payload is encrypted.

# 3. What Happens After Client Hello?
**a. Server Hello**
Server selects a cipher suite and sends its certificate.
**b. Key Exchange**
In TLS 1.3, this uses Ephemeral Diffie–Hellman.
**c. Secure Connection Established**
All subsequent communication becomes encrypted.
