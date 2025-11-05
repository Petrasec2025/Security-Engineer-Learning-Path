# Cyber Crisis Management - TryHackMe Room

![TryHackMe](https://img.shields.io/badge/TryHackMe-Room-success)
![Category](https://img.shields.io/badge/Category-Incident%20Response-blue)
![Difficulty](https://img.shields.io/badge/Difficulty-Intermediate-orange)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Premium](https://img.shields.io/badge/Premium-Yes-important)

## 📋 Room Overview

This premium TryHackMe room provides comprehensive training on Cyber Crisis Management and the role of Crisis Management Teams (CMT) during severe cybersecurity incidents. It covers incident severity classification, CMT roles and responsibilities, the critical "Golden Hour" response, and the complete crisis management process.

## 🎯 Learning Objectives

- **Understand** how CMT deals with cyber crises
- **Learn** the importance of the "Golden Hour" and time-critical response
- **Master** the CMT process and decision-making framework
- **Recognize** the role of security engineers as subject matter experts

## 🚨 Key Concepts & Definitions

### 1. **Cyber Crisis Definition**
- **Level 4 Incident**: Critical incidents requiring CMT invocation
- **Severity Classification**: Based on scope (users/systems affected) vs recovery difficulty
- **Trigger Examples**: Ransomware deployment requiring environment shutdown

### 2. **Incident Severity Levels**
<img width="1356" height="653" alt="Screenshot 2025-11-06 at 2 19 21 AM" src="https://github.com/user-attachments/assets/6a1c836e-d034-44c1-b32c-3f23d3707694" />

1. **Level 1: SOC Incident** - Handled by Security Operations Center (phishing reports)
2. **Level 2: CERT Incident** - Single team response (single user phishing interaction)
3. **Level 3: CSIRT Incident** - Multiple teams with incident managers (multiple users with malware)
4. **Level 4: CMT Incident** - Critical incidents requiring "nuclear actions" (ransomware deployment)

### 3. **Severity Classification Matrix**
- **Low**: Multiple users affected, low impact
- **Moderate**: Multiple users affected, medium impact  
- **High**: Entire business unit affected, medium impact
- **Critical**: Entire business unit affected, high impact

### 4. **CMT Roles & Responsibilities**

#### CMT Chair
- **Role**: CEO or COO
- **Responsibility**: Leads CMT, final decision authority
- **Decision Style**: Autocratic approach for rapid response

#### Executives
- **Members**: CEO, COO, CIO, CTO, CFO, CISO
- **Role**: Voting rights, ultimate accountability
- **Focus**: Damage limitation and business impact

#### Communication Team
- **Responsibility**: Internal and external stakeholder communication
- **Critical Function**: Narrative control to prevent panic
- **Scope**: Employees, customers, press relations

#### Legal Advisor
- **Responsibility**: Ensures actions comply with laws
- **Key Decisions**: Ransom payment legality, threat actor interaction
- **Jurisdiction**: Country-specific legal requirements

#### Operations Team
- **Responsibility**: Business continuity during crisis
- **Focus**: Minimal operational disruption
- **Leadership**: Often COO or operations experts

#### Subject Matter Experts (SMEs)
- **Role**: Technical advisors to CMT
- **Members**: SOC heads, incident managers, security engineers
- **Function**: Provide technical context for informed decisions

#### Scribe
- **Responsibility**: Comprehensive note-taking
- **Importance**: Legal documentation and timeline creation
- **Audience**: Regulators, government, internal review

### 5. **The Golden Hour**
The first critical hour after CMT invocation where rapid response is essential.

#### Assembly Phase
- **First Step**: Notify and assemble CMT members
- **Process**: Follow pre-defined playbooks and call trees
- **Challenges**: Member availability, communication channel security
- **Responsibility**: CSIRT Chair initiates invocation

#### Information Gathering
- **CSIRT Briefing**: Incident summary and current status
- **Actions Review**: Previously taken measures and effectiveness
- **Recommendations**: Proposed "nuclear actions" for immediate implementation

#### Crisis Triage
- **Process**: Assess incident severity and impact
- **Consideration**: Action consequences on organization
- **Expansion**: Determine additional required stakeholders

#### Notifications
- **Holding Statements**: Prepared messages acknowledging investigation
- **Purpose**: Reassurance without revealing sensitive details
- **Timing**: Often initiated during Golden Hour

### 6. **CMT Process Cycle**

#### Information Updates
- **Frequency**: Determined by CMT, more frequent initially
- **Source**: SME briefings and stakeholder reports
- **Communication**: Technical information abstracted for business understanding
- **Focus**: Impact assessment rather than technical details

#### Triage
- **Definition**: Process of determining crisis severity
- **Functions**: 
  - Adjust severity rating
  - Identify required SMEs
  - Plan communication strategy
- **Outcome**: Updated crisis understanding

#### Action Discussions
- **Scope**: Major business-impacting decisions
- **Examples**:
  - VPN access termination
  - Active Directory domain takeback
  - Disaster recovery environment activation
- **Goal**: Understand action impacts and identify alternatives

#### Action Approvals
- **Time Limitation**: Discussions capped to prevent delays
- **Decision Authority**: CMT Chair (CEO) with executive input
- **Accountability**: Executives bear ultimate responsibility
- **Urgency**: Critical in time-sensitive scenarios (e.g., ransomware spread)

#### Documentation and Closure
- **Scribe Notes**: Comprehensive timeline and decision record
- **Crisis Document**: Formal incident summary and response analysis
- **Lessons Learned**: Process improvement and policy adaptation
- **Legal Requirement**: Often required for regulators and government

### 7. **Subject Matter Experts (SMEs) Role**

#### Critical Functions
- **Scope Assessment**: Provide accurate incident impact understanding
- **Action Identification**: Recommend available technical responses
- **Impact Analysis**: Evaluate effectiveness vs. business disruption
- **System Expertise**: Deep knowledge of specific assets and recovery options

#### Security Engineer Responsibilities
- **Backup Knowledge**: Recovery point objectives and availability
- **DR Capabilities**: Disaster recovery environment switching feasibility
- **System Impact**: Consequences of asset shutdowns
- **Communication**: Clear technical information for business decision-making

### 8. **Additional CMT Actions**

#### Internal Communication
- **Audience**: Employees, help desk, internal stakeholders
- **Preparation**: Pre-written holding statements for rapid deployment
- **Goal**: Panic prevention and support channel management

#### External Communication
- **Channels**: Customers, press, social media
- **Complexity**: Increased difficulty due to social media dynamics
- **Specialization**: Often handled by dedicated communication teams
- **Objective**: Reputational damage control and public reassurance

#### Regulatory Notification
- **Requirements**: Sector-specific legal obligations (e.g., financial sector)
- **Examples**: Financial regulators, information commissioners
- **Basis**: GDPR, industry-specific compliance frameworks
- **Timeline**: Often legally mandated reporting deadlines

#### Law Enforcement Engagement
- **Agencies**: FBI, national cybersecurity centers
- **Benefits**: Investigation assistance, evidence chain of custody
- **Preparation**: Pre-defined processes in CMT playbooks
- **Legal Support**: Prosecution evidence preservation

## 🔍 Practical Application

### Severity Classification Answers
- **Multiple users, medium impact**: Moderate
- **Multiple users, low impact**: Low  
- **Entire business unit, high impact**: Critical

### CMT Roles Answers
- **Note-taking**: Scribe
- **Session leadership**: Chair
- **Legal compliance**: Legal
- **Stakeholder communication**: Communication
- **Technical information**: Subject Matter Experts

### Golden Hour Answers
- **First step**: Assembly
- **Update provider**: CSIRT

### Process Knowledge Answers
- **Severity determination**: Triage
- **Action responsibility**: CMT Chair
- **Ultimate accountability**: Executives

### SME Role Answer
- **Technical information providers**: Subject Matter Experts

### Final Flag
- **Completion Flag**: `THM{The.Crisis.has.been.managed!}`

## 💡 Self-Reflection

### Key Insights Gained

This room provided me with a comprehensive understanding of enterprise-level crisis management during severe cybersecurity incidents. I learned that effective crisis response requires a structured, autocratic approach rather than democratic decision-making due to time constraints.

### Critical Takeaways

1. **Severity Escalation Understanding**: Recognizing when incidents transition from technical issues to business crises requiring CMT involvement.

2. **Golden Hour Criticality**: The first hour determines crisis outcome success, emphasizing rapid but informed decision-making.

3. **SME Value Proposition**: As a security engineer, my role transforms from technical implementer to critical advisor during crises, requiring clear business-focused communication.

4. **Action Impact Awareness**: "Nuclear actions" have significant business consequences that must be carefully weighed against crisis containment benefits.

### Practical Implementation

This knowledge prepares me to:
- Identify crisis-level incidents requiring CMT escalation
- Serve effectively as a Subject Matter Expert during crises
- Understand the CMT decision-making process and information needs
- Prepare holding statements and communication templates in advance
- Document actions comprehensively for legal and improvement purposes

The room emphasized that crisis management isn't about technical perfection but about making the best possible decisions with limited information under extreme time pressure.

## 🏆 Room Completion

This premium room successfully bridges the gap between technical incident response and executive-level crisis management. The comprehensive coverage of CMT roles, the Golden Hour concept, and the complete crisis management process provides essential knowledge for security professionals who may participate in crisis response.

---

*This training has equipped me with the understanding that cyber crisis management requires blending technical expertise with business acumen, and that effective crisis response depends on clear communication, rapid decision-making, and comprehensive documentation throughout the process.*
