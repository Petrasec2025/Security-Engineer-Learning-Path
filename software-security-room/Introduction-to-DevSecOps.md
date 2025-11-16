# TryHackMe - Introduction to DevSecOps Room Writeup

![TryHackMe](https://img.shields.io/badge/TryHackMe-Introduction%20to%20DevSecOps-red) 
![Category](https://img.shields.io/badge/Category-DevSecOps-blue) 
![Time](https://img.shields.io/badge/Time-120%20min-green) 
![Difficulty](https://img.shields.io/badge/Difficulty-Easy-lightgreen)

## 📋 Table of Contents
- [Room Overview](#room-overview)
- [Learning Objectives](#learning-objectives)
- [Task 1: Introduction](#task-1-introduction)
- [Task 2: DevOps: A New Hope](#task-2-devops-a-new-hope)
- [Task 3: The Infinite Loop](#task-3-the-infinite-loop)
- [Task 4: Shifting Left](#task-4-shifting-left)
- [Task 5: DevSecOps: Security Strikes Back](#task-5-devsecops-security-strikes-back)
- [Task 6: DevSecOps Culture](#task-6-devsecops-culture)
- [Task 7: Exercise: Fuel Trouble](#task-7-exercise-fuel-trouble)
- [Key Takeaways](#key-takeaways)
- [Self-Reflection](#self-reflection)

## 🎯 Room Overview

This room serves as the foundation for the DevSecOps learning path, covering the evolution of software development methodologies and the importance of integrating security early in the development lifecycle.

**Room Details:**
- **Title:** Introduction to DevSecOps
- **Duration:** 120 minutes
- **Participants:** 68,042+
- **Path:** First room in the DevSecOps learning path

## 🎓 Learning Objectives

- Understand the history of software development practices and their evolution
- Learn the core concepts and importance of DevSecOps
- Explore DevSecOps culture and discipline
- Understand "Shifting Left" security principles

## 📖 Task 1: Introduction

**Objective:** Get introduced to the DevSecOps learning path and room structure.

**Key Concepts:**
- Secure SDLC (Software Development Life Cycle)
- Pipeline Automation
- Infrastructure as Code (IaC)
- Dependency Management
- CI/CD Security

**Answer:** No answer needed

## 🔄 Task 2: DevOps: A New Hope

### Software Development Evolution

**Waterfall Model (1970s)**
<img width="614" height="443" alt="Screenshot 2025-11-16 at 1 42 00 PM" src="https://github.com/user-attachments/assets/1ff558cd-4db5-4219-aced-9eaff6d1b09f" />

- Rigid hierarchical structure with separate teams
- Led to communication gaps and blame games
- Security testing performed at the end
- Not scalable for modern development needs

**Agile Methodology (2000s)**
<img width="558" height="376" alt="Screenshot 2025-11-16 at 1 42 06 PM" src="https://github.com/user-attachments/assets/b2a8a245-dfe7-4aa7-a60a-c3485a91c167" />
<img width="447" height="622" alt="Screenshot 2025-11-16 at 1 42 14 PM" src="https://github.com/user-attachments/assets/7d060566-01d2-43c3-b4bc-d2bf37fccf0b" />

- Focus on flexibility and adaptability
- Four core values from Agile Manifesto:
  1. Individuals and interactions over processes and tools
  2. Working software over comprehensive documentation
  3. Customer collaboration over contract negotiation
  4. Responding to change over following a plan
- Self-organizing teams

**DevOps (2008)**
- Cultural change emphasizing integration and automation
- Unites development, operations, and QA teams
- Focus on building trust between teams
- Enables small, reversible changes with full visibility

### Questions & Answers

**What methodology relies on self-organising teams that focus on constructive collaboration?**
```
agile
```

**What methodology relies on automation and integration to drive cultural change and unite teams?**
```
DevOps
```

**What traditional approach to project management led to mistrust and poor communication between development teams?**
```
waterfall
```

**What does DevOps emphasize?**
```
building trust
```

## 🔁 Task 3: The Infinite Loop
<img width="788" height="367" alt="Screenshot 2025-11-16 at 1 47 32 PM" src="https://github.com/user-attachments/assets/939f2d72-895b-4447-a6a3-3d398a4b0315" />

### DevOps Components

**CI/CD (Continuous Integration/Continuous Deployment)**
- Frequent merging of small code changes
- Automated testing and checks
- Early bug detection
- Reliable version rollbacks

**Infrastructure as Code (IaC)**
- Manage and provision infrastructure through code
- Consistent resource creation
- Tools: Terraform, Vagrant, Docker

**Configuration Management**
- Maintain infrastructure state
- Efficient change application
- Improved visibility

**Orchestration**
- Automation of workflows
- Fast response to problems
- Health check monitoring

**Monitoring**
- Performance and stability data collection
- Faster recovery
- Better root-cause analysis

**Microservices**
- Application broken into small services
- Flexibility and scalability
- Reduced complexity

### Questions & Answers

**What helps in adding tests in an automated manner and deals with the frequent merging of small code changes?**
```
CI/CD
```

**What process focuses on collecting data to analyse the performance and stability of services?**
```
Monitoring
```

**What is a way to provision infrastructure through reusable and consistent pieces of code?**
```
IaC
```

## ⬅️ Task 4: Shifting Left

### Shifting Left Concept

**Traditional Approach:**
- Security testing at the end of development cycle
- Long delays and team friction
- High remediation costs

**Shift Left Approach:**
- Security integrated from earliest development stages
- Early detection of security flaws
- Lower remediation costs
- No need for rollbacks
<img width="643" height="229" alt="Screenshot 2025-11-16 at 1 49 04 PM" src="https://github.com/user-attachments/assets/c19386ee-caea-4167-a4c0-2dacc1e62dd4" />

**Benefits:**
- Catches flaws early in fast-paced environments
- Adapts security testing to development lifecycle
- Reduces economic losses from security incidents
- Improves product quality and security

### Why Shift Left?
- Automated infrastructure provisioning increases velocity
- Post-development security reviews become bottlenecks
- Security must keep pace with development speed
- Regulatory compliance requirements

### Questions & Answers

**What term is it used to describe accounting for security from the earliest stages in a development lifecycle?**
```
shift left
```

**What is the development approach where security is introduced from the early stages of a development lifecycle until the final stages?**
```
DevSecOps
```

## 🛡️ Task 5: DevSecOps: Security Strikes Back
<img width="401" height="648" alt="Screenshot 2025-11-16 at 1 49 54 PM" src="https://github.com/user-attachments/assets/9eb68944-2db9-4187-a374-0d552f149b94" />

### DevSecOps Value Proposition
- Reduces vulnerabilities
- Maximizes test coverage
- Automates security frameworks
- Prevents brand reputation damage
- Facilitates auditing and monitoring

### DevSecOps Challenges

**Security Silos**
- Security teams isolated from DevOps processes
- Creates specialized security knowledge gaps
- Not scalable or flexible

**Lack of Visibility & Prioritization**
- Security treated as separate from application components
- Difficulty prioritizing risks appropriately
- Trust issues between teams

**Stringent Processes**
- Overcomplicated security compliance verification
- Hinders developer experimentation
- Need for sandbox environments for testing

### Questions & Answers

**What DevSecOps challenge can lead to a siloed culture?**
```
Security Silos
```

**What DevSecOps challenge can affect not prioritizing the right risks at the right times?**
```
Lack of visibility
```

**What DevSecOps challenge stems from needlessly overcomplicated security processes?**
```
Stringent Processes
```

## 🤝 Task 6: DevSecOps Culture

### Key Cultural Elements

**Promote Autonomy of Teams**
- Automate security processes in development pipeline
- Create educational playbooks and runbooks
- Build confidence in engineers to make secure decisions
- Security as supporting function rather than blocker

**Visibility and Transparency**
- Security state dashboards for services
- Accessible security tools and alerts
- Clear remediation suggestions
- Educational approach to security findings

**Understanding and Empathy**
- Recognize different risk perspectives across teams
- Build processes that find common ground
- Account for flexibility in deadlines and bandwidth
- Demonstrate value through understanding team workflows

### Questions & Answers

**How can you make security scalable so it's not left behind when start ups face hypergrowth or in large corporations?**
```
promote autonomy of teams
```

**How can you support teams in understanding risk and educating on security flaws?**
```
Visibility and Transparency
```

**What are key factors to successfully instill security in the development process by accounting for flexibility?**
```
Understanding and Empathy
```

## 🎮 Task 7: Exercise: Fuel Trouble

### Mission Scenario
- **Mission:** Travel to planet with least risk
- **Fuel:** 130,000 Light Years
- **Planets:** Testooine, Hackboo, TryHothMe, Dagobug
- **Models:** Waterfall, Agile, DevOps

### Comic Analysis

**Comic 1 - Waterfall Approach**
- Rigid decision-making based on initial tests
- No flexibility to change course
- Follows predetermined plan

**Comic 2 - Agile Approach**
- Adapts based on new test results
- Changes course when risks identified
- Collaborative decision-making

**Comic 3 - DevOps Approach**
- Continuous analysis and parameter adjustment
- Automated testing and trajectory calculations
- Integrated team collaboration
- Data-driven course correction

### Questions & Answers

**What Software Development Model did the team in Comic 1 follow?**
```
Waterfall
```

**What Software Development Model did the team in Comic 2 follow?**
```
agile
```

**What Software Development Model did the team in Comic 3 follow?**
```
DevOps
```

**What is the flag?**
<img width="668" height="507" alt="Screenshot 2025-11-16 at 1 53 53 PM" src="https://github.com/user-attachments/assets/1df9bac1-dd17-45be-ae78-102ca0b103de" />
<img width="678" height="527" alt="Screenshot 2025-11-16 at 1 54 04 PM" src="https://github.com/user-attachments/assets/62eefc66-0653-4e56-abd1-63d986e346e7" />
<img width="676" height="485" alt="Screenshot 2025-11-16 at 1 54 12 PM" src="https://github.com/user-attachments/assets/822b5d1e-27b3-43d5-a295-7721a774e039" />
<img width="671" height="281" alt="Screenshot 2025-11-16 at 1 54 18 PM" src="https://github.com/user-attachments/assets/108438e5-27b4-4ecb-8440-4fc269e3d4b7" />

```
THM{ONE_TWO_THREE}
```

## 💡 Key Takeaways

### Evolution of Development Methodologies
1. **Waterfall → Agile → DevOps → DevSecOps**
2. Each evolution addresses limitations of previous models
3. Modern approaches emphasize collaboration and automation

### Core DevSecOps Principles
1. **Shift Left:** Integrate security from the beginning
2. **Automation:** Embed security in CI/CD pipelines
3. **Collaboration:** Break down security silos
4. **Culture:** Build security as shared responsibility

### Success Factors
1. **Visibility:** Clear security state monitoring
2. **Education:** Accessible security knowledge
3. **Flexibility:** Adaptable security processes
4. **Empathy:** Understanding team perspectives

## 📝 Self-Reflection

This room provided excellent foundational knowledge about DevSecOps principles and practices. The historical context of software development methodologies helped understand why DevSecOps emerged as a necessary evolution. The "Shifting Left" concept is particularly valuable, emphasizing that security shouldn't be an afterthought but integrated throughout the development lifecycle.

The practical exercise with the comic scenarios effectively demonstrated how different methodologies approach problem-solving, making abstract concepts more tangible. Understanding these differences is crucial for implementing effective DevSecOps practices in real-world scenarios.

The room successfully highlighted that DevSecOps is as much about cultural change as it is about technical implementation. The emphasis on building trust, promoting autonomy, and developing empathy between teams provides a holistic view of what makes DevSecOps initiatives successful.

This foundation will be invaluable as I progress through the DevSecOps learning path, particularly when diving into more technical aspects like pipeline security, infrastructure as code, and automated testing.

---
**Tags:** `#TryHackMe` `#DevSecOps` `#Security` `#DevOps` `#CI/CD` `#ShiftLeft`
