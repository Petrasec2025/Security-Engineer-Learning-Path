# Network Device Hardening - TryHackMe Room Writeup

![TryHackMe](https://img.shields.io/badge/TryHackMe-Room-success)
![Network Security](https://img.shields.io/badge/Network-Device%20Hardening-blue)
![Difficulty](https://img.shields.io/badge/Difficulty-Intermediate-orange)
![Time](https://img.shields.io/badge/Time-3%20hours-purple)
![Category](https://img.shields.io/badge/Category-Security%20Engineering-green)

## 📋 Room Overview

**Room Title:** Network Device Hardening  
**Platform:** TryHackMe  
**Category:** Security Engineering / Network and System Security  
**Duration:** 180 minutes  
**Difficulty:** Intermediate  
**Completion Status:** 5% (Partial Completion)

## 🎯 Learning Objectives

This room focuses on essential network device security concepts including:

- **Identifying and mitigating security vulnerabilities**
- **Hardening network device configurations**
- **Implementing security best practices**
- **Enhancing network resilience against cyber threats**

## 🔍 Core Concepts Covered

### Task 2: Common Threat and Attack Vectors

**Key Differentiations:**
- **Network Devices:** Control and manage network resources (routers, switches, firewalls)
- **Endpoint Devices:** Generate/consume data at network edge (laptops, smartphones, servers)

**Major Threats Identified:**
- **Unauthorized Access:** Password attacks, vulnerability exploitation, social engineering
- **Denial of Service (DoS):** Service disruption through flooding and resource exhaustion
- **Man-in-the-Middle Attacks:** ARP/DNS spoofing, rogue access points
- **Privilege Escalation:** Weak credentials, vulnerability exploitation
- **Bandwidth Theft:** Unauthorized resource linking and data scraping

**Answer:** `Denial of Service (DoS)`

### Task 3: Common Hardening Techniques

**General Hardening Methods:**
- **Updating & Patching:** Regular security updates for OS and applications
- **Service & Port Management:** Disabling unnecessary services and ports
- **Principle of Least Privilege (POLP):** Minimum necessary permissions
- **Log Monitoring:** Security event detection and analysis
- **Regular Backups:** Incident recovery preparedness
- **Strong Authentication:** Complex passwords and Multi-Factor Authentication (MFA)

**Secure Protocol Implementation:**
- **Secure Protocols:** HTTPS, SSH, SSL/TLS, IPsec
- **Insecure Protocols to Block:** FTP, HTTP, Telnet, SMTP (clear-text transmission)

**Monitoring & Logging:**
- **Syslog:** Centralized log message collection and analysis
- **SNMP:** Network device event notifications
- **NetFlow:** Network traffic monitoring and analysis
- **Packet Captures:** Traffic analysis using tools like Wireshark

**Answers:**
- Insecure protocol: **FTP**
- Log protocol: **Syslog**

### Task 4: Hardening Virtual Private Networks

**OpenVPN Hardening Practices:**
- **Strong Encryption:** AES-128-CBC/AES-256-CBC cipher configuration
- **Software Updates:** Regular OpenVPN patching
- **Strong Authentication:** SHA256/SHA512 hashing algorithms
- **Default Settings:** Changing default credentials
- **Perfect Forward Secrecy (PFS):** Unique session keys with tls-crypt
- **Dedicated Users:** Restricted permissions for VPN operations

**Hands-on Configuration:**
- Configuration file: `/etc/openvpn/server/server.conf`
- Service management: `sudo systemctl restart openvpn-server@server.service`

**Answers:**
- Cipher update flag: `THM{CIPHER_UPDATED_1101}`
- Auth update flag: `THM{AUTH_UPDATED_123}`
- OpenVPN port: `1194`

### Task 5: Hardening Routers, Switches & Firewalls

**OpenWrt Router Hardening:**
- **Device Setup:** Proper hostname, timezone, and logging configuration
- **Credential Management:** Changing default admin passwords
- **Secure Protocols:** Enabling SSH with proper configuration
- **Startup Scripts:** Managing and monitoring execution scripts
- **Wi-Fi Security:** WPA2/WPA3 encryption, SSID management

**Web Interface Access:**
- URL: `10.10.229.108:8080`
- Credentials: `root`/`TryHackMe`

**Answers:**
- Default SSH port: `22`
- System notes flag: `THM{SYSTEM101}`
- Log buffer size: `64`
- uhttpd start priority: `50`

### Task 6: Advanced Hardening Techniques

**Traffic Management:**
- **Firewall Rules:** Accept/deny traffic based on source/destination
- **Traffic Monitoring:** Real-time upload/download statistics
- **Port Forwarding:** Controlled external access to internal services

**Scheduled Tasks & Updates:**
- **Cron Job Monitoring:** Regular review of scheduled tasks
- **Firmware Updates:** Regular security patches and updates

**Enterprise-Level Protections:**
- **Port Security:** MAC address limiting and unauthorized access detection
- **ARP Spoofing Prevention:** Static ARP tables and MAC filtering
- **Rogue DHCP Prevention:** Static DHCP binding and network mapping
- **IPv6 Implementation:** Built-in IPsec support for enhanced security

**Answers:**
- ICMP rule name: `Allow-Ping`
- Port forwarding rule: `THM_PORT`

### Task 7: Network Monitoring Tools

**Essential Monitoring Solutions:**
- **Nagios:** Open-source infrastructure monitoring with real-time alerts
- **SolarWinds NPM:** Comprehensive performance monitoring with network mapping
- **PRTG:** All-in-one monitoring with traffic analysis and custom dashboards
- **Zabbix:** Open-source performance monitoring with customizable alerts

**Answer:** `yea` (Network monitoring tools detect bandwidth bottlenecks)

## 🛡️ Key Security Takeaways

1. **Comprehensive Patching:** Regular updates for all network device firmware and software
2. **Access Control:** Strong authentication with MFA and principle of least privilege
3. **Protocol Security:** Enable secure protocols (SSH, HTTPS) and disable insecure ones (FTP, Telnet)
4. **Traffic Management:** Implement proper firewall rules and traffic monitoring
5. **Logging & Monitoring:** Centralized logging with real-time alerting capabilities
6. **Configuration Hardening:** Change defaults, secure management interfaces, disable unnecessary services

## 🔧 Technical Implementation Highlights

### VPN Security
- Configured strong encryption (AES-128-CBC/AES-256-CBC)
- Implemented secure hashing (SHA256/SHA512)
- Enabled Perfect Forward Secrecy for session security

### Router Hardening
- Changed default administrative credentials
- Configured secure remote access (SSH)
- Implemented proper logging and monitoring
- Managed startup scripts and scheduled tasks

### Network Protection
- Established firewall rules for traffic control
- Configured port forwarding with security considerations
- Implemented enterprise-level protections (port security, ARP spoofing prevention)

## 📈 Personal Reflection

This room provided excellent practical experience in network device security hardening across multiple platforms. The hands-on approach with OpenVPN and OpenWrt gave real-world configuration experience that's directly applicable to enterprise environments.

**Key Learnings:**
- The importance of changing default credentials cannot be overstated
- Proper protocol selection significantly reduces attack surface
- Regular monitoring and logging are crucial for threat detection
- Enterprise environments require layered security approaches

**Areas for Further Study:**
- Advanced firewall rule optimization
- Network segmentation strategies
- Automated monitoring and alerting systems
- Integration with SIEM solutions
- Zero Trust network architecture implementation

## 🎓 Recommendation

This room is highly valuable for:
- **Network Administrators** securing organizational infrastructure
- **Security Engineers** implementing network security controls
- **IT Professionals** managing network devices
- **Cybersecurity Students** learning practical network hardening

**Prerequisites:** Basic networking knowledge and understanding of OSI model are recommended before attempting this room.

---

*This writeup documents my learning journey through the TryHackMe Network Device Hardening room. The room provides essential, practical knowledge for securing network infrastructure against modern cyber threats.*
