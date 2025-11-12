# Network Security Protocols - TryHackMe Room Writeup

![TryHackMe](https://img.shields.io/badge/TryHackMe-Room-success)
![Network Security](https://img.shields.io/badge/Network-Security%20Protocols-blue)
![Difficulty](https://img.shields.io/badge/Difficulty-Intermediate-orange)
![Time](https://img.shields.io/badge/Time-3%20hours-purple)
![Category](https://img.shields.io/badge/Category-Security%20Engineering-green)

## 📋 Room Overview

**Room Title:** Network Security Protocols  
**Platform:** TryHackMe  
**Category:** Security Engineering / Network and System Security  
**Duration:** 180 minutes  
**Difficulty:** Intermediate  
**Completion Status:** 0% (Partial Completion)

## 🎯 Learning Objectives

This room provides comprehensive coverage of secure network protocols across different OSI model layers:

- **Application Layer Security Protocols** (HTTPS, FTPS, SMTPS, POP3S, DNSSEC, OpenPGP, SSH)
- **Presentation & Session Layer Protocols** (SSL/TLS, SOCKS5)
- **Network Layer Security** (IPsec, VPN technologies)
- **Practical implementation and configuration of secure protocols**

## 🔐 Core Protocols Covered

### Task 2: Application Layer Security Protocols

**HTTPS (Hypertext Transfer Protocol Secure)**
- **Purpose:** Secure web browsing and data transmission
- **Encryption:** SSL/TLS layer over HTTP
- **Port:** 443 (vs HTTP port 80)
- **Workflow:** Client-server encrypted communication preventing eavesdropping
- **Key Feature:** Protects sensitive information like credentials and financial data

**FTPS (File Transfer Protocol Secure)**
- **Purpose:** Secure file transfers
- **Modes:** 
  - **Active Mode:** Server initiates data connection to client
  - **Passive Mode:** Client establishes both control and data connections
- **Encryption:** TLS security for command and data channels
- **Ports:** 21 (Explicit), 990 (Implicit)

**SMTPS (Simple Mail Transfer Protocol Secure)**
- **Purpose:** Secure email transmission
- **Encryption:** Wraps SMTP inside TLS using STARTTLS command
- **Ports:** 587, 465
- **Protection:** Prevents email interception and tampering

**POP3S (Post Office Protocol Secure)**
- **Purpose:** Secure email retrieval
- **Encryption:** TLS wrapper around POP3
- **Port:** 995 (vs POP3 port 110)
- **Limitations:** Processes emails locally, no multi-device synchronization

**Answers:**
- Default HTTPS port: `443`
- Passive FTP command: `PASV`

### Task 3: Advanced Application Layer Protocols

**DNSSEC (Domain Name System Security Extensions)**
- **Purpose:** DNS response validation and protection against spoofing
- **Features:** 
  - **Authenticity:** Confirms DNS record authorship
  - **Integrity:** Ensures records aren't modified in transit
- **Mechanism:** Digital signatures using private/public key pairs

**OpenPGP & GnuPG**
- **Purpose:** End-to-end email encryption
- **PGP:** Pretty Good Privacy (Phil Zimmerman)
- **GPG:** Gnu Privacy Guard (OpenPGP implementation)
- **Key Management:** 
  - Private key for signing/decryption
  - Public key for verification/encryption
- **Command:** `gpg --gen-key` (key pair generation)

**SSH (Secure Shell)**
- **Purpose:** Secure remote system access
- **Advantages over Telnet:** Encrypted traffic, protected credentials
- **Protection:** Prevents eavesdropping and command manipulation

**Answers:**
- PGP: `Pretty Good Privacy`
- GPG: `Gnu Privacy Guard`
- Key generation command: `gpg --gen-key`
- Encrypted client: `3` (SSH)

### Task 4: Presentation & Session Layers

**SSL/TLS (Secure Sockets Layer/Transport Layer Security)**
- **Purpose:** General-purpose encryption wrapper for various protocols
- **Handshake Process:**
  1. Client Hello (TLS version, cipher suites)
  2. Server Hello (certificate, chosen cipher)
  3. Authentication (certificate validation)
  4. Key Exchange (premaster secret)
  5. Session Key Generation
  6. Encrypted Communication
- **Implementation:** Used in HTTPS, FTPS, SMTPS, POP3S

**SOCKS5 (Socket Secure Version 5)**
- **Purpose:** Proxy protocol for secure data exchange
- **Workflow:**
  1. Client Initiation (version, authentication methods)
  2. Proxy Reply (chosen authentication)
  3. Request Processing (host/port specification)
  4. Data Relay
- **Benefits:** Internal detail hiding, censorship bypassing

**Answers:**
- Hello message includes TLS version: `yea`
- SOCKS version byte: `5`
- Practical exercise flag: `THM{GOT_THE_SSLKEY}`

### Task 5: Network Layer Security

**IPsec (Internet Protocol Security)**
- **Components:**
  - **AH (Authentication Header):** Authentication and integrity (no confidentiality)
  - **ESP (Encapsulating Security Payload):** Authentication, integrity, and confidentiality
  - **SA (Security Association):** Key negotiation and management
- **Modes:**
  - **Transport Mode:** Secures payload only
  - **Tunnel Mode:** Secures entire IP packet

**VPN (Virtual Private Network)**
- **Purpose:** Secure private connections over public networks
- **Common Protocols:**
  - **IPsec:** Network-level security (Cisco VPN)
  - **SSL/TLS:** Application-level security (OpenVPN)
- **Legacy Protocols:** PPTP (no longer secure)

**Answers:**
- ESP: `Encapsulating Security Payload`
- Cisco VPN protocol: `IPsec`
- OpenVPN encryption: `SSL/TLS`

## 🛡️ Security Benefits Summary

### Confidentiality Protection
- **HTTPS/FTPS/SMTPS/POP3S:** SSL/TLS encryption
- **SSH:** Encrypted remote access
- **OpenPGP:** End-to-end email encryption
- **IPsec/VPN:** Secure network tunnels

### Integrity Assurance
- **DNSSEC:** Signed DNS records
- **SSL/TLS:** Message authentication codes
- **IPsec AH:** Packet integrity verification

### Authentication Mechanisms
- **Certificate-based:** SSL/TLS handshakes
- **Key-based:** SSH, OpenPGP
- **Protocol-specific:** SOCKS5 authentication methods

## 🔧 Practical Implementation Insights

### Protocol Selection Guidelines
- **Web Traffic:** Always use HTTPS (port 443)
- **File Transfer:** Prefer FTPS over FTP
- **Email:** Implement SMTPS/POP3S with OpenPGP for sensitive communications
- **Remote Access:** Use SSH instead of Telnet
- **DNS:** Deploy DNSSEC for resolution security
- **Network Connectivity:** Implement IPsec VPNs for site-to-site security

### Configuration Best Practices
- Regular certificate updates and validation
- Strong cipher suite selection
- Proper key management and rotation
- Comprehensive logging and monitoring

## 📈 Personal Reflection

This room provided an excellent comprehensive overview of network security protocols across all OSI layers. The structured approach from application to network layer protocols helped build a holistic understanding of how security is implemented at different network levels.

**Key Takeaways:**
- The evolution from cleartext protocols (HTTP, FTP, Telnet) to their secure counterparts demonstrates the industry's response to growing security threats
- SSL/TLS serves as a fundamental building block for multiple secure protocols
- Different security needs require different protocol solutions (end-to-end vs transport security)
- Practical implementation varies significantly across protocols while maintaining core security principles

**Technical Insights Gained:**
- Deep understanding of handshake processes in SSL/TLS and SOCKS5
- Clear differentiation between various secure email protocols and their use cases
- Appreciation for the layered security approach in modern networks
- Understanding of when to use transport vs tunnel mode in IPsec

**Areas for Further Exploration:**
- Advanced IPsec configuration and troubleshooting
- DNSSEC implementation challenges in enterprise environments
- Performance implications of various encryption protocols
- Emerging protocols like QUIC and their security implications

## 🎓 Professional Value

This knowledge is essential for:
- **Network Security Engineers** designing secure infrastructure
- **System Administrators** implementing security protocols
- **Security Analysts** understanding attack vectors and protections
- **IT Auditors** evaluating protocol implementation compliance
- **DevOps Engineers** securing application communications

The room successfully bridges theoretical concepts with practical implementations, making the knowledge directly applicable to real-world security scenarios.

---

*This writeup documents my systematic learning journey through the TryHackMe Network Security Protocols room, providing a comprehensive reference for secure protocol implementation across enterprise networks.*
