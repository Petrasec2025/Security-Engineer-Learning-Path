# Active Directory Hardening - TryHackMe Room Writeup

![TryHackMe](https://img.shields.io/badge/TryHackMe-Room-success)
![Active Directory](https://img.shields.io/badge/Active%20Directory-Hardening-blue)
![Difficulty](https://img.shields.io/badge/Difficulty-Intermediate-orange)
![Time](https://img.shields.io/badge/Time-4%20hours-purple)

## 📋 Room Overview

**Room Title:** Active Directory Hardening  
**Platform:** TryHackMe  
**Category:** Security Engineering / Network and System Security  
**Duration:** 240 minutes  
**Difficulty:** Intermediate  
**Completion Status:** 36% (Partial Completion)

## 🎯 Learning Objectives

This room focuses on essential Active Directory security concepts including:

- **Secure authentication methods**
- **Host security through group policies** 
- **Least Privilege model implementation**
- **Protection against known AD attacks**
- **Recovery planning for post-compromise scenarios**

## 🏗️ Core Concepts Covered

### Task 2: Understanding General Active Directory Concepts

**Key Learnings:**
- **Domain Structure:** Understanding domains as core logical units in AD
- **Domain Controllers:** Role as authentication/authorization gatekeepers
- **Trees & Forests:** Hierarchical organization and trust relationships
- **Trust Types:** Transitive vs. Non-transitive, One-way vs. Two-way
- **Containers & Leaves:** Object hierarchy in AD structure

**Answer:** `tryhackme.loc` (Root domain identification)

### Task 3: Securing Authentication Methods

**Security Implementations:**
- **LM Hash Disablement:** Preventing weak hash storage
- **SMB Signing:** Ensuring data integrity and MITM protection
- **LDAP Signing:** Securing directory access protocol
- **Password Policies:** Enforcing complexity and rotation requirements

**Configuration:** 
- Minimum password length: **7 characters**
- LM hash storage disabled via Group Policy

### Task 4: Implementing Least Privilege Model

**Principle Application:**
- **Account Type Segmentation:** User, Privilege, and Shared accounts
- **Role-Based Access Control:** Granular permission management
- **Tiered Access Model:** Tier 0 (Admin), Tier 1 (Servers), Tier 2 (End-users)
- **Regular Auditing:** Usage, privilege, and change audits

**Security Decisions:**
- Computers/Printers in Tier 0? **nay**
- High privilege for temporary vendor? **nay**

### Task 5: Microsoft Security Compliance Toolkit

**Tools Explored:**
- **Security Baselines:** Pre-configured GPO backups from Microsoft
- **Policy Analyser:** GPO comparison and conflict resolution
- **Official Sources:** Emphasis on downloading only from Microsoft

### Task 6: Protecting Against Known Attacks

**Attack Mitigations:**
- **Kerberoasting:** Offline password cracking prevention
- **Weak Passwords:** Strong password policy enforcement
- **RDP Brute Forcing:** Access control and monitoring
- **Public Shares:** Regular audit and access restriction

## 🔧 Technical Implementation

### Group Policy Management
Accessed through: `Server Manager > Tools > Group Policy Management`
- Configured security policies for authentication hardening
- Implemented password complexity requirements
- Enabled SMB and LDAP signing

### Security Baselines
- Downloaded official Microsoft security baselines
- Applied through PowerShell scripts
- Used Policy Analyser for GPO management

## 🛡️ Key Security Takeaways

1. **Authentication Security:** Disable LM hashes, enforce SMB/LDAP signing
2. **Password Policies:** Minimum 7+ characters with complexity requirements  
3. **Access Control:** Implement tiered model with least privilege principle
4. **Attack Prevention:** Protect against Kerberoasting, brute forcing, public shares
5. **Compliance:** Utilize Microsoft Security Compliance Toolkit for baseline security

## 📈 Personal Reflection

This room provided a solid foundation in Active Directory security fundamentals. The hands-on approach with Windows Server 2019 allowed practical implementation of security policies that are directly applicable to enterprise environments. The emphasis on Microsoft's official tools and baselines reinforces industry-standard practices.

**Areas for Further Study:**
- Advanced Group Policy configurations
- Automated monitoring and alerting for AD attacks
- Integration with SIEM solutions
- Disaster recovery planning for domain controllers

## 🎓 Recommendation

This room is excellent for:
- **System Administrators** looking to harden AD environments
- **Security Analysts** understanding AD attack vectors
- **Cybersecurity Students** learning enterprise security fundamentals

**Prerequisites:** Basic understanding of Active Directory concepts is recommended before attempting this room.

---

*This writeup documents my learning journey through the TryHackMe Active Directory Hardening room. The room provides essential knowledge for securing enterprise Windows environments against common attack vectors.*
