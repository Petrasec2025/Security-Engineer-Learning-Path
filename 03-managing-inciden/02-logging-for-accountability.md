# Incident Response: Logs and Accountability - TryHackMe Room

![TryHackMe](https://img.shields.io/badge/TryHackMe-Room-success) 
![Category](https://img.shields.io/badge/Category-Incident%20Response-blue) 
![Difficulty](https://img.shields.io/badge/Difficulty-Intermediate-orange)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

## 📋 Room Overview

This TryHackMe room explores the critical relationship between logging and accountability in cybersecurity, focusing on how proper logging practices support incident response and ensure non-repudiation. The room covers SIEM architecture, log ingestion methods, storage considerations, and practical log analysis using Splunk.

## 🎯 Learning Objectives

- **Understand** where data originates, how it's stored, and how security engineers leverage it
- **Comprehend** why accountability is crucial to security and how logging enhances its efficacy
- **Apply** logs and data sources to incident response and accountability principles

## 📖 Key Concepts Covered

### 1. **Accountability in IAAA Model**
- Final pillar of Identification, Authentication, Authorization, and Accountability
- Holds users responsible for their actions through logging
- Essential for maintaining confidentiality, integrity, and availability

### 2. **Non-Repudiation**
- **Definition**: The concept that an individual cannot contest an action
- **Opposite**: Repudiation (disputing an action)
- **Role**: Proves user actions through authentic logs
- **Application**: Part of threat models like STRIDE

### 3. **SIEM Architecture**
- **Search Head**: Component responsible for searching data
- **Indexer**: Handles data storage and indexing
- **Forwarder**: Manages data transmission and load balancing

### 4. **Data Ingestion Methods**
- Agent/Forwarder
- Port-forwarding
- Syslog
- Upload

### 5. **Storage Considerations**
- **Hot Storage**: Frequently accessed data (high-performance)
- **Warm Storage**: Occasionally accessed data
- **Cold Storage**: Rarely accessed data (low-cost storage)
- **PCI DSS Compliance**: Requires 1-year audit log retention with 90 days immediate availability

### 6. **Log Types**
- **Manual Log Sources**: Change logs (human-written)
- **Automated Log Sources**: System logs, application logs (automatically generated)

### 7. **Effective Log Usage**
- **Correlation**: Using multiple log types and sources to build incident narratives
- **Data Enrichment**: Enhancing logs with additional context
- **Validation**: Using multiple sources to verify log authenticity

## 🔍 Practical Exercise

### Splunk Analysis Results

- **Total Events Indexed**: 12,256
- **Events (April 15th-16th 2022)**: 12,250
- **Unique Users**: 4
- **Events for User "James"**: 5
- **Utility Used by James**: wmic
- **Event ID Following Process Creation**: 3

## 💡 Self-Reflection

### Technical Insights Gained

Through this room, I developed a deeper understanding of how logging serves as the foundation for accountability in cybersecurity. The practical Splunk exercise demonstrated how multiple log sources can be correlated to reconstruct user activities and establish non-repudiation.

### Key Takeaways

1. **Log Integrity is Paramount**: Without guaranteed authenticity, logs lose their value for accountability and incident response.

2. **Storage Strategy Matters**: Different storage tiers (hot/warm/cold) serve different purposes in the data lifecycle while maintaining compliance.

3. **Correlation Creates Context**: Using multiple log types together provides a more complete picture of security events than any single log source alone.

4. **SIEM Architecture Impacts Effectiveness**: Understanding how search heads, indexers, and forwarders work together helps optimize log management.

### Practical Applications

This knowledge directly applies to real-world scenarios where I need to:
- Design logging strategies that support accountability
- Configure SIEM solutions for effective incident response
- Ensure compliance with regulatory requirements
- Investigate security incidents using correlated log data

## 🏆 Room Completion

This room provided comprehensive coverage of logging principles and their relationship to accountability. The hands-on Splunk exercise effectively reinforced the theoretical concepts, demonstrating how proper log analysis can trace user activities and support incident investigations.

---

*This room has significantly enhanced my understanding of how logging supports accountability in cybersecurity and provided practical skills in log analysis using enterprise SIEM tools.*
