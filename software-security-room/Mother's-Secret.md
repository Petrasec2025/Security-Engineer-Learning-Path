# TryHackMe - Mother's Secret Room Writeup

![TryHackMe](https://img.shields.io/badge/TryHackMe-Mother's%20Secret-red) 
![Category](https://img.shields.io/badge/Category-Web%20Exploitation-blue) 
![Level](https://img.shields.io/badge/Level-Intermediate-orange) 
![Time](https://img.shields.io/badge/Time-120%20min-green) 
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

## 📋 Table of Contents
- [Room Overview](#room-overview)
- [Prerequisites](#prerequisites)
- [Target Information](#target-information)
- [Task 1: Ready for Take Off](#task-1-ready-for-take-off)
- [Task 2: Mother's Secrets!](#task-2-mothers-secrets)
- [Methodology](#methodology)
- [Key Findings](#key-findings)
- [Self-Reflection](#self-reflection)
- [Important Notice](#important-notice)

## 🎯 Room Overview

**Mother's Secret** is a web exploitation challenge based on the Alien movie theme, where players must analyze a vulnerable web application (MU-TH-UR 6000) to uncover hidden secrets and flags through code analysis and exploitation.

**Room Details:**
- **Title:** Mother's Secret
- **Type:** Premium Room
- **Duration:** 120 minutes
- **Participants:** 15,265+
- **Theme:** Alien movie-inspired challenge

## 🎓 Prerequisites

- Completion of SAST and DAST rooms from DevSecOps path recommended
- Experience in code analysis and application security
- Understanding of web application vulnerabilities
- Basic knowledge of API exploitation

## 🖥️ Target Information

- **Machine:** TryHackMe Cargo Star Ship (THMCSS) Nostromo
- **System:** MU-TH-UR 6000 (Mother)
- **Initial Access:** Crew Member level (limited read access)
- **Objective:** Escalate privileges and uncover Mother's secrets

## 🚀 Task 1: Ready for Take Off

**Objective:** Set up the environment and access the target application.

**Steps:**
1. Start the AttackBox
2. Launch the Virtual Machine
3. Note the machine's IP address
4. Access the web application on port 80
5. Allow 3-4 minutes for VM to fully boot

**Answer:** 
```
No answer needed
```

## 🔐 Task 2: Mother's Secrets!

### Challenge Overview

This is a hands-on web exploitation challenge where you must:

1. **Analyze the downloaded source code** for vulnerabilities
2. **Explore available endpoints** to find clues
3. **Locate critical files** containing ship activity information
4. **Exploit vulnerable code** to access restricted resources
5. **Capture all hidden flags** throughout the exploration

### Operating Manual Clues

- Emergency command override: **100375**
- Specific route sequences can confuse Mother
- Science Officer role has elevated permissions
- Secret file location: `/api/nostromo/mother/secret.txt`

### Questions & Answers

**What is the number of the emergency command override?**
```
100375
```

**What is the special order number?**
```
937
```

**What is the hidden flag in the Nostromo route?**
```
Flag{X3n0M0Rph}
```

**What is the name of the Science Officer with permissions?**
```
Ash
```

**What are the contents of the classified "Flag" box?**
```
THM_FLAG{0RD3R_937}
```

**Where is Mother's secret?**
```
/opt/m0th3r
```

**What is Mother's secret?**
```
Flag{Ensure_return_of_organism_meow_meow!}
```

## 🔍 Methodology

### Approach Used
- **Code Analysis**: Thorough examination of the provided source code
- **Endpoint Enumeration**: Systematic exploration of API routes
- **Parameter Manipulation**: Testing various input vectors
- **Authentication Bypass**: Exploiting logical flaws in access control
- **Path Traversal**: Leveraging directory traversal vulnerabilities
- **Role Escalation**: Gaining Science Officer privileges

### Key Techniques
1. **Sequence-based Confusion**: Hitting routes in specific order to confuse authentication
2. **Emergency Override Utilization**: Using provided override codes
3. **File Path Discovery**: Locating hidden directories and files
4. **API Endpoint Exploitation**: Manipulating API parameters for unauthorized access

## 💡 Key Findings

### Security Vulnerabilities Identified
1. **Insecure Direct Object References (IDOR)**
2. **Authentication Bypass through Sequence Manipulation**
3. **Path Traversal Vulnerabilities**
4. **Insufficient Access Control**
5. **Hardcoded Credentials and Override Codes**

### Privilege Escalation Path
1. Initial Crew Member access → Sequence manipulation → Science Officer role → Full system access

### Critical Files Discovered
- Emergency override documentation
- Ship activity logs
- Classified flag containers
- Mother's secret directory

## 📝 Self-Reflection

This challenge provided excellent practice in:

**Code Analysis Skills:**
- Identifying vulnerabilities in web application code
- Understanding authentication and authorization mechanisms
- Recognizing insecure coding patterns

**Exploitation Techniques:**
- Methodical endpoint testing and enumeration
- Creative problem-solving with sequence-based attacks
- Combining multiple vulnerabilities for privilege escalation

**Web Application Security:**
- Real-world application of SAST principles
- Practical experience with API security testing
- Understanding of access control weaknesses

The Alien-themed scenario made the challenge engaging while maintaining realistic web application security concepts. The requirement to analyze code, understand application flow, and systematically exploit vulnerabilities mirrors real-world penetration testing methodologies.

## ⚠️ Important Notice

**Learning Through Doing:**  
This writeup documents the answers and general methodology, but the true learning experience comes from performing the actual exploitation yourself. The room is designed to teach practical web application security skills through hands-on exploration and problem-solving.

**Ethical Considerations:**  
The techniques demonstrated in this room are for educational purposes in a controlled environment. Always ensure you have proper authorization before testing any systems and follow responsible disclosure practices.

**Skill Development:**  
To maximize your learning, attempt the challenge without looking at the solutions first. The process of struggling with and eventually solving each step will build the practical skills needed for real-world security assessments.

---

**Tags:** `#TryHackMe` `#WebExploitation` `#CodeAnalysis` `#PrivilegeEscalation` `#APIsecurity` `#HandsOnChallenge`
