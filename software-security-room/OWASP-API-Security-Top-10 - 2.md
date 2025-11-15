# OWASP API Security Top 10 - Part 2 - TryHackMe Room Writeup

![TryHackMe](https://img.shields.io/badge/TryHackMe-Room-success)
![OWASP](https://img.shields.io/badge/OWASP-API%20Security%20Part%202-blue)
![Difficulty](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time](https://img.shields.io/badge/Time-3%20hours-orange)
![Category](https://img.shields.io/badge/Category-API%20Security-purple)

## 📋 Room Overview

**Room Title:** OWASP API Security Top 10 - Part 2  
**Platform:** TryHackMe  
**Category:** Software Security  
**Duration:** 180 minutes  
**Difficulty:** Intermediate  
**Completion Status:** 5% (Partial Completion)

## 🎯 Learning Objectives

- **Mass Assignment** vulnerabilities and prevention
- **Security Misconfiguration** identification and remediation
- **Injection** attack prevention in APIs
- **Improper Assets Management** risks
- **Insufficient Logging & Monitoring** implementation

## 🔐 Vulnerabilities Covered

### 6. **Mass Assignment**
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

**Vulnerability:** Automatic client-side data binding to server-side objects allowing unauthorized parameter manipulation.

**Practical Exercise:**
- Exploited signup endpoint: `/apirule6/user`
- Attempted credit value manipulation from default 50 to 1000
- Tested secure endpoint with server-side validation

**Key Findings:**
- Blind data insertion: `nay` (not recommended)
- Secure endpoint enforced default credit value: `50`
- Server-side filtering prevented parameter manipulation

**Mitigation Measures:**
- Framework-specific protection (Laravel fillable/guarded arrays)
- Input validation and allowlisting
- Avoid automatic data binding functions

### 7. **Security Misconfiguration**
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

**Vulnerability:** Poor security configurations exposing sensitive system information.

**Practical Exercise:**
- Analyzed server health endpoint: `/apirule7/ping_v`
- Identified stack trace information leakage
- Tested secure endpoint with proper error handling

**Key Findings:**
- Error logs exposure: `nay` (not recommended)
- Secure endpoint HTTP response code: `500`
- Error ID in response: `1401`
- Proper error handling prevents information disclosure

**Mitigation Measures:**
- Administrative interface access restrictions
- Default credential elimination
- Directory listing disablement
- Production debugging deactivation

### 8. **Injection**
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

**Vulnerability:** Unfiltered user input processed by API leading to unauthorized actions.

**Practical Exercise:**
- Exploited login endpoint with SQL injection: `/apirule8/user/login_v`
- Used payload: `' OR 1=1--'` for authentication bypass
- Tested secure endpoint with parameterized queries

**Key Findings:**
- Data extraction possible: `yea`
- Remote code execution possible: `yea`
- Invalid credential response code: `403`
- Framework built-in filters prevent injection

**Mitigation Measures:**
- Input validation libraries
- Parameterized queries implementation
- WAF security rules
- Framework-specific sanitization features

### 9. **Improper Assets Management**
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

**Vulnerability:** Unmaintained API versions exposing outdated endpoints with weaker security.

**Practical Exercise:**
- Accessed deprecated API version: `/apirule9/v1/user/login`
- Compared data exposure between v1 and v2
- Extracted sensitive user information from old endpoint

**Key Findings:**
- Single server hosting: `nay` (not recommended)
- Alice's balance: `100`
- Alice's country: `USA`
- Version segregation prevents data leakage

**Mitigation Measures:**
- Network-level blocking of deprecated APIs
- Environment segregation (R&D, QA, production)
- Comprehensive API documentation
- Automated documentation generation

### 10. **Insufficient Logging & Monitoring**
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

**Vulnerability:** Lack of comprehensive logging making attack detection and investigation difficult.

**Practical Exercise:**
- Tested logging endpoint: `/apirule10/logging`
- Analyzed metadata collection capabilities
- Verified logging implementation

**Key Findings:**
- Public log access: `nay` (not recommended)
- Successful logging response code: `200`
- Comprehensive logging enables threat detection

**Mitigation Measures:**
- SIEM system integration
- Failed authentication tracking
- Log integrity protection
- Custom alert implementation

## 🛠️ Security Principles Demonstrated

### Data Integrity & Validation
- **Mass Assignment:** Parameter manipulation prevention
- **Injection:** Input sanitization and validation
- **Assets Management:** Version control and deprecation

### System Hardening
- **Security Misconfiguration:** Proper error handling and configuration
- **Logging & Monitoring:** Comprehensive audit trail implementation

### Access Control
- **Assets Management:** Environment segregation
- **Logging:** Sensitive data protection

## 📊 Testing Methodology

### Tools Used
- **Talend API Tester:** Endpoint testing and manipulation
- **Chrome Browser:** Interface interaction
- **Laravel Framework:** Target application platform

### Testing Approach
- **Parameter Manipulation:** Mass assignment exploitation
- **Error Analysis:** Information leakage identification
- **Payload Injection:** SQL injection testing
- **Version Comparison:** Asset management assessment
- **Logging Verification:** Monitoring capability validation

## 📈 Personal Reflection

This room provided excellent practical experience with the remaining OWASP API Security Top 10 vulnerabilities, completing the comprehensive coverage of API security principles.

**Key Technical Insights:**
- The danger of mass assignment in modern frameworks and the importance of server-side validation
- How security misconfigurations can reveal critical system information through error messages
- The persistent threat of injection attacks and the effectiveness of framework-based prevention
- The risks associated with maintaining deprecated API versions with weaker security
- The critical role of logging and monitoring in incident response and threat detection

**Practical Learning Outcomes:**
- Hands-on experience with mass assignment vulnerability exploitation and prevention
- Understanding of proper error handling to prevent information disclosure
- Skills in testing and preventing injection attacks in API endpoints
- Knowledge of API version management and deprecation strategies
- Experience with logging implementation for security monitoring

**Real-World Application:**
The vulnerabilities covered in this part are particularly relevant in modern API-driven architectures where:
- Rapid development can lead to security oversights
- Multiple API versions coexist in production environments
- Comprehensive logging is essential for compliance and security
- Framework features can introduce security risks if misconfigured

**Areas for Further Development:**
- Advanced injection prevention techniques
- Automated API security testing tools
- SIEM integration strategies
- API gateway security configurations
- Microservices logging architecture

## 🎓 Professional Value

This room completes the essential knowledge for:
- **API Developers** building secure and maintainable interfaces
- **Security Engineers** implementing comprehensive API security controls
- **DevOps Teams** managing API versioning and deployment
- **Security Analysts** monitoring API security events
- **Compliance Officers** ensuring API security standards adherence

The combined knowledge from both parts provides a complete understanding of OWASP API Security Top 10, making it invaluable for professionals working with modern API-based architectures.

---

*This writeup documents my comprehensive learning journey through OWASP API Security Top 10 - Part 2, completing the essential knowledge of API security vulnerabilities and mitigation strategies for modern application development.*
