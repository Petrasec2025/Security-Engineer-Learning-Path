# OWASP API Security Top 10 - Part 1 - TryHackMe Room Writeup

![TryHackMe](https://img.shields.io/badge/TryHackMe-Room-success)
![OWASP](https://img.shields.io/badge/OWASP-API%20Security-blue)
![Difficulty](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time](https://img.shields.io/badge/Time-3%20hours-orange)
![Category](https://img.shields.io/badge/Category-API%20Security-purple)

## 📋 Room Overview

**Room Title:** OWASP API Security Top 10 - Part 1  
**Platform:** TryHackMe  
**Category:** Software Security  
**Duration:** 180 minutes  
**Difficulty:** Intermediate  
**Completion Status:** 5% (Partial Completion)

## 🎯 Learning Objectives

- **Broken Object Level Authorisation (BOLA)** principles and exploitation
- **Broken User Authentication (BUA)** mechanisms and bypass techniques
- **Excessive Data Exposure** identification and prevention
- **Lack of Resources & Rate Limiting** vulnerabilities
- **Broken Function Level Authorisation** exploitation

## 🔐 Vulnerabilities Covered

### 1. **Broken Object Level Authorisation (BOLA)**
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

**Vulnerability:** Insecure Direct Object Reference (IDOR) allowing unauthorized access to resources through object identifier manipulation.

**Practical Exercise:**
- Exploited vulnerable endpoint: `/apirule1/users/{ID}`
- Identified total employees: `3`
- Extracted employee information through ID enumeration

**Key Findings:**
- Employee ID 2 flag: `THM{838123}`
- Employee ID 3 username: `Bob`

**Mitigation Measures:**
- Implement proper authorization mechanisms
- Use random, unpredictable tokens
- Enforce user policy-based access controls

### 2. **Broken User Authentication (BUA)**
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

**Vulnerability:** Weak authentication implementation allowing account takeover through credential bypass.

**Practical Exercise:**
- Exploited login endpoint using only email validation
- Extracted authentication tokens without password verification
- HR token: `cOC%Aonyis%H)mZ&uJkuI?_W#4&m>Y`
- Identified user geographical information

**Key Findings:**
- sales@mht.com country: `China`
- Authentication bypass through incomplete validation

**Mitigation Measures:**
- Strong password policies
- Avoid credential exposure in requests
- Implement MFA and account lockout mechanisms
- Secure password storage

### 3. **Excessive Data Exposure**
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

**Vulnerability:** API endpoints revealing more information than necessary in responses.

**Practical Exercise:**
- Analyzed comment API endpoints
- Identified excessive data in responses
- Extracted device information and user details

**Key Findings:**
- Post ID 2 device ID: `iOS15.411`
- Post ID 3 username: `hacker#!`
- Sensitive data exposed beyond required fields

**Mitigation Measures:**
- Programmatic data filtration at API level
- Avoid generic serialization methods
- Regular API response reviews
- Comprehensive testing for data leaks

### 4. **Lack of Resources & Rate Limiting**
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

**Vulnerability:** Absence of request limitations leading to resource exhaustion and potential DoS attacks.

**Practical Exercise:**
- Tested OTP sending endpoints
- Identified absence of rate limiting
- Verified secure implementation with restrictions

**Key Findings:**
- Rate limiting possible at network level: `yea`
- Secure endpoint response code: `200`
- Invalid email response: `Invalid Email`

**Mitigation Measures:**
- CAPTCHA implementation for bot prevention
- Request frequency limitations
- Payload size restrictions
- Resource usage monitoring

### 5. **Broken Function Level Authorisation**
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

**Vulnerability:** Privilege escalation through authorization header manipulation.

**Practical Exercise:**
- Exploited admin dashboard endpoints
- Used `isAdmin` header manipulation
- HR user Alice's token: `YWxpY2U6dGVzdCFAISM6Nzg5Nzg=`

**Key Findings:**
- Alice's mobile number: `+1235322323`
- Admin address flag: `THM{3432$@#2!}`
- Privilege escalation through header modification

**Mitigation Measures:**
- Deny-by-default authorization approach
- Role-based access control validation
- Regular authorization logic reviews
- Business logic security testing

## 🛠️ Tools & Techniques Used

### Testing Environment
- **Talend API Tester:** API endpoint testing and debugging
- **Chrome Browser:** Interface interaction and testing
- **Laravel-based Web Application:** Target application platform

### Testing Methodology
- **Endpoint Analysis:** Identifying vulnerable API paths
- **Parameter Manipulation:** Object ID and header modification
- **Response Inspection:** Data exposure analysis
- **Rate Limiting Testing:** Request frequency validation

## 📊 Security Principles Demonstrated

### Authorization & Authentication
- **BOLA:** Object-level access control failures
- **BUA:** Authentication mechanism weaknesses
- **BFLA:** Function-level privilege escalation

### Data Protection
- **Excessive Data Exposure:** Information disclosure risks
- **Input Validation:** Parameter manipulation prevention

### Availability & Performance
- **Rate Limiting:** Resource protection mechanisms
- **DoS Prevention:** Service availability maintenance

## 📈 Personal Reflection

This room provided excellent practical experience with API security vulnerabilities, particularly focusing on authorization and authentication flaws that are common in real-world applications.

**Key Technical Insights:**
- The prevalence of IDOR vulnerabilities in API endpoints with predictable object identifiers
- How authentication bypass can occur through incomplete validation logic
- The importance of implementing data filtration at the API level rather than relying on front-end filtering
- How rate limiting is crucial for preventing resource exhaustion attacks
- The dangers of privilege escalation through simple header manipulation

**Practical Learning Outcomes:**
- Hands-on experience with API security testing methodologies
- Understanding of common authorization bypass techniques
- Skills in identifying excessive data exposure in API responses
- Knowledge of rate limiting implementation strategies
- Experience with privilege escalation detection and prevention

**Real-World Application:**
The vulnerabilities demonstrated reflect common issues found in production APIs. Understanding these attack vectors is essential for both API developers and security testers to build and assess secure API implementations.

**Areas for Further Development:**
- Advanced JWT token manipulation techniques
- Complex authorization logic testing
- Automated API security scanning tools
- API gateway security configurations
- Microservices security architecture

## 🎓 Professional Value

This room is essential for:
- **API Developers** building secure application interfaces
- **Security Testers** assessing API security posture
- **DevSecOps Engineers** implementing API security in CI/CD pipelines
- **Application Architects** designing secure API frameworks

The comprehensive coverage of OWASP API Security Top 10 principles provides foundational knowledge that is directly applicable to modern API development and security assessment practices.

---

*This writeup documents my practical learning journey through OWASP API Security Top 10 - Part 1, demonstrating hands-on exploitation of critical API vulnerabilities and understanding of essential security mitigation measures for modern API development.*
