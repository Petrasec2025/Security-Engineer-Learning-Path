# Intro to Cloud Security - TryHackMe Room Writeup

![TryHackMe](https://img.shields.io/badge/TryHackMe-Room-success)
![Cloud Security](https://img.shields.io/badge/Cloud-Security-blue)
![Difficulty](https://img.shields.io/badge/Difficulty-Intermediate-orange)
![Time](https://img.shields.io/badge/Time-3%20hours-purple)
![Category](https://img.shields.io/badge/Category-Security%20Engineering-green)

## 📋 Room Overview

**Room Title:** Intro to Cloud Security  
**Platform:** TryHackMe  
**Category:** Security Engineering / Network and System Security  
**Duration:** 180 minutes  
**Difficulty:** Intermediate  
**Completion Status:** 0% (Partial Completion)

## 🎯 Learning Objectives

- **Cloud security models** and architectural concepts
- **Security through policies & procedures**
- **Identity & access management** in cloud environments
- **Networking security** management
- **Storage security** and data protection
- **Additional concepts** like disaster recovery and monitoring

## ☁️ Core Cloud Concepts & Definitions

### Task 2: Architectural Concepts of Cloud

**Cloud Computing Definition:** Delivery of computing services over the internet with pay-as-you-go pricing and on-demand access.

**Key Characteristics:**
- **Scalability:** Resources scale up/down based on business needs
- **Simplicity:** User-friendly design and interfaces
- **Cost Effective:** No upfront hardware investment
- **Enhanced Automation:** Limited human administration required

**Cloud Service Models:**
- **IaaS (Infrastructure as a Service):** Provider manages hardware, customer manages OS/software
- **PaaS (Platform as a Service):** Provider manages hardware + platform, customer manages applications
- **SaaS (Software as a Service):** Provider manages everything, customer only uses software
  <img width="1331" height="643" alt="Screenshot 2025-11-12 at 11 56 17 PM" src="https://github.com/user-attachments/assets/db63cc85-386b-456d-9169-aa9f9db25135" />


**Cloud Deployment Models:**
- **Public Cloud:** Shared resources among multiple customers (AWS, Azure)
- **Private Cloud:** Dedicated resources for single customer
- **Hybrid Cloud:** Combination of public and private clouds

**Essential Terminologies:**
- **Virtualization:** Technology enabling resource sharing among multiple users
- **Compute:** Processing power for running applications
- **Storage:** Logical pools of physical storage in cloud
- **Networking:** High-speed connectivity between cloud resources

**Answers:**
- IaaS vendor deployment: `Hardware`
- Single-customer cloud: `Private Cloud`

### Task 3: Cloud Security Concepts

**Data Classification:**
- **Confidential Data:** Highly sensitive, potential damage if exposed
- **Internal Data:** Moderate risk if exposed
- **Public Data:** No consequences if exposed
  <img width="740" height="580" alt="Screenshot 2025-11-13 at 12 03 24 AM" src="https://github.com/user-attachments/assets/c26dfb8c-d7b4-47e6-937b-76a114475ae2" />

**Cloud Data Lifecycle Security:**
1. **Create/Update Phase:**
   - SSL/TLS implementation for secure communication
   - Data encryption for confidentiality
   - Secure connection paths

2. **Store Phase:**
   - Encryption at rest
   - Regular backups
   - Secure storage containers

3. **Use Phase:**
   - Secure authentication mechanisms
   - Restricted permissions
   - Secure virtualization isolation

4. **Share Phase:**
   - Jurisdictional compliance
   - Data Loss Prevention (DLP) implementation

5. **Archive Phase:**
   - Long-term encryption
   - Physical security measures
   - Environmental risk considerations

6. **Destroy Phase:**
   - Secure data destruction
   - Crypto shredding (destroy encryption keys)

**Major Security Issues & Solutions:**
- **Data Confidentiality:** Encryption and access controls
- **Virtualization Issues:** VM isolation mechanisms
- **Insecure APIs:** Secure interface development
- **Malicious Insiders:** Monitoring and least privilege
- **Account Hijacking:** Multi-factor authentication
- **Access Control:** Robust ACM implementation

**Answers:**
<img width="1440" height="780" alt="Screenshot 2025-11-13 at 12 10 48 AM" src="https://github.com/user-attachments/assets/72e1b8b6-d06c-4195-a42d-72d76136dc78" />
<img width="692" height="725" alt="Screenshot 2025-11-13 at 12 12 07 AM" src="https://github.com/user-attachments/assets/7c619d59-40a8-42b0-9e98-e8f5f5ef46d8" />
<img width="1440" height="777" alt="Screenshot 2025-11-13 at 12 12 21 AM" src="https://github.com/user-attachments/assets/4901238a-a025-4238-9b88-8554eb9b2a54" />


- First lifecycle phase: `Create`
- Interactive flag: `THM{CLOUD_DATA_LIFECYCLE}`

### Task 4: Cloud Security Risks by Deployment Model
<img width="537" height="260" alt="Screenshot 2025-11-13 at 12 12 59 AM" src="https://github.com/user-attachments/assets/7a7ab713-5256-42d7-aed5-ace2afa39c76" />


**Private Cloud Risks:**
- **Personnel Threats:** Insider risks from provider staff
- **Natural Disasters:** Physical location vulnerabilities
- **External Attacks:** DDoS, MITM attacks

**Public Cloud Risks:**
- **Vendor Lock-In:** Difficulty migrating data
- **Threat of New Entrants:** Competitor access
- **Privilege Escalation:** Unauthorized permission acquisition

**Community Cloud Risks:**
- **Vulnerability Propagation:** Shared infrastructure risks
- **Policy Enforcement:** Administrative challenges

**Answers:**
- Vendor lock-in model: `Public`
- Policy enforcement challenge: `yea`

## 🔐 Security Implementation Frameworks

### Task 5: Security Through Access Management

**Access Management Definition:** Ensuring right people have right permissions for right jobs.

**Key Components:**
- **Identities:** Digital representations of users/services
- **Authentication Factors:** Unique characteristics (passwords, biometrics, certificates)
- **Roles:** Defined permission domains
<img width="881" height="360" alt="Screenshot 2025-11-13 at 12 17 29 AM" src="https://github.com/user-attachments/assets/a5deb286-b4d7-42df-9245-bfbd563437e9" />

**AWS IAM (Identity and Access Management):**
- Granular access control to AWS resources
- Role-based access without password sharing
- Multi-factor authentication support
- Cross-account permission management

**IAM Terminology:**
- **Resources:** Objects within services (users, roles, policies)
- **Identities:** Authorized users with specific roles
- **Entities:** Authentication resources (users, roles)
- **Principals:** Persons/applications requesting resource access

**Answers:**
- Biometric authentication: `yea`

### Task 6: Security Through Policies

**Policy Types:**
- **Identity-based Policies:** Attached to identities for permission granting
- **Resource-based Policies:** Implemented on resources defining access rules
- **Session-based Policies:** Temporary access for specific timeframes

**AWS Policy Implementation:**
- JSON or Visual Editor creation methods
- Service-specific permission definitions
- Conditional access based on time, IP, etc.

**Answer:** Time-specific database access: `yea`

### Task 7: Security Through Network Management

**Layered Network Security Approach:**

**Layer 1 - Security Groups:**
- Allow rules only (no deny rules)
- "Deny all unless allowed explicitly" principle
- Instance-level traffic control

**Layer 2 - Network ACLs (Access Control Lists):**
- Include deny rules
- VPC instance protection
- IP-based blocking capabilities

**Layer 3 - Vendor Solutions:**
- AWS DNS Firewall
- AWS Network Firewall
- Provider-specific security features

**AWS Network Security Components:**
- Security Groups
- Network ACLs
- DNS Firewall
- Network Firewall

**Answer:** Security group best practice: `yea`

### Task 8: Security Through Storage Management

**Storage Protection Approaches:**
- **Geographical Boundaries:** Region-based access policies
- **Role-based Authorization:** Identity-based data access
- **Data Encryption:** Server-side encryption at rest

**Critical Storage Aspects:**
- Secure connection strings
- Access security policies
- Data encryption standards
- Physical security measures

**AWS Storage Services:**
- RDS (Relational Database Service)
- S3 (Simple Storage Service)
- Redis and other data repositories

**Answer:** Encryption necessity: `nay` (Both at-rest and in-transit encryption are essential)

## 🛡️ Additional Security Concepts

### Task 9: Advanced Cloud Security

**Disaster Recovery (DR) Approaches:**

**Cold DR:**
- **Cost:** Inexpensive
- **RTO:** Highest recovery time
- **Method:** Data/images snapshots

**Warm DR:**
- **Cost:** Moderate
- **RTO:** Medium recovery time
- **Method:** Near real-time synchronization

**Hot DR:**
- **Cost:** Expensive
- **RTO:** Near zero
- **Method:** Parallel operation with load balancing

**Monitoring & Logging:**
- **Real-time Logging:** Comprehensive activity tracking
- **API Call Monitoring:** Source IP, timing, and action logging
- **Credential Reports:** User account activity monitoring

**AWS Monitoring Services:**
- **IAM:** Basic access logging
- **CloudTrail:** API call recording
- **CloudWatch:** Infrastructure monitoring
- **GuardDuty:** Malicious activity detection

**Patch Management:**
- Automated and scheduled updates
- System vulnerability scanning
- AWS Systems Manager for patch management

**Answer:** DR backup location: `nay` (Should be in different geographical location)

## 📈 Personal Reflection

This room provided a comprehensive foundation in cloud security principles across major service providers, with particular focus on AWS implementations.

**Key Technical Insights:**
- Clear understanding of shared responsibility models in cloud security
- Practical knowledge of IAM policy creation and management
- Hands-on experience with AWS security services configuration
- Comprehensive view of data lifecycle security requirements

**Security Implementation Understanding:**
- The principle of least privilege in cloud access management
- Importance of encryption both at-rest and in-transit
- Layered network security approach in cloud environments
- Disaster recovery strategy selection based on business requirements

**Real-World Application Value:**
The knowledge gained directly applies to:
- Cloud infrastructure security design and implementation
- Compliance and regulatory requirements meeting
- Incident response planning for cloud environments
- Cost-benefit analysis of different DR strategies

**Areas for Further Development:**
- Multi-cloud security strategy implementation
- Advanced IAM policy optimization
- Cloud security automation and orchestration
- Container and serverless security in cloud environments
- Cloud-native application protection platforms (CNAPP)

## 🎓 Professional Relevance

This room is essential for:
- **Cloud Security Architects** designing secure cloud infrastructures
- **DevSecOps Engineers** implementing security in CI/CD pipelines
- **Security Analysts** monitoring cloud environments
- **IT Auditors** assessing cloud security compliance
- **System Administrators** managing cloud resources

The practical AWS exercises provide immediately applicable skills that are highly valuable in today's cloud-centric job market.

---

*This writeup documents my systematic learning journey through the TryHackMe Intro to Cloud Security room, establishing fundamental knowledge of cloud security principles and AWS-specific implementations that form the basis of modern cloud security practices.*
