# Auditing and Monitoring - TryHackMe Room Writeup

![TryHackMe](https://img.shields.io/badge/TryHackMe-Room-success)
![Auditing](https://img.shields.io/badge/Auditing-Monitoring-blue)
![Difficulty](https://img.shields.io/badge/Difficulty-Intermediate-orange)
![Time](https://img.shields.io/badge/Time-1%20hour-yellow)
![Category](https://img.shields.io/badge/Category-Security%20Engineering-green)

## 📋 Room Overview

**Room Title:** Auditing and Monitoring  
**Platform:** TryHackMe  
**Category:** Security Engineering / Network and System Security  
**Duration:** 60 minutes  
**Difficulty:** Intermediate  
**Completion Status:** 10% (Partial Completion)

## 🎯 Learning Objectives

- **Understanding auditing** concepts and frameworks
- **Log management** on Linux and Windows systems
- **Monitoring principles** and implementation
- **SIEM (Security Information and Event Management)** basics
- **Practical log analysis** using real tools

## 🔍 Core Concepts & Definitions

### Task 1: Introduction

**Auditing Definition:** A systematic, independent, and objective process of gathering and evaluating evidence to determine if an organization complies with applicable laws, regulations, and industry standards.

**Monitoring Definition:** Continuous observation of an organization's computer technologies and related resources to ensure performance, security, and compliance.

**Answers:**
- Systematic review: `Auditing`
- Continuous observation: `Monitoring`

### Task 2: Audit Objectives and Types

**Audit Objectives:**
- **Risk Assessment:** Identify vulnerabilities affecting information assets
- **Regulatory Compliance:** Ensure adherence to laws and standards
- **IT Governance:** Evaluate decision-making and resource allocation
- **Security Management:** Assess information security policies and controls
- **Operational Evaluation:** Review system design and maintenance processes
- **Data Management:** Ensure data accuracy, completeness, and availability
- **Business Continuity:** Verify disaster recovery capabilities
- **Fraud Detection:** Identify unauthorized activities

**Audit Types:**
- **Internal Audits:** Conducted by organization's own personnel
- **External Audits:** Performed by independent auditors
- **Third-party Audits:** Assess vendors and service providers

**Answers:**
- Independent auditors: `External Audit`
- Organization's personnel: `Internal Audit`

### Task 3: Audit Frameworks

**Popular Audit Frameworks:**

| Framework | Description | Industries | Developer |
|-----------|-------------|------------|-----------|
| **COSO** | Internal control framework for risk management | All industries | Committee of Sponsoring Organizations |
| **COBIT** | IT governance and management framework | All industries | ISACA |
| **ISAE 3402** | Assurance standard for service organization controls | All industries | International Auditing Standards |
| **ISO 27001** | Information security management system standard | All industries | International Organization for Standardization |
| **ITIL** | IT service management best practices framework | All industries | CCTA (Central Computer and Telecommunications Agency) |
| **PCI DSS** | Payment card data security standard | Financial services | PCI Security Standards Council |
| **SOX** | Financial reporting requirements for public companies | Public companies | US Government |

**Answers:**
- Card payment standard: `PCI DSS`
- ITIL developer: `CCTA`
- COBIT developer: `ISACA`

### Task 4: Auditing IT Infrastructure and Operations

**Audit Process Stages:**
1. **Planning:** Establish scope, objectives, and timelines
2. **Execution:** Gather evidence and assess compliance
3. **Assessment:** Identify gaps and make recommendations
4. **Reporting:** Document findings and communicate results
5. **Follow-up:** Monitor implementation of recommendations

**Audit Areas:**
- Information Systems Hardware
- Operating Systems
- File Systems
- Database Management Systems
- Network Infrastructure
- IT Operations
- Business Continuity Planning
- Disaster Recovery Planning

**Answers:**
- Findings presentation: `4` (Reporting)
- Recommendation review: `5` (Follow-up)
- Scope establishment: `1` (Planning)

### Task 5: Logs

**Logging Definition:** Process of recording events as they occur on computer systems for troubleshooting, monitoring, auditing, and compliance purposes.

**Logging Purposes:**
- **Troubleshooting:** Identify and resolve system errors
- **Monitoring:** Track system performance and resource utilization
- **Auditing:** Record user activities for accountability
- **Compliance:** Meet regulatory requirements for record-keeping

### Task 6: Log Management on Linux

**Linux Log Locations:** `/var/log/`

**Key Linux Log Tools:**
- **aureport:** Generate audit summary reports
- **ausearch:** Search audit logs with specific criteria
- **Common log types:** System logs, Application logs, Security logs

**Practical Commands:**
```bash
aureport --failed                    # Show failed events summary
ausearch -m USER_LOGIN -sv no -i     # Search failed login attempts
ausearch --message USER_LOGIN --success no --interpret | grep ct=root | wc -l  # Count failed root logins
```

**Answers:**
- Failed logins: `263`
- Mike's failed logins: `4`
- Root failed logins: `227`

### Task 7: Log Management on MS Windows

**Windows Log Types:**
- **System Logs:** Driver failures, hardware issues
- **Application Logs:** Software-specific events
- **Security Logs:** Authentication, policy changes
- **Forwarded Events:** Centralized logs from multiple systems

**Windows Event IDs:**
- **4624:** Successful logon
- **4625:** Failed logon attempt
- **4634:** Logoff completed
- **4647:** User-initiated logoff
- **4779:** Disconnected remote session

**Windows Log Location:** `%SystemRoot%\System32\Logfiles`

**Answers:**
- Failed login event ID: `4625`
- Total failed attempts: `2`
- 2021 failed attempts: `1`

### Task 8: Monitoring

**Monitoring Definition:** Continuous, real-time observation of IT system performance and metrics to identify potential issues proactively.

**Key Differences - Logging vs Monitoring:**

| Aspect | Logging | Monitoring |
|--------|---------|------------|
| **Primary Function** | Historical record for later review | Real-time observation of system status |
| **Error Detection** | Post-incident analysis | Immediate anomaly detection |
| **Process** | Passive data collection | Active ongoing analysis |
| **Timeliness** | Retrospective analysis | Real-time reporting |
| **Key Objectives** | Diagnostics, compliance, forensics | Preventive maintenance, performance |

### Task 9: SIEM Basics

**SIEM Definition:** Security Information and Event Management - integrated technologies providing holistic view of organizational security.

**SIEM Key Capabilities:**
- **Data Aggregation:** Collect from multiple sources
- **Correlation & Analysis:** Identify patterns in events
- **Alerting & Reporting:** Automatic notifications and dashboards
- **Forensic Analysis:** Historical incident investigation
- **Threat Intelligence:** Integration with external threat feeds
- **Automation & Orchestration:** Automated response to incidents

**Popular SIEM Solutions:** Wazuh, Splunk

## 🛠️ Practical Implementation

### Linux Log Analysis
- Used `aureport` for audit summary generation
- Employed `ausearch` for specific event filtering
- Combined commands with `grep` and `wc` for targeted counting
- Analyzed authentication failures and user activities

### Windows Log Analysis
- Utilized Event Viewer for log inspection
- Identified specific event IDs for security monitoring
- Tracked successful and failed authentication attempts
- Performed historical log analysis

## 📊 Comparison Summary

### Logging vs Monitoring vs Auditing

| Aspect | Logging | Monitoring | Auditing |
|--------|---------|------------|----------|
| **Definition** | Recording system activities | Real-time system observation | Systematic review and analysis |
| **Main Function** | Historical account storage | Live system state visualization | Compliance verification |
| **Timing** | Post-event recording | Real-time analysis | Periodic or event-triggered |
| **Process** | Passive data collection | Active continuous analysis | Scheduled systematic review |
| **Primary Use** | Debugging, forensics, compliance | Performance maintenance, issue prevention | Standards validation, accountability |
| **Key Role** | Data gathering and accountability | Preventive and predictive maintenance | Compliance and legal verification |

## 📈 Personal Reflection

This room provided comprehensive coverage of essential security operations concepts, bridging theoretical frameworks with practical implementation.

**Key Technical Insights:**
- Clear understanding of different audit frameworks and their applications
- Hands-on experience with both Linux and Windows log analysis tools
- Practical knowledge of audit process lifecycle from planning to follow-up
- Understanding of SIEM capabilities in modern security operations

**Practical Skills Developed:**
- Linux audit log analysis using `aureport` and `ausearch`
- Windows Event Viewer navigation and event ID interpretation
- Difference between reactive logging and proactive monitoring
- Framework selection based on organizational needs

**Real-World Application Value:**
The knowledge gained directly applies to:
- Security Operations Center (SOC) operations
- Compliance and regulatory requirements
- Incident response and forensic investigations
- IT governance and risk management
- System performance optimization

**Areas for Further Development:**
- Advanced SIEM configuration and rule creation
- Automated alerting and response workflows
- Cross-platform log correlation techniques
- Compliance reporting automation
- Threat hunting using log data

## 🎓 Professional Relevance

This room is essential for:
- **Security Analysts** monitoring organizational systems
- **IT Auditors** conducting compliance assessments
- **System Administrators** maintaining system health and security
- **SOC Engineers** implementing monitoring solutions
- **Compliance Officers** ensuring regulatory adherence

The practical exercises with real logging tools provide immediately applicable skills that are crucial in today's security-focused IT environments.

---

*This writeup documents my comprehensive learning journey through the TryHackMe Auditing and Monitoring room, establishing fundamental knowledge of security operations principles that form the backbone of effective organizational security management.*
