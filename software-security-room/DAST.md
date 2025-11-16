# DAST (Dynamic Application Security Testing) - TryHackMe Room Writeup

![TryHackMe](https://img.shields.io/badge/TryHackMe-Room-success)
![DAST](https://img.shields.io/badge/DAST-Dynamic%20Analysis-blue)
![Difficulty](https://img.shields.io/badge/Difficulty-Intermediate-yellow)
![Time](https://img.shields.io/badge/Time-2%20hours-orange)
![Category](https://img.shields.io/badge/Category-Software%20Security-purple)

## 📋 Room Overview

**Room Title:** DAST (Dynamic Application Security Testing)  
**Platform:** TryHackMe  
**Category:** Software Security  
**Duration:** 120 minutes  
**Difficulty:** Intermediate  
**Completion Status:** 5% (Partial Completion)

## 🎯 Learning Objectives

- **DAST Fundamentals** and black-box testing approach
- **ZAP Proxy** tool usage and configuration
- **Spidering/Crawling** techniques for application mapping
- **Authenticated Scans** and session management
- **API Security Testing** with OpenAPI specifications
- **CI/CD Integration** for automated security testing

## 🔍 Core Concepts & Definitions

### Task 2: Dynamic Application Security Testing (DAST)

**DAST Definition:** Process of testing a running web application instance for vulnerabilities using black-box testing approach, simulating external attacker perspective.

**Manual vs Automated DAST:**

| Aspect | Manual DAST | Automated DAST |
|--------|-------------|----------------|
| **Approach** | Security engineer manual testing | Automated tool scanning |
| **Coverage** | Business logic, complex flows | Common vulnerabilities, quick scans |
| **Timing** | Periodic, comprehensive | Continuous, development phases |
| **Expertise** | High security knowledge required | Lower barrier to entry |

**DAST in SDLC:**
- **Automated DAST:** Test phases, quick feedback
- **Manual DAST:** Periodic comprehensive testing
- **Production:** Full web application penetration testing

**DAST Pros & Cons:**

**Pros:**
- Runtime vulnerability detection
- Language-agnostic testing
- Reduced false positives vs SAST
- Deployment-specific issue identification
- Business logic flaw detection

**Cons:**
- Limited code coverage
- Difficult application crawling
- No remediation guidance
- Long scan times
- Requires running application

**DAST Process:**
1. **Spidering/Crawling:** Application mapping and parameter identification
2. **Vulnerability Scanning:** Attack payload execution against identified targets

**Answers:**
- DAST replaces SAST/SCA: `Nay`
- Application mapping: `Spidering/Crawling`
- Code examination: `Nay`

### Task 3: Spiders and Crawlers

**Spidering Definition:** Automated process of navigating through web applications to map resources and identify attack surfaces.

**ZAP Spider Types:**

**Regular Spider:**
- HTML link parsing
- No JavaScript execution
- Fast but limited coverage

**AJAX Spider:**
- Real browser integration (Firefox/Chrome)
- JavaScript execution capability
- Comprehensive coverage
- **Headless browsers:** GUI-less browser instances

**Spidering Process:**
- Start from base URL
- Follow all discovered links recursively
- Build site structure map
- Identify parameters and forms

**Practical Implementation:**
- **Tools → Spider:** Regular spider configuration
- **Tools → AJAX Spider:** JavaScript-enabled spidering
- **Firefox integration:** Real browser for complex applications

**Answers:**
- GUI-less browsers: `Headless`
- login.php POST parameters: `pass, user`
- AJAX spider discovery: `/view.php`

### Task 4: Scanning for Vulnerabilities

**Scan Policy Configuration:** Customizing vulnerability tests based on application technology stack.

**Policy Parameters:**
- **Threshold:** False positive/negative balance
- **Strength:** Test intensity and coverage

**Application Technology Stack:**
- **OS:** Linux
- **Web Server:** Apache 2.4
- **Language:** PHP (no frameworks)
- **Database:** None

**Policy Optimization:**
- Disable irrelevant tests (SQL injection for non-database apps)
- Adjust thresholds based on risk tolerance
- Balance scan speed vs coverage

**Scan Execution:**
- **Tools → Active Scan**
- Select starting point and scope
- Apply customized scan policy
- Review results in Alerts tab

**False Positive Management:**
- Manual verification of findings
- "Mark as False Positive" option
- Continuous policy refinement

**Answers:**
- Disabled tests speed scans: `Yea`
- High-risk alerts: `Cross Site Scripting (Reflected)`

### Task 5: Authenticated Scans

**Authentication Challenges:**
- Restricted areas require valid sessions
- Manual login process recording
- Session maintenance during scans

**ZAP Authentication Process:**

**ZEST Scripts:**
- Record authentication sequences
- Reproduce login processes
- Handle session management

**Context Configuration:**
- Define URL groups with shared authentication
- Link ZEST scripts to contexts
- Configure user accounts

**Session Management:**
- **Logged-in Indicators:** Elements visible only when authenticated
- **Logged-out Indicators:** Elements visible when logged out
- **Verification Strategies:** Periodic session validation

**Authentication Workflow:**
1. Record login process with ZEST script
2. Create context for protected areas
3. Configure authentication script
4. Define session indicators
5. Run authenticated spidering and scanning

**Answers:**
- Authentication script type: `ZEST scripts`
- Authenticated scan finding: `Remote OS Command Injection`

### Task 6: Checking APIs with ZAP

**API Testing Challenges:**
- No spidering capability
- Endpoint discovery difficulty
- Parameter specification required

**API Documentation Standards:**
- **OpenAPI (Swagger):** REST API specification
- **SOAP:** XML-based web services
- **GraphQL:** Query language for APIs

**OpenAPI Import:**
- **Import → OpenAPI definition**
- URL or file-based import
- Automatic endpoint and parameter loading

**API Specification Example:**
```json
{
  "/asciiart/{art_id}": {
    "get": {
      "parameters": [
        {
          "name": "art_id",
          "in": "path",
          "type": "string",
          "required": true
        }
      ]
    }
  }
}
```

**API Scanning Process:**
1. Import API specification
2. Automatic passive scanning
3. Active scan against defined endpoints
4. Vulnerability analysis and reporting

**Answers:**
- /asciiart/generate vulnerability: `Remote OS Command Injection`
- Path traversal false positive: `yea`

### Task 7: CI/CD Integration

**Pipeline Integration Challenges:**
- Scan timing determination
- Trigger configuration
- Scan intensity balancing
- Development process impact

**CI/CD Components:**
- **Gitea:** Code repository (http://MACHINE_IP:3000/)
- **Jenkins:** CI/CD pipeline (http://MACHINE_IP:8080/)
- **Credentials:** thm/thm

**zap2docker:** Dockerized ZAP for automation

**Scan Types:**
- **Baseline Scan:** 1-minute spidering, no active scan
- **Full Scan:** Comprehensive spidering and active scanning
- **API Scan:** OpenAPI/GraphQL/SOAP specification testing

**Pipeline Integration:**
```docker
docker run -t owasp/zap2docker-stable zap-baseline.py -t https://www.example.com
```

**Jenkins Integration:**
- Add ZAP scan stage to Jenkinsfile
- Baseline scans for commit validation
- Report generation and analysis
- Build failure on vulnerability detection

**Answers:**
- simple-webapp medium vulnerabilities: `3`
- simple-api failed build: `4`
- API high-risk vulnerability: `Remote OS Command Injection`

## 🛠️ Technical Implementation

### ZAP Proxy Workflow
1. **Application Discovery:** Spidering/crawling to map attack surface
2. **Authentication Setup:** ZEST script recording and context configuration
3. **Scan Policy Configuration:** Technology-specific test optimization
4. **Vulnerability Scanning:** Active testing with customized payloads
5. **Results Analysis:** Manual verification and false positive management

### API Testing Methodology
1. **Specification Acquisition:** OpenAPI/Swagger documentation
2. **Endpoint Import:** Automated loading of API structure
3. **Parameter Analysis:** Input validation and attack vector identification
4. **Security Testing:** Comprehensive vulnerability assessment

### CI/CD Integration Strategy
- **Baseline Scans:** Quick validation on each commit
- **Scheduled Full Scans:** Comprehensive weekly/monthly testing
- **API Security:** Continuous API endpoint monitoring
- **Report Integration:** Automated vulnerability reporting

## 📈 Personal Reflection

This room provided comprehensive hands-on experience with Dynamic Application Security Testing, covering both manual techniques and automated tool integration.

**Key Technical Insights:**
- The importance of proper spidering configuration for comprehensive application coverage
- How ZEST scripts enable complex authentication scenario testing
- The critical role of scan policy customization in reducing false positives
- API testing challenges and OpenAPI specification utilization
- CI/CD integration strategies for continuous security validation

**Practical Learning Outcomes:**
- Hands-on ZAP Proxy configuration and usage
- Authentication workflow implementation for protected areas
- API security testing with specification files
- Jenkins pipeline integration for automated scanning
- Vulnerability analysis and false positive management

**Real-World Application:**
The skills gained directly apply to:
- Web application security assessment programs
- DevSecOps pipeline implementation
- API security testing methodologies
- Continuous security monitoring
- Vulnerability management processes

**Professional Development Value:**
This room is essential for:
- **Security Engineers** implementing DAST programs
- **DevOps Teams** integrating security into CI/CD
- **Application Developers** understanding security testing
- **Security Analysts** performing web application assessments
- **API Developers** ensuring interface security

**Areas for Further Development:**
- Advanced ZAP scripting and automation
- Complex authentication scenario handling
- API security testing beyond OpenAPI
- Performance optimization for large-scale applications
- Integration with other security testing tools

---

*This writeup documents my comprehensive learning journey through DAST principles and practical implementation, providing essential knowledge for integrating dynamic security testing into modern software development and deployment workflows.*
