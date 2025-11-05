# Becoming a First Responder - TryHackMe Room

![TryHackMe](https://img.shields.io/badge/TryHackMe-Room-success)
![Category](https://img.shields.io/badge/Category-Incident%20Response-blue)
![Difficulty](https://img.shields.io/badge/Difficulty-Intermediate-orange)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Premium](https://img.shields.io/badge/Premium-Yes-important)

## 📋 Room Overview

This premium TryHackMe room provides comprehensive training on the role and responsibilities of a first responder in cybersecurity incidents. It covers evidence preservation, stakeholder alerting, incident isolation, business continuity planning, and proper documentation procedures for effective incident response.

## 🎯 Learning Objectives

- **Understand** what a first responder is and their critical tasks
- **Learn** the importance of preserving evidence in incident response
- **Master** processes required for successful handover to blue teams
- **Apply** proper documentation and communication protocols

## 🚨 Key Concepts & Definitions

### 1. **First Responder Role**
- **Definition**: The initial person who discovers and responds to a cybersecurity incident
- **Responsibility**: May be any team member, not necessarily blue team personnel
- **Critical Function**: Bridge between incident discovery and formal incident response team engagement

### 2. **Evidence Preservation**

#### Volatility Order (IETF Guidelines)
1. **Registers and Cache** - Extremely volatile, changes in split seconds
2. **Routing Table, ARP Cache, Process Table, Kernel Statistics and Memory** - Critical for understanding network communication and running processes
3. **Temporary File Systems** - Contains session data and temporary application files
4. **Disk** - Important for legal proceedings and local log analysis
5. **Remote Logging and Monitoring** - Remote log sources with retention policies
6. **Physical Configuration and Network Topology** - Network segmentation and physical setup
7. **Archival Media** - Backups used for historical comparison

#### Critical "Don'ts" for First Responders
- **Don't** shut down the host (loses volatile evidence, alerts threat actors)
- **Don't** trust programs on the compromised system (may be altered by threat actors)
- **Don't** run programs that modify file access times (taints evidence)

### 3. **Chain of Custody**
- **Definition**: The process of documenting evidence handling to ensure legal admissibility
- **Purpose**: Proves evidence hasn't been tampered with
- **Process**: Includes documentation of collection, storage, transfer, and analysis
- **Legal Requirement**: Essential for court proceedings

### 4. **Incident Playbooks**
- **Definition**: Predefined processes and steps for handling specific types of incidents
- **Purpose**: Ensures repeatable, consistent incident response
- **Examples**: Phishing playbooks, account compromise playbooks
- **Integration**: Multiple playbooks can work together for complex incidents

### 5. **Call Trees**
- **Definition**: Structured communication plan showing who needs to be informed during incidents
- **Purpose**: Ensures proper escalation and stakeholder notification
- **Structure**: Hierarchical with escalation paths for unavailable personnel
- **Implementation**: Often automated through ticketing systems like Jira

### 6. **Containment Methods**

#### Network Segmentation
- **Definition**: Isolating host at network level by moving to different segment
- **Purpose**: Prevents infection spread to other network hosts
- **Implementation**: Through network security controls

#### Physical Isolation
- **Definition**: Physically confiscating and disconnecting the compromised host
- **Purpose**: Complete isolation from network and users
- **Use Case**: User workstations, critical systems

#### Virtual Isolation
- **Definition**: Software-based restriction of host communication
- **Purpose**: Remote containment without physical access
- **Tools**: EDR (Endpoint Detection and Response) systems
- **Limitation**: May fail if EDR is compromised

#### Advanced Technique: Rate Limiting
- **Purpose**: Slows threat actor communication without full isolation
- **Benefit**: Less likely to alert threat actors while buying investigation time
- **Implementation**: Through EDR or network controls

### 7. **Business Continuity Plan (BCP)**
- **Definition**: Comprehensive plan for recovering from significant incidents
- **Purpose**: Maintains business operations during recovery
- **Superpowers**: Allows bypassing normal change management processes
- **Invocation**: By senior management based on incident severity

#### BCP vs DRP
- **DRP (Disaster Recovery Plan)**: Focuses on technical system recovery
- **BCP**: Encompasses DRP plus communication, stakeholder management, and business operations

#### BCP Creation Process
1. **Business Impact Analysis** - Assess worst-case scenarios and impacts
2. **Define Recovery Actions** - Document specific recovery procedures
3. **Plan BCP Team Structure** - Assign responsibilities and roles
4. **Test BCP Plan** - Conduct training and tabletop exercises

#### BCP Metrics
- **RPO (Recovery Point Objective)**: Acceptable data loss timeframe
- **RTO (Recovery Time Objective)**: Time required to recover hardware
- **WRT (Work Recovery Time)**: Time required to recover software and data
- **MTD (Maximum Tolerable Downtime)**: Maximum acceptable downtime
- **MTBF (Mean Time Between Failures)**: Average system operation time between incidents
- **MTTR (Mean Time To Repair)**: Average system recovery time

### 8. **Documentation Standards**
- **Time Format**: UTC for consistency across all records
- **Template Elements**:
  - Action request time
  - Action description
  - Reasoning for action
  - Approving individual
  - Responsible individual
  - Action completion time
  - Observed changes

## 🔍 Practical Application

### Evidence Preservation Priority Answers
- **Disk**: Priority 4
- **Archival Media**: Priority 7  
- **Register and Cache**: Priority 1
- **Legal Evidence Term**: Chain of Custody

### Incident Response Terminology
- **Defined Blue Team Process**: Playbook
- **Stakeholder Notification Structure**: Call Tree

### Containment Methods
- **Remote EDR Containment**: Virtual Isolation
- **Physical Host Collection**: Physical Isolation
- **Network Communication Prevention**: Network Segmentation

### BCP Knowledge
- **BCP**: Business Continuity Plan
- **DRP**: Disaster Recovery Plan
- **Hardware Recovery Metric**: Recovery Time Objective (RTO)
- **Average Recovery Time**: Mean Time to Repair (MTTR)

### Documentation Standards
- **Standard Time Format**: UTC

### Final Flag
- **Completion Flag**: `THM{I.am.ready.to.become.a.first.responder}`

## 💡 Self-Reflection

### Key Insights Gained

This room provided me with a comprehensive understanding of the first responder's critical role in cybersecurity incidents. I learned that proper evidence preservation is not just about collecting data but understanding the volatility hierarchy and legal requirements like chain of custody.

### Critical Takeaways

1. **Evidence Volatility Awareness**: Understanding that registers and memory contain the most volatile evidence that must be captured first revolutionized my approach to incident response.

2. **Containment Strategy Nuance**: Learning that complete isolation isn't always the best immediate response and that techniques like rate limiting can provide investigative advantages was particularly insightful.

3. **BCP Superpowers**: Recognizing that Business Continuity Plans provide necessary shortcuts during crises, but require meticulous documentation to maintain accountability.

4. **Documentation Discipline**: Realizing that even during high-pressure incidents, comprehensive documentation in standard formats (like UTC) is essential for both immediate response and future lessons learned.

### Practical Implementation

This knowledge prepares me to:
- Properly preserve evidence without contaminating it
- Effectively escalate incidents through proper channels
- Recommend appropriate containment strategies
- Understand when and how to invoke business continuity measures
- Maintain thorough documentation for legal and improvement purposes

The room emphasized that first responders don't need to be incident response experts, but they do need to understand proper procedures to bridge the gap between discovery and professional response team engagement.

## 🏆 Room Completion

This premium room successfully transformed theoretical incident response concepts into practical, actionable knowledge for first responders. The comprehensive coverage of evidence preservation, communication protocols, containment strategies, and documentation standards provides a solid foundation for anyone who might discover a cybersecurity incident.

---

*This training has equipped me with the knowledge and confidence to properly respond as a first responder, understanding that my initial actions can significantly impact the success of the entire incident response process.*
