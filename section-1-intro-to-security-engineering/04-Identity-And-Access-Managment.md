
Here's the updated version with the TryHackMe badge added:

---

## 🛡️ Identity and Access Management (IAM) - TryHackMe Room Summary

![TryHackMe](https://img.shields.io/badge/TryHackMe-IAM%20Room-red) ![Completion](https://img.shields.io/badge/Status-Completed-brightgreen) ![Level](https://img.shields.io/badge/Level-Beginner-blue)

### 🧠 Introduction
This room explores the core concepts of managing identities and authorizations in information security. Using relatable examples like a comic strip and real-world scenarios, it breaks down how systems verify users, grant access, and ensure accountability.

---

## 🔑 Core Concepts of IAAA

### 1. **Identification**
- **Definition:** The process of claiming an identity.
- **Examples:** Username, Email, Student ID, Passport Number.
- **Purpose:** Uniquely identify a user in a system.

### 2. **Authentication**
- **Definition:** Proving the claimed identity.
- **Methods:**
  - **Something you know:** Password, PIN, Passphrase.
  - **Something you have:** Phone (SMS code), Security Key.
  - **Something you are:** Fingerprint, Face ID.
- **MFA (Multi-Factor Authentication):** Using two or more authentication methods for enhanced security.

### 3. **Authorization**
- **Definition:** Deciding what an authenticated user is allowed to access.
- **Examples:** Read/Write permissions, Role-based access.

### 4. **Access Control**
- **Definition:** Enforcing authorization policies.
- **Examples:** File permissions, Door locks, Smart card access.

### 5. **Accountability**
- **Definition:** Holding users responsible for their actions.
- **Tools:** Logging, Auditing, SIEM (Security Information and Event Management).

---

## 🛠️ Access Control Models

| Model | Description | Example |
|--------|-------------|---------|
| **DAC** (Discretionary Access Control) | Resource owner decides access. | Sharing a Google Doc with specific people. |
| **RBAC** (Role-Based Access Control) | Access based on user roles. | Accountants access financial files. |
| **MAC** (Mandatory Access Control) | System-enforced access, highly restrictive. | Classified government systems. |

---

## 🔁 Single Sign-On (SSO)
- **Definition:** Authenticate once to access multiple services.
- **Benefits:**
  - One strong password.
  - Simplified MFA setup.
  - Efficient access management.
  - Reduced support requests.

---

## 🚨 Attacks Against Authentication
- **Replay Attack:** Attacker resends a captured authentication packet to gain access.
- **Mitigation:** Use time-sensitive or unique challenge-response mechanisms.

---

## 📚 Key Abbreviations
- **IAAA:** Identification, Authentication, Authorization, Accountability
- **MFA:** Multi-Factor Authentication
- **SSO:** Single Sign-On
- **IdM:** Identity Management
- **IAM:** Identity and Access Management
- **SIEM:** Security Information and Event Management

---

## ✅ Answers to Room Questions

| Task | Question | Answer |
|------|----------|--------|
| 2 | Room recommended before this? | `Security Principles` |
| 2 | Process for read/send email? | `Authorization` |
| 2 | Process requiring username? | `Identification` |
| 2 | Enforcing policy changes? | `Accountability` |
| 3 | Not used for identification? | `Year of birth` |
| 3 | Not used for identification? | `Street number` |
| 4 | Email login authentication? | `Something you know` |
| 4 | Bank app with SMS code? | `2FA` |
| 4 | Voicemail PIN? | `Something you know` |
| 5 | Secretary sending email for manager? | `Authorization` |
| 5 | Ensuring file not modified? | `Access Control` |
| 5 | Cleaning staff access to rooms? | `Authorization` |
| 8 | Reusing encrypted password attack? | `Replay Attack` |
| 9 | Sharing doc with accounting dept? | `RBAC` |
| 9 | Social media post to 3 friends? | `DAC` |
| 10 | SSO stands for? | `Single Sign-On` |
| 10 | Simplifies MFA setup? | `Yea` |
| 10 | Requires multiple passwords? | `Nay` |
| 10 | Access services after one login? | `Yea` |
| 10 | Single password with SSO? | `Yea` |

---

## 🧭 Reflection
This room provided a clear and practical understanding of identity and access management. It emphasized how each component—Identification, Authentication, Authorization, and Accountability—works together to form a secure system. The use of everyday examples made complex topics like SSO and access control models easy to grasp. Understanding these concepts is crucial for designing and maintaining secure systems in both personal and professional contexts.

---

### 🔗 TryHackMe Badge
[![TryHackMe](https://tryhackme-badges.s3.amazonaws.com/Petras20.png)](https://tryhackme.com/p/Petras20)

**Room Link:** [Identity and Access Management](https://tryhackme.com/room/identityandaccessmanagementiam)  
**Completed by:** [Petras20](https://tryhackme.com/p/Petras20)

---
