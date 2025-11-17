# TryHackMe - Traverse Room Writeup

![TryHackMe](https://img.shields.io/badge/TryHackMe-Traverse-red) 
![Category](https://img.shields.io/badge/Category-Web%20Security-blue) 
![Level](https://img.shields.io/badge/Level-Intermediate-orange) 
![Time](https://img.shields.io/badge/Time-120%20min-green) 
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

## 📋 Table of Contents
- [Room Overview](#room-overview)
- [Scenario](#scenario)
- [Task 1: Traverse](#task-1-traverse)
- [Investigation Findings](#investigation-findings)
- [Vulnerabilities Discovered](#vulnerabilities-discovered)
- [Attack Analysis](#attack-analysis)
- [Remediation Steps](#remediation-steps)
- [Self-Reflection](#self-reflection)
- [Important Notice](#important-notice)

## 🎯 Room Overview

**Traverse** is a web security challenge where you play as Bob, a security engineer investigating a compromised tourism web application that gets hacked daily after moving from QA to Production.

**Room Details:**
- **Title:** Traverse
- **Type:** Premium Room
- **Duration:** 120 minutes
- **Participants:** 10,932+
- **Scenario:** Real-world web application security investigation

## 🎭 Scenario

Bob, a security engineer, works with a DevOps team on a tourism web application. After moving from QA to Production, the website gets compromised daily. Despite consulting the blue team, the root cause remains unidentified. Bob turns to TryHackMe's Software Security pathway to enhance his skills and solve the mystery.

## 🔍 Task 1: Traverse

**Objective:** Investigate the compromised web application, identify vulnerabilities, and restore the website.

**Initial Setup:**
1. Start the machine
2. Access the website at `http://MACHINE_IP`
3. Analyze the compromised application
4. Identify attack vectors and restore functionality

## 🕵️ Investigation Findings

### Questions & Answers

**What type of encoding is used by the hackers to obfuscate the JavaScript file?**
```
HEX
```

**What is the flag value after deobfuscating the file?**
```
DIRECTORY LISTING IS THE ONLY WAY
```

**Logging is an important aspect. What is the name of the file containing email dumps?**
```
email_dump.txt
```

**The logs folder contains email logs and has a message for the software team lead. What is the name of the directory that Bob has created?**
```
planning
```

**What is the key file for opening the directory that Bob has created for Mark?**
```
THM{100100111}
```

**What is the email address for ID 5 using the leaked API endpoint?**
```
john@traverse.com
```

**What is the ID for the user with admin privileges?**
```
3
```

**What is the endpoint for logging in as the admin? Mention the last endpoint instead of the URL.**
```
/realadmin
```

**The attacker uploaded a web shell and renamed a file used for managing the server. Can you find the name of the web shell that the attacker has uploaded?**
```
thm_shell.php
```

**What is the name of the file renamed by the attacker for managing the web server?**
```
renamed_file_manager.php
```

**Can you use the file manager to restore the original website by removing the "FINALLY HACKED" message? What is the flag value after restoring the main website?**
```
[Flag value to be discovered during the challenge]
```

## 🔓 Vulnerabilities Discovered

### 1. **Information Disclosure**
- Directory listing enabled
- Exposed sensitive files and logs
- API endpoint leakage

### 2. **Authentication Bypass**
- Hidden admin endpoints (`/realadmin`)
- Weak access controls
- Predictable user IDs

### 3. **File Upload Vulnerabilities**
- Unrestricted file upload
- Web shell deployment (`thm_shell.php`)
- File manager manipulation

### 4. **Input Validation Issues**
- Lack of proper encoding validation
- Path traversal possibilities
- Insufficient input sanitization

### 5. **Security Misconfigurations**
- Exposed development files
- Debug information leakage
- Inadequate logging controls

## 🎯 Attack Analysis

### Attack Chain Reconstruction
1. **Reconnaissance**: Directory traversal and information gathering
2. **Obfuscation**: HEX encoding of malicious JavaScript
3. **Authentication Bypass**: Discovery of hidden admin endpoints
4. **Privilege Escalation**: Accessing admin functionality
5. **Persistence**: Uploading web shells and modifying file managers
6. **Defacement**: Replacing main website content

### Key Attack Vectors
- **Directory Traversal**: Access to restricted directories
- **API Endpoint Exploitation**: Unauthorized data access
- **File Upload Bypass**: Malicious file deployment
- **Admin Interface Access**: Hidden endpoint discovery

## 🛡️ Remediation Steps

### Immediate Actions
1. **Remove malicious files**
   - Delete `thm_shell.php`
   - Restore original file manager
   - Clean compromised content

2. **Secure authentication**
   - Change all credentials
   - Implement proper access controls
   - Remove
