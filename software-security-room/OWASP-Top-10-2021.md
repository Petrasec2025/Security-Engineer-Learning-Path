# OWASP Top 10 - 2021 - TryHackMe Room Writeup

![TryHackMe](https://img.shields.io/badge/TryHackMe-Room-success)
![OWASP](https://img.shields.io/badge/OWASP-Top%2010%202021-red)
![Difficulty](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time](https://img.shields.io/badge/Time-2%20hours-orange)
![Category](https://img.shields.io/badge/Category-Web%20Security-blue)

## 📋 Room Overview

**Room Title:** OWASP Top 10 - 2021  
**Platform:** TryHackMe  
**Category:** Software Security  
**Duration:** 120 minutes  
**Difficulty:** Intermediate  
**Completion Status:** 2% (Partial Completion)

## 🎯 Learning Objectives

This room provides comprehensive coverage of the OWASP Top 10 2021 vulnerabilities with practical exploitation exercises for each category.

## 🔓 Vulnerabilities Covered

### 1. **Broken Access Control (IDOR Challenge)**
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

**Vulnerability:** Insecure Direct Object Reference (IDOR) allows unauthorized access to resources by manipulating object identifiers.

**Practical Exercise:**
- Accessed application at `http://10.10.214.90`
- Logged in with credentials: `noot`/`test1234`
- Exploited IDOR to access other users' notes

**Flag Found:** `flag{fivefourthree}`

### 2. **Cryptographic Failures**
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

**Vulnerability:** Misuse or lack of cryptographic algorithms for protecting sensitive information.

**Practical Exercise:**
- Discovered sensitive directory: `/assets`
- Found database file: `webapp.db`
- Extracted admin password hash: `6eea9b7ef19179a06954edd0f6c05ceb`
- Cracked hash using Crackstation: `qwertyuiop`
- Logged in as admin

**Flag Found:** `THM{Yzc2YjdkMjE5N2VjMzNhOTE3NjdiMjdl}`

### 3. **Injection - Command Injection**
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

**Vulnerability:** User input passed directly to system commands without sanitization.

**Practical Exercise:**
- Exploited command injection via inline commands `$(command)`
- Discovered strange file: `drpepper.txt`
- Identified system information:
  - Non-root users: `0`
  - App running as: `apache`
  - User shell: `/sbin/nologin`
  - Alpine Linux version: `3.16.0`

### 4. **Insecure Design**
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

**Vulnerability:** Flaws inherent to application architecture rather than implementation.

**Practical Exercise:**
- Exploited password reset mechanism design flaw
- Reset Joseph's password through weak validation

**Flag Found:** `THM{Not_3ven_c4tz_c0uld_sav3_U!}`

### 5. **Security Misconfiguration**
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

**Vulnerability:** Poor security configurations exposing sensitive features.

**Practical Exercise:**
- Accessed Werkzeug debug console at `/console`
- Executed Python code to list files
- Found database: `todo.db`
- Read application source code from `app.py`

**Flag Found:** `THM{Just_a_tiny_misconfiguration}`

### 6. **Vulnerable and Outdated Components**
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

**Vulnerability:** Using software with known vulnerabilities.

**Practical Exercise:**
- Exploited Nostromo 1.9.6 RCE vulnerability (CVE-2019-16278)
- Used modified exploit script

**Flag Found:** `THM{But_1ts_n0t_my_f4ult!}`

### 7. **Identification and Authentication Failures**
![Status](https://img.shields.io/badge/Status-Partial-yellow)

**Vulnerability:** Weak authentication mechanisms allowing account compromise.

**Practical Exercise:**
- Exploited re-registration vulnerability using whitespace
- Accessed Darren's account with username " darren" (leading space)

**Flag Found:** `fe86079416a21a3c99937fea8874b667`

### 8. **Software and Data Integrity Failures**
![Status](https://img.shields.io/badge/Status-Partial-yellow)

**Vulnerability:** Lack of integrity verification for software and data.

**Practical Exercise:**
- Calculated jQuery SHA-256 hash: `sha256-ZosEbRLbNQzLpnKIkEdrPv7lOy9C27hHQ+Xp8a4MxAQ=`
- Explored JWT vulnerabilities
- Logged in as guest (password: `guest`)
- Identified JWT cookie: `jwt-session`

### 9. **Security Logging and Monitoring Failures**
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

**Vulnerability:** Inadequate logging and monitoring of security events.

**Practical Exercise:**
- Analyzed provided log file
- Identified attacker IP: `49.99.13.16`
- Detected attack type: `Brute Force`

### 10. **Server-Side Request Forgery (SSRF)**
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

**Vulnerability:** Coercing application to send requests to arbitrary destinations.

**Practical Exercise:**
- Discovered admin area restricted to: `localhost`
- Found server parameter pointing to: `secure-file-storage.com`
- Intercepted API key via SSRF

**Flag Found:** `THM{Hello_Im_just_an_API_key}`

## 🛠️ Technical Skills Demonstrated

### Web Application Testing
- **IDOR Exploitation:** Parameter manipulation for unauthorized access
- **Cryptographic Analysis:** Hash extraction and cracking
- **Command Injection:** System command execution via web inputs
- **Authentication Bypass:** Logic flaws and re-registration attacks

### Security Analysis
- **Vulnerability Research:** CVE identification and exploit adaptation
- **Log Analysis:** Security event identification and attack pattern recognition
- **Configuration Review:** Security misconfiguration identification

### Tool Usage
- **SQLite Analysis:** Database interrogation and sensitive data extraction
- **Hash Cracking:** Online tools for password recovery
- **JWT Manipulation:** Token analysis and modification

## 📈 Personal Reflection

This room provided excellent hands-on experience with real-world web application vulnerabilities. The practical approach of exploiting each OWASP Top 10 category reinforced theoretical knowledge with immediate application.

**Key Technical Insights:**
- The prevalence of IDOR vulnerabilities in applications with poor access control
- How cryptographic failures often stem from improper implementation rather than algorithm weaknesses
- The power of command injection for initial system access
- How design flaws can create vulnerabilities that are difficult to patch

**Practical Learning Outcomes:**
- Gained experience with multiple web application attack vectors
- Developed methodology for systematic vulnerability testing
- Improved skills in analyzing and exploiting different vulnerability types
- Enhanced understanding of web application security architecture

**Real-World Application:**
The vulnerabilities demonstrated in this room reflect common issues found in production applications. Understanding these attack vectors is crucial for both offensive security testing and defensive application development.

**Areas for Further Development:**
- Advanced JWT exploitation techniques
- Complex SSRF attack chains
- Automated vulnerability scanning integration
- Defense implementation strategies

## 🎓 Professional Value

This room is essential for:
- **Web Application Penetration Testers** understanding common vulnerability patterns
- **Developers** learning secure coding practices
- **Security Analysts** recognizing attack signatures
- **Bug Bounty Hunters** identifying lucrative vulnerability types

The comprehensive coverage of OWASP Top 10 2021 provides foundational knowledge that is directly applicable to real-world security assessments and application development.

---

*This writeup documents my practical learning journey through the OWASP Top 10 2021 room, demonstrating hands-on exploitation of critical web application vulnerabilities that form the basis of modern web security testing.*
