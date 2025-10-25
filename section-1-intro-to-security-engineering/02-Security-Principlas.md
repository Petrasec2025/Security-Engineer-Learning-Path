# 🧠 TryHackMe: Security Principles — Study Notes

![TryHackMe Room](https://img.shields.io/badge/TryHackMe-Security%20Principles-red?logo=tryhackme)
![Difficulty](https://img.shields.io/badge/Difficulty-Beginner-blue)
![Duration](https://img.shields.io/badge/Duration-90%20minutes-yellow)
![Learning%20Path](https://img.shields.io/badge/Path-Security%20Engineer-green)
![Badge](https://img.shields.io/badge/Badge-Earned%20on%20Completion-success)

---


## 🏁 Room Objective

This room explores **core cybersecurity principles** that form the foundation of secure system design and defense strategies.  
It introduces the **CIA Triad**, **DAD Triad**, **security models**, **defense-in-depth**, and **trust frameworks** such as **Zero Trust** and **Trust but Verify**.

> **Key Learning Goals:**
> - Understand the **CIA Triad** and its opposite (**DAD Triad**).  
> - Learn foundational **security models** like Bell-LaPadula, Biba, and Clark-Wilson.  
> - Explore **ISO/IEC 19249 principles** for secure architecture and design.  
> - Grasp **Zero Trust** and **Trust but Verify** philosophies.  
> - Differentiate between **vulnerability, threat, and risk**.

---

## 🧩 Task 1 — Knowing the Adversary

Before implementing controls, we must **understand who we’re defending against**.  
A toddler vs. an industrial spy require different protection levels — security is contextual.

**Key Idea:**  
Perfect security does not exist. We aim to **raise the cost** for attackers and improve posture continuously.

---

## 🧩 Task 2 — CIA Triad

| Principle | Description | Real-world Example |
|------------|-------------|--------------------|
| **Confidentiality** | Ensures only authorized users can access information. | Protecting patient medical records or credit card data. |
| **Integrity** | Ensures data remains unaltered and accurate. | Preventing tampering of an order’s shipping address. |
| **Availability** | Ensures access to systems/services when needed. | Ensuring hospital systems or shopping apps remain online. |

> 💡 **Balance is key:** Over-focusing on one may weaken others (e.g., extreme confidentiality may harm availability).

✅ *Flag:* `THM{CIA_TRIAD}`

---

## 🧩 Task 3 — Beyond CIA: Authenticity & Nonrepudiation

| Concept | Description | Example |
|----------|-------------|----------|
| **Authenticity** | Verifies data is genuine and from a trusted source. | Confirming that a purchase order came from a valid client. |
| **Nonrepudiation** | Prevents senders from denying their actions. | A signed digital order cannot be denied by the sender. |

These ensure **trust and accountability** in digital communications.

---

## 🧩 Task 4 — Parkerian Hexad

In 1998, Donn Parker extended the CIA Triad into six elements:

| Element | Description |
|----------|-------------|
| **Confidentiality** | Prevent unauthorized access. |
| **Integrity** | Ensure accuracy and consistency. |
| **Availability** | Ensure resources are accessible. |
| **Authenticity** | Verify the source of data. |
| **Possession** | Maintain control over information. |
| **Utility** | Ensure information remains useful (e.g., lost encryption key = no utility). |

---

## 🧩 Task 5 — DAD Triad (Opposite of CIA)

| Attack Type | Opposite of | Description |
|--------------|-------------|--------------|
| **Disclosure** | Confidentiality | Unauthorized data exposure. |
| **Alteration** | Integrity | Data tampering or modification. |
| **Destruction/Denial** | Availability | Data loss or service disruption. |

**Example:**
- Dumping customer data online → *Disclosure*  
- Tampering with patient files → *Alteration*  
- Disabling power to data centers → *Destruction/Denial*

✅ *Answers:*  
- Dumped customer records → **Disclosure**  
- Power shutdown attack → **Destruction/Denial**

---

## 🧩 Task 6 — Security Models

### **1. Bell-LaPadula (Confidentiality)**
- *No Read Up (Simple Security)* → Low cannot read high.
- *No Write Down (Star Property)* → High cannot write to low.  
  ➜ Summary: **“Write up, Read down.”**

### **2. Biba Model (Integrity)**
- *No Read Down* → High integrity subject avoids low data.
- *No Write Up* → Low integrity subject cannot write to high.  
  ➜ Summary: **“Read up, Write down.”**

### **3. Clark-Wilson Model (Integrity with Rules)**
- Uses **CDIs**, **UDIs**, **TPs**, and **IVPs**.
- Focuses on **well-formed transactions** and **data validation**.

---

## 🧩 Task 7 — Defence-in-Depth

**Concept:**  
Use multiple security layers to delay, detect, and deter attackers.  
Example: Locked drawer → Locked room → Locked building → CCTV → Guards.

Each layer compensates for potential failure in others.  
➜ Relates to **Layering** and **Domain Separation** in ISO/IEC 19249.

---

## 🧩 Task 8 — ISO/IEC 19249: Architectural & Design Principles

### 🧱 Architectural Principles:
1. **Domain Separation** – Isolate components by security domains.  
2. **Layering** – Multiple layers for validation and control (e.g., OSI model).  
3. **Encapsulation** – Hide internal details and expose controlled interfaces (APIs).  
4. **Redundancy** – Maintain availability and integrity (e.g., RAID, power backups).  
5. **Virtualization** – Sandbox environments, isolate workloads.

### 🧩 Design Principles:
1. **Least Privilege** – Grant minimum necessary permissions.  
2. **Attack Surface Minimization** – Disable unnecessary services.  
3. **Centralized Parameter Validation** – Validate all inputs in one place.  
4. **Centralized Security Services** – Single authentication or policy hub.  
5. **Prepare for Error & Exception Handling** – Fail safe; prevent info leaks.

✅ *Answers:*
- Turning off insecure server → **2 (Attack Surface Minimization)**  
- New employee given limited access → **1 (Least Privilege)**  
- ATM handles network failure safely → **5 (Error Handling)**

---

## 🧩 Task 9 — Zero Trust vs. Trust but Verify

| Model | Core Idea | Implementation Example |
|--------|------------|-------------------------|
| **Trust but Verify** | Trust entities but confirm behavior via logs and audits. | Reviewing proxy or IDS logs. |
| **Zero Trust** | “Never trust, always verify.” Every entity is adversarial until authenticated. | Microsegmentation, identity-based access. |

> 🔐 Zero Trust limits breach impact by **minimizing implicit trust**.

---

## 🧩 Task 10 — Vulnerability, Threat & Risk

| Term | Meaning | Example |
|-------|----------|----------|
| **Vulnerability** | Weakness in a system. | Outdated database software. |
| **Threat** | Potential event exploiting a weakness. | Public exploit released for that software. |
| **Risk** | Likelihood and impact of a threat exploiting a vulnerability. | Attack leads to data breach and downtime. |

---

## 🧩 Task 11 — Shared Responsibility Model (Cloud Security)

Security responsibilities differ by service model:

| Service Type | Provider Responsibility | Customer Responsibility |
|---------------|--------------------------|--------------------------|
| **IaaS** | Hardware, network | OS, applications, data |
| **PaaS** | Hardware, OS | Applications, data |
| **SaaS** | Infrastructure, apps | Data, access management |

> Security in the cloud = **Shared responsibility** between **provider and customer**.

---

## 🧭 Reflection

**Key Takeaways:**
- Security is about **balance, not absolutes**.  
- The **CIA Triad** defines what we protect; **DAD** shows what we defend against.  
- **Models** like Bell-LaPadula and Biba establish theoretical control frameworks.  
- **Defence-in-Depth** and **Zero Trust** ensure layered and contextual protection.  
- Understanding **threats, vulnerabilities, and risks** drives effective mitigation.  

**Next Room:** 🔒 [Intro to Cryptography](../03-Intro-to-Cryptography/README.md)

---

**Badge Earned:** 🏅 *Security Principles – TryHackMe*
