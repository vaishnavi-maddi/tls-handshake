# TLS Handshake Traffic Analysis 

This project analyzes the TLS Client Hello packet to understand how encrypted HTTPS communication begins. The lab demonstrates how modern browsers negotiate TLS, choose encryption algorithms, and identify the destination server using SNI.

## Objective
- Capture TLS handshake packets using Wireshark  
- Identify Client Hello fields  
- Understand TLS negotiation flow  
- Interpret SOC-relevant metadata such as SNI and cipher suites  

## Methodology
1. Started packet capture on interface `ens33`  
2. Visited HTTPS websites to generate TLS traffic  
3. Applied the filter: tls
4. Located and analyzed the **Client Hello** packet  
5. Saved filtered packets as `tls-handshake-s.pcapng` 
