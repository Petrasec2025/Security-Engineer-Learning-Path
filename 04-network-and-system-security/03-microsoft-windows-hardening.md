# Windows Hardening Lab - TryHackMe Room

## 🛡️ Overview

This comprehensive lab explores essential Windows 10 hardening techniques across multiple security domains. Through hands-on exercises, I implemented security controls for identity management, network security, application hardening, and storage protection to mitigate common attack vectors.

[![TryHackMe](https://tryhackme-badges.s3.amazonaws.com/Petras20.png)](https://tryhackme.com/p/Petras20)

## 📋 Lab Objectives

- **Identity & Access Management**: Implement proper user account controls and authentication policies
- **Network Security**: Configure firewall rules and disable vulnerable protocols
- **Application Management**: Harden Microsoft Office and browser security settings
- **Storage & Compute**: Implement encryption and backup strategies
- **System Monitoring**: Utilize Windows event logging and telemetry

## 🏗️ Architecture & Environment

**Target Machine**: Windows 10 VM
- **IP Address**: Dynamic assignment from TryHackMe
- **Username**: Harden
- **Password**: harden
- **Access Method**: Remote Desktop Protocol (RDP)

## 🔍 Key Findings & Implementation

### Task 2: Understanding General Concepts

**Windows Services Analysis**
- Identified App Readiness service running with **Manual** startup type
- Discovered telemetry services collecting diagnostic data through DiagTrack

**Registry Investigation**
- Located and documented registry key: `{THM_REG_FLAG}`
- Found telemetry flag in Diagnosis folder: `{THM_1000710}`

**Event Logging**
- Analyzed Event Viewer for security incidents
- Categorized events by type (Information, Warning, Error)

### Task 3: Identity & Access Management

**Account Security**
- Administrator account: **Harden**
- Standard accounts configured: **0**
- Implemented Principle of Least Privilege

**User Account Control (UAC)**
- Configured UAC to **"Always Notify"** for elevated privileges
- Ensured administrative consent for system changes

**Password Policies**
- Enforced complexity requirements
- Configured account lockout after failed attempts
- Implemented password history requirements

### Task 4: Network Management

**Firewall Configuration**
- Activated **Private** profile as primary firewall configuration
- Implemented default deny rules for inbound connections

**Protocol Security**
- Disabled SMBv1 protocol using PowerShell:
  ```powershell
  Disable-WindowsOptionalFeature -Online -FeatureName SMB1Protocol
  ```

**DNS Protection**
- Verified hosts file integrity
- Identified tryhack.me resolution: **192.168.1.140**

**ARP Security**
- Analyzed ARP cache entries
- Documented broadcast address: **ff-ff-ff-ff-ff-ff**
- Implemented ARP cache clearing procedures

### Task 5: Application Management

**Windows Defender Exclusions**
- Identified excluded file extension: **.__**

**Microsoft Office Hardening**
- Executed security hardening script
- Obtained completion flag: `{THM_1101110}`
- Implemented macro security controls
- Applied Attack Surface Reduction rules

**Browser Security**
- Enabled Microsoft SmartScreen protection
- Configured strict tracking prevention
- Implemented reputation-based download scanning

### Task 6: Storage Management

**BitLocker Recovery**
- Located BitLocker recovery key with **48 characters**
- Documented last six digits: **377564**

**Backup Strategy**
- Identified backup file format: **.bkf**
- Configured File History for data protection

**Secure Boot**
- Verified UEFI secure boot compatibility
- Ensured trusted boot process integrity

## 🛠️ Technical Implementation Details

### Registry Hardening
```bash
# Accessed registry editor
regedit
# Located security-related keys and values
```

### Service Management
```bash
# Accessed services console
services.msc
# Configured service startup types
```

### Firewall Configuration
```bash
# Accessed advanced firewall settings
WF.msc
# Implemented inbound/outbound rules
```

### Event Monitoring
```bash
# Accessed event logs
eventvwr
# Configured security auditing
```

## 📊 Security Controls Implemented

### Preventive Controls
- User Account Control (UAC)
- Windows Defender Firewall
- AppLocker application whitelisting
- BitLocker encryption
- Secure Boot verification

### Detective Controls
- Windows Event Logging
- Real-time antivirus protection
- SmartScreen application reputation
- ARP cache monitoring

### Corrective Controls
- System backup and recovery
- Account lockout policies
- Malware quarantine procedures
- ARP cache flushing

## 🎯 Attack Vectors Mitigated

1. **Privilege Escalation**: UAC and standard user accounts
2. **Network Attacks**: Firewall rules and SMB disabling
3. **Malware Execution**: AppLocker and Defender protections
4. **Data Exfiltration**: BitLocker encryption
5. **Phishing Attacks**: Browser security controls
6. **ARP Spoofing**: Cache monitoring and clearing

## 📈 Lessons Learned

### Security Principles Applied
- **Defense in Depth**: Multiple layers of security controls
- **Principle of Least Privilege**: Minimal user permissions
- **Default Deny**: Block all, allow by exception
- **Continuous Monitoring**: Real-time threat detection

### Windows-Specific Insights
- Telemetry services provide valuable security data
- Registry modifications require careful consideration
- Group Policy offers centralized security management
- Built-in tools provide robust security capabilities

## 🔮 Future Hardening Considerations

- Implement Windows Defender Application Guard
- Configure Credential Guard for additional protection
- Deploy Windows Sandbox for application testing
- Establish centralized logging with SIEM integration
- Regular security baseline assessments

## 📚 References & Resources

- [Microsoft Security Baselines](https://docs.microsoft.com/en-us/windows/security/)
- [NIST Windows 10 Security Guidelines](https://nvlpubs.nist.gov/)
- [CIS Windows 10 Benchmark](https://www.cisecurity.org/)
- [TryHackMe Windows Fundamentals Modules](https://tryhackme.com)

---

**Completion Time**: 120 minutes  
**Skills Demonstrated**: Windows Security, System Hardening, Security Controls Implementation, Incident Analysis
