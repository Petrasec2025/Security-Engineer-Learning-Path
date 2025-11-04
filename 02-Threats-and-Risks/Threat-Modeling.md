# 🛡️ Threat Modelling - TryHackMe Room Summary

![TryHackMe](https://img.shields.io/badge/TryHackMe-Threat%20Modelling-red) ![Completion](https://img.shields.io/badge/Status-Completed-brightgreen) ![Level](https://img.shields.io/badge/Level-Premium-orange) ![Time](https://img.shields.io/badge/Duration-60%20min-blue)

## 🎯 Introduction
This premium room explores threat modelling frameworks to build cyber resiliency and emulation capabilities. It covers systematic approaches to identify, prioritize, and address potential security threats across organizational landscapes.

## 📚 Prerequisites
- Intro to Threat Emulation
- Principles of Security

---

## 🔍 Core Concepts

### Threat, Vulnerability & Risk

| Concept | Definition | Example |
|---------|------------|---------|
| **Threat** | Potential occurrence that may exploit vulnerabilities | Someone breaking into your home |
| **Vulnerability** | Weakness or flaw in a system | Broken locks or open windows |
| **Risk** | Possibility of compromise due to threat exploiting vulnerability | High crime rate neighborhood |

### High-Level Threat Modelling Process
1. **Defining the scope** - Systems, applications, and networks
2. **Asset Identification** - Architecture diagrams and dependencies
3. **Identify Threats** - Cyber attacks, social engineering, insider threats
4. **Analyze Vulnerabilities & Prioritize Risks** - Impact assessment
5. **Develop Countermeasures** - Security controls implementation
6. **Monitor and Evaluate** - Continuous testing and validation

### Collaborative Teams
- **Security Team** - Leads threat modelling process
- **Development Team** - Builds secure systems
- **IT & Operations** - Manages infrastructure
- **GRC Team** - Compliance and risk management
- **Business Stakeholders** - Strategic alignment
- **End Users** - User perspective insights

---

## 🎯 Threat Modelling Frameworks

### 1. MITRE ATT&CK Framework
**Purpose**: Comprehensive knowledge base of adversary behavior

**Key Features**:
- Tactics (high-level objectives)
- Techniques (methods to achieve goals)
- Procedure examples, mitigations, detection strategies

**Example Technique**: `T1190 - Exploit Public-Facing Application`

**ATT&CK Navigator Usage**:
- Create custom matrices
- Search and select techniques
- Annotate with scores and comments
- Filter by platforms and threat groups

### 2. DREAD Framework
**Qualitative Risk Assessment Model**:

| Component | Assessment Question |
|-----------|---------------------|
| **Damage** | How bad would an attack be? |
| **Reproducibility** | How easy to reproduce? |
| **Exploitability** | How much work to launch? |
| **Affected Users** | How many people impacted? |
| **Discoverability** | How easy to find vulnerability? |

**Scoring**: 1-10 scale with overall average calculation

### 3. STRIDE Framework
**Categories & Policy Violations**:

| Category | Policy Violated | Examples |
|----------|-----------------|----------|
| **Spoofing** | Authentication | Email spoofing, phishing sites |
| **Tampering** | Integrity | Unauthorized modifications |
| **Repudiation** | Non-repudiation | Denying transactions |
| **Information Disclosure** | Confidentiality | Data breaches |
| **Denial of Service** | Availability | Resource exhaustion |
| **Elevation of Privilege** | Authorization | Privilege escalation |

### 4. PASTA Framework
**7-Step Risk-Centric Methodology**:

1. **Define Objectives** - Scope and security objectives
2. **Define Technical Scope** - Asset inventory
3. **Decompose Application** - Component breakdown
4. **Analyze Threats** - Threat identification
5. **Vulnerability Analysis** - Weakness assessment
6. **Analyze Attacks** - Scenario simulation
7. **Risk & Impact Analysis** - Countermeasure development

---

## 🛠️ Practical Applications & Case Studies

### MITRE ATT&CK Navigator
- **Enterprise Matrix**: Network-based threats
- **Mobile Matrix**: Mobile device threats
- **ICS Matrix**: Industrial control systems
- **Features**: Filtering, scoring, commenting, exporting

### Attack Trees
- Hierarchical representation of attack scenarios
- Root node = attacker's primary goal
- Child nodes = strategies and techniques
- Attack paths = vulnerability chains

---

## 🎯 STRIDE Framework - Complete Case Study Exercise

### Scenario: E-commerce Payment Processing System
**Objective**: Conduct threat modelling for a new payment processing system using STRIDE framework.

**Teams Involved**:
- **Development Team** - Application security
- **System Architecture Team** - Cloud infrastructure design
- **Security Team** - Threat expertise and risk mitigation
- **Business Stakeholders** - Strategic alignment
- **Network Infrastructure Team** - Network security

**Complete STRIDE Analysis Results**:

| Threat Scenario | STRIDE Components | Risk Level | Mitigation Strategies |
|-----------------|-------------------|------------|---------------------|
| **Email Spoofing Attacks** | Spoofing, Repudiation | High | DMARC, DKIM, SPF implementation |
| **DDoS on Payment Gateway** | Denial of Service | Critical | WAF, Load balancers, CDN |
| **SQL Injection in Payment Form** | Tampering, Information Disclosure | High | Parameterized queries, Input validation |
| **Cloud Storage Misconfiguration** | Information Disclosure | Medium | Regular S3 bucket audits, Access controls |
| **Privilege Escalation in Admin Panel** | Elevation of Privilege | High | RBAC, Regular privilege reviews |
| **Transaction Repudiation** | Repudiation | Medium | Comprehensive logging, Digital signatures |
| **Man-in-the-Middle Attacks** | Tampering, Information Disclosure | High | TLS/SSL encryption, Certificate pinning |

**STRIDE Exercise Screenshots**:

![STRIDE Case Scenario 1](https://github.com/user-attachments/assets/d30ab29b-baf4-4407-9f2e-c275e80fde03)
*STRIDE framework introduction and overview*

![STRIDE Case Scenario 2](https://github.com/user-attachments/assets/605cde82-fc8d-4847-8b36-dd03a17e1c62)
*Team collaboration and roles in STRIDE exercise*

![STRIDE Case Scenario 3](https://github.com/user-attachments/assets/efb9d465-4dc3-407b-bf84-d9245d457576)
*STRIDE threat categorization process*

![STRIDE Case Scenario 4](https://github.com/user-attachments/assets/a426b130-c20e-4e03-984c-c8caed9220dd)
*Spoofing threats identification*

![STRIDE Case Scenario 5](https://github.com/user-attachments/assets/bafe0162-3522-4f92-bbc7-b88ec771eb6e)
*Tampering threats analysis*

![STRIDE Case Scenario 6](https://github.com/user-attachments/assets/fc0ebd06-e620-4d75-b846-394b26803d36)
*Information disclosure threats*

![STRIDE Case Scenario 7](https://github.com/user-attachments/assets/090ae56f-dcd3-439a-9199-81a84e0eea8c)
*Denial of service and elevation of privilege threats*

![STRIDE Case Scenario 8](https://github.com/user-attachments/assets/c9cb8592-87ba-4ed7-899e-e7eb26aa65e5)
*STRIDE exercise completion and flag*

**Flag Obtained**: `THM{m0d3ll1ng_w1th_STR1D3}`

---

## 🎯 PASTA Framework - Complete Case Study Exercise

### Scenario: Online Banking Platform
**Objective**: Conduct risk-centric threat modelling for Asia Pacific online banking platform using PASTA framework.

**Teams Involved**:
- **Development Team** - Secure application development
- **System Architecture Team** - Cloud services architecture
- **Security Team** - Threat and vulnerability expertise
- **Business Stakeholder Team** - Critical asset identification

**Complete PASTA 7-Step Process Application**:

### Step 1: Define Objectives
**Business Objectives**:
- Secure online banking transactions for 1M+ customers
- Maintain PCI DSS compliance
- Protect customer financial data
- Ensure 99.9% system availability
- Comply with regional financial regulations

**Security Objectives**:
- Prevent unauthorized access to accounts
- Protect transaction integrity
- Ensure data confidentiality
- Maintain audit trails for compliance

### Step 2: Define Technical Scope
**Asset Inventory**:
- Web application servers (Apache/Tomcat)
- Oracle database systems with financial data
- OAuth 2.0 authentication services
- REST API endpoints for mobile banking
- Payment gateway integrations
- Customer relationship management (CRM) system
- Audit and logging systems

**System Architecture**:
- Multi-tier architecture: Web → Application → Database
- Load-balanced web servers
- Geographically distributed databases
- CDN for static content delivery
- VPN for administrative access

### Step 3: Decompose Application
**Application Components**:
- **Login Module** - Authentication and session management
- **Transaction Processing** - Fund transfers, bill payments
- **Account Management** - Profile updates, preferences
- **Reporting Systems** - Statements, transaction history
- **Admin Console** - User management, system monitoring

**Data Flows**:
- Customer → Web Server → Auth Service → Database
- Mobile App → API Gateway → Microservices → Database
- Payment Gateway → Transaction Processor → Database

**Trust Boundaries**:
- Internet to DMZ (web servers)
- DMZ to internal network (application servers)
- Internal network to database layer
- Third-party integrations to internal systems

### Step 4: Analyze Threats
**Identified Threats**:
- Credential stuffing attacks
- Man-in-the-middle attacks
- SQL injection vulnerabilities
- Cross-site scripting (XSS) attacks
- Session hijacking
- Insider threats from employees
- Third-party vendor risks
- DDoS attacks on banking portal

**Threat Sources**:
- Organized cybercrime groups
- Nation-state actors
- Hacktivists
- Malicious insiders
- Script kiddies

### Step 5: Vulnerability Analysis
**Technical Vulnerabilities**:
- Unpatched Apache Struts vulnerabilities
- Weak password policies
- Insufficient input validation
- Insecure direct object references
- Missing security headers
- Improper error handling revealing system information

**Process Vulnerabilities**:
- Inadequate security training
- Weak change management processes
- Insufficient monitoring and alerting
- Lack of incident response testing

**Human Vulnerabilities**:
- Social engineering susceptibility
- Password reuse across systems
- BYOD security risks

### Step 6: Analyze Attacks
**Attack Scenarios Simulated**:

**Scenario 1: Account Takeover**
- Attacker uses credential stuffing tools
- Gains access to customer account
- Performs unauthorized transactions
- **Impact**: Financial loss, reputational damage

**Scenario 2: Database Breach**
- SQL injection through search functionality
- Exfiltration of customer PII and financial data
- **Impact**: Regulatory fines, customer trust loss

**Scenario 3: DDoS Attack**
- Botnet targets banking portal during peak hours
- Service unavailable for legitimate customers
- **Impact**: Revenue loss, customer dissatisfaction

**Scenario 4: Insider Threat**
- Disgruntled employee exports customer data
- Sells information to competitors
- **Impact**: Intellectual property theft, legal consequences

### Step 7: Risk and Impact Analysis
**Risk Prioritization Matrix**:

| Risk | Likelihood | Impact | Priority |
|------|------------|--------|----------|
| **Credential Stuffing** | High | High | Critical |
| **SQL Injection** | Medium | High | High |
| **DDoS Attacks** | High | Medium | High |
| **Insider Threats** | Low | High | Medium |
| **XSS Attacks** | Medium | Medium | Medium |

**PASTA Exercise Screenshots**:

![PASTA Case Scenario 1](https://github.com/user-attachments/assets/9c6fd2ca-418b-4223-8337-f2e25431d106)
*PASTA framework introduction and 7-step methodology*

![PASTA Case Scenario 2](https://github.com/user-attachments/assets/c74b181d-0256-4fd9-82cb-a9a63fb63985)
*Step 1: Define Objectives*

![PASTA Case Scenario 3](https://github.com/user-attachments/assets/f151e149-729e-475f-9d83-de37daca00a7)
*Step 2: Define Technical Scope*

![PASTA Case Scenario 4](https://github.com/user-attachments/assets/8f78575e-dfa2-4573-a1c9-ac89d3570f99)
*Step 3: Decompose Application*

![PASTA Case Scenario 5](https://github.com/user-attachments/assets/b42731b4-c008-4e36-a88e-deff7209a184)
*Step 4: Analyze Threats*

![PASTA Case Scenario 6](https://github.com/user-attachments/assets/e5496861-adf8-44ec-a56a-34eeda77e77c)
*Step 5: Vulnerability Analysis*

![PASTA Case Scenario 7](https://github.com/user-attachments/assets/7387ab1c-ba6c-43dc-ac60-a689b15ef960)
*Step 6: Analyze Attacks*

![PASTA Case Scenario 8](https://github.com/user-attachments/assets/fc157d30-fde9-4bac-bdaf-5c32778c53a6)
*Step 7: Risk and Impact Analysis*

![PASTA Case Scenario 9](https://github.com/user-attachments/assets/622b15cb-744b-4fe2-8bc9-20d1cb77fdfc)
*PASTA exercise completion and flag*

![PASTA Case Scenario 10](https://github.com/user-attachments/assets/a8e6153a-12e0-4d2c-857a-04b239493e58)
*PASTA framework team collaboration*

**Countermeasures Implemented**:
- Web Application Firewall (WAF) with bot detection
- Multi-factor authentication for all users
- Regular vulnerability scanning and penetration testing
- Employee security awareness training
- Incident response team with 24/7 monitoring
- Data encryption at rest and in transit
- Regular security audits and compliance checks

**Flag Obtained**: `THM{c00k1ng_thr34ts_w_P4ST4}`

---

## ✅ Room Answers

| Task | Question | Answer |
|------|----------|--------|
| 2 | Weakness or flaw in a system | `vulnerability` |
| 2 | Process of developing architecture diagrams | `Asset Identification` |
| 2 | Diagram for potential threat analysis | `Attack Tree` |
| 3 | Technique ID of Exploit Public-Facing Application | `T1190` |
| 3 | Tactic for T1190 | `Initial Access` |
| 4 | Techniques attributed to APT33 | `31` |
| 4 | Discovery techniques under IaaS filter | `13` |
| 5 | Component assessing potential harm | `Damage` |
| 5 | Component for vulnerability discovery ease | `Discoverability` |
| 5 | Component for impacted users | `Affected Users` |
| 6 | Foundational STRIDE concept | `CIA Triad` |
| 6 | Policy violated by Information Disclosure | `Confidentiality` |
| 6 | Unauthorized data modification | `Tampering` |
| 6 | System availability disruption | `Denial of Service` |
| 6 | STRIDE exercise flag | `THM{m0d3ll1ng_w1th_STR1D3}` |
| 7 | System component breakdown step | `Decompose the Application` |
| 7 | Attack scenario simulation step | `Analyse the Attacks` |
| 7 | Asset inventory creation step | `Define the Technical Scope` |
| 7 | PASTA exercise flag | `THM{c00k1ng_thr34ts_w_P4ST4}` |

---

## 🎯 Framework Comparison

| Framework | Primary Use Case | Strengths |
|-----------|------------------|-----------|
| **MITRE ATT&CK** | Adversary behavior mapping | Practical, hands-on approach |
| **DREAD** | Qualitative risk assessment | Numerical prioritization |
| **STRIDE** | Software system analysis | Systematic threat categorization |
| **PASTA** | Business-aligned modelling | Holistic, risk-centric approach |

---

## 🧭 Personal Reflection

This room provided an excellent comprehensive overview of threat modelling methodologies. The hands-on experience with MITRE ATT&CK Navigator was particularly valuable for understanding how to map real-world adversary techniques. The framework comparisons helped clarify when to use each approach based on organizational needs.

**Key Takeaways**:
- Threat modelling is essential for proactive security
- Different frameworks serve different purposes
- Collaboration across teams is crucial
- Continuous monitoring and adaptation are necessary
- Practical tools like ATT&CK Navigator enhance threat intelligence capabilities

The case studies for STRIDE and PASTA provided realistic scenarios that demonstrated how these frameworks can be applied in real-world situations. The STRIDE exercise with the e-commerce payment system showed how to systematically categorize threats, while the PASTA exercise with the banking platform demonstrated a comprehensive risk-centric approach.

The room effectively balanced theoretical concepts with practical exercises, making complex topics accessible and applicable to real-world scenarios.

---

### 🔗 TryHackMe Badge
[![TryHackMe](https://tryhackme-badges.s3.amazonaws.com/Petras20.png)](https://tryhackme.com/p/Petras20)

**Room Link**: [Threat Modelling](https://tryhackme.com/room/threatmodelling)  
**Completed by**: [Petras20](https://tryhackme.com/p/Petras20)  
**Room Type**: Premium  
**Completion Date**: 2024

---

*This comprehensive summary demonstrates the practical application of threat modelling frameworks to enhance organizational security posture and build cyber resilience against evolving threats.*
