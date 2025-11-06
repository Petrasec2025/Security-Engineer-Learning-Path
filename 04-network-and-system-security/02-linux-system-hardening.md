# Linux System Hardening - TryHackMe Room Notes

![TryHackMe](https://img.shields.io/badge/TryHackMe-Premium%20Room-red) ![Time](https://img.shields.io/badge/Time-120%20min-blue) ![Users](https://img.shields.io/badge/Users-24,517-green) ![Progress](https://img.shields.io/badge/Progress-9%25-orange)

## 📋 Room Overview
**Room Name**: Linux System Hardening  
**Platform**: TryHackMe (Premium Room)  
**Duration**: 120 minutes  
**Participants**: 24,517 users  
**Objective**: Learn comprehensive Linux system security hardening techniques

---

## 🎯 Learning Objectives
- Physical Security measures
- Filesystem Encryption (LUKS)
- Firewall Configuration
- Remote Access Security
- User Account Management
- Software and Services Security
- Update and Upgrade Policies
- Audit and Log Configuration

---

## 📚 Detailed Content Summary

### Task 1: Introduction
**Definition**: Overview of Linux security importance and cost benefits compared to proprietary systems.

**Key Commands**:
```bash
ssh tryhackme@MACHINE_IP
# Password: insecurePass123
```

### Task 2: Physical Security
**Definition**: Protecting systems from physical access threats and unauthorized boot modifications.

**Key Commands**:
```bash
grub2-mkpasswd-pbkdf2
```

**Key Terms**:
- **PBKDF2**: Password-Based Key Derivation Function 2
- **GRUB**: Grand Unified Bootloader

### Task 3: Filesystem Partitioning and Encryption
**Definition**: Implementing disk encryption using LUKS to protect data at rest.

**Key Commands**:
```bash
cryptsetup -y -v luksFormat /dev/sdb1
cryptsetup luksOpen /dev/sdb1 EDCdrive
cryptsetup luksDump /dev/sdb1
```

**Key Terms**:
- **LUKS**: Linux Unified Key Setup
- **LUKS phdr**: Partition Header containing encryption metadata
- **KM**: Key Material sections storing encrypted master keys

### Task 4: Firewall
**Definition**: Configuring network traffic control using various Linux firewall solutions.

**Key Technologies**:
- **Netfilter**: Core packet filtering framework
- **iptables**: Traditional firewall frontend
- **nftables**: Modern replacement for iptables
- **UFW**: Uncomplicated Firewall (user-friendly frontend)

**Key Commands**:
```bash
# iptables
iptables -A INPUT -p tcp --dport 22 -j ACCEPT
iptables -A OUTPUT -p tcp --sport 22 -j ACCEPT

# nftables
nft add table fwfilter
nft add chain fwfilter fwinput { type filter hook input priority 0 \; }

# UFW
ufw allow 22/tcp
ufw status
```

### Task 5: Remote Access
**Definition**: Securing remote system access, primarily focusing on SSH security.

**Security Measures**:
- Disable root login: `PermitRootLogin no`
- Disable password authentication: `PasswordAuthentication no`
- Enable public key authentication: `PubkeyAuthentication yes`

**Key Commands**:
```bash
ssh-keygen -t rsa
ssh-copy-id username@server
```

### Task 6: Securing User Accounts
**Definition**: Implementing user account security policies and privilege management.

**Key Commands**:
```bash
# Add to sudoers group
usermod -aG sudo username  # Debian/Ubuntu
usermod -aG wheel username # RedHat/Fedora

# Disable account
# Edit /etc/passwd and change shell to /sbin/nologin
```

**Password Policy Configuration**:
- File: `/etc/security/pwquality.conf` or `/etc/pam.d/common-password`
- Options: `difok`, `minlen`, `minclass`, `badwords`, `retry`

### Task 7: Software and Services
**Definition**: Minimizing attack surface by managing installed software and network services.

**Security Practices**:
- Disable unnecessary services
- Block unneeded network ports
- Replace legacy protocols (Telnet/TFTP) with secure alternatives (SSH/SFTP)
- Remove identification strings from service banners

**Secure Protocol Replacements**:
- Telnet → SSH
- TFTP/FTP → SFTP/FTPS

### Task 8: Update and Upgrade Policies
**Definition**: Maintaining system security through regular updates and understanding distribution lifecycles.

**Update Commands**:
```bash
# Debian/Ubuntu
apt update && apt upgrade

# RedHat/Fedora
yum update    # Older versions
dnf update    # Newer versions
```

**Distribution Support**:
- **Ubuntu LTS**: 5 years free + 5 years extended
- **RedHat Enterprise**: 12 years total support
- **Key Vulnerabilities**: Dirty COW (emphasizes kernel updates)

**Acronyms**:
- **YUM**: Yellowdog Updater, Modified
- **DNF**: Dandified YUM

### Task 9: Audit and Log Configuration
**Definition**: Monitoring system activity through log files for security auditing.

**Key Log Files**:
- `/var/log/messages` - General system logs
- `/var/log/auth.log` / `/var/log/secure` - Authentication logs
- `/var/log/utmp` / `/var/log/wtmp` - User login records
- `/var/log/kern.log` - Kernel messages
- `/var/log/boot.log` - Boot information

**Log Analysis Commands**:
```bash
tail -n 15 kern.log
grep denied secure
```

### Task 10: Conclusion
**Definition**: Summary of Linux hardening best practices and implementation guidelines.

**Core Principles**:
1. Document host information
2. Test changes in non-production environments
3. Document all modifications
4. Implement defense in depth

---

## 🤔 Self-Reflection

### 📊 Knowledge Assessment
**Strengths Developed**:
- Comprehensive understanding of Linux security layers
- Practical experience with encryption implementation
- Firewall configuration across different technologies
- User account security management

**Areas for Improvement**:
- Need more hands-on practice with nftables
- Deeper understanding of SELinux/AppArmor integration
- Real-world scenario application of update policies

### 💡 Key Takeaways
1. **Defense in Depth**: Multiple security layers are crucial
2. **Principle of Least Privilege**: Essential for user management
3. **Regular Updates**: Critical for vulnerability mitigation
4. **Monitoring**: Logs provide essential security intelligence

### 🛠️ Practical Applications
- Enterprise server hardening
- Cloud infrastructure security
- Compliance requirements implementation
- Incident response preparation

### 🔄 Continuous Learning Path
- Advanced SELinux/AppArmor configuration
- Container security hardening
- Automated security compliance tools
- Intrusion detection systems integration

---

## 🎖️ Achievement Badges
![Linux Security](https://img.shields.io/badge/Linux-Security%20Hardening-success) ![Encryption](https://img.shields.io/badge/LUKS-Encryption-blue) ![Firewall](https://img.shields.io/badge/Firewall-Configuration-important) ![SSH Security](https://img.shields.io/badge/SSH-Hardened-brightgreen)

This room provided a solid foundation in Linux system security, covering both theoretical concepts and practical implementations essential for securing production environments.
