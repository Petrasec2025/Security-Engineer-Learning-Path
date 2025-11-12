# Virtualization and Containers - TryHackMe Room Writeup

![TryHackMe](https://img.shields.io/badge/TryHackMe-Room-success)
![Virtualization](https://img.shields.io/badge/Virtualization-Containers-blue)
![Difficulty](https://img.shields.io/badge/Difficulty-Beginner-green)
![Time](https://img.shields.io/badge/Time-1%20hour-yellow)
![Category](https://img.shields.io/badge/Category-Cloud%20Computing-purple)

## 📋 Room Overview

**Room Title:** Virtualization and Containers  
**Platform:** TryHackMe  
**Category:** Cloud Computing / Virtualization  
**Duration:** 60 minutes  
**Difficulty:** Beginner  
**Completion Status:** 94%  
**Target Machine:** Minikube Server v2.1 (10.10.51.226)

## 🎯 Learning Objectives

- **Understand virtualization concepts** and their practical applications
- **Learn about hypervisors** (Type 1 and Type 2) and their differences
- **Explore container technology** with Docker
- **Introduction to Kubernetes** orchestration platform
- **Hands-on experience** with container deployment and management

## 🏗️ Core Concepts & Definitions

### Task 2: What is Virtualization?

**Virtualization Definition:** The concept of encapsulating capabilities and features of a physical machine in a virtual environment (virtual machine).

**Key Benefits:**
- **Cost Reduction:** Decreases physical hardware requirements
- **Scalability:** Easy resource allocation based on usage
- **Efficiency:** Dynamic resource management

**Virtualization Structure:**
- **Virtualization Engine:** Software creating abstraction layer
- **Guest OS:** Operating system installed on virtual machine
- **Host OS:** Underlying operating system running virtualization engine

**Answers:**
- Scalability benefit: `Y`
- Virtual machine OS: `guest OS`

### Task 3: Hypervisors

**Hypervisor Definition:** Software that creates abstraction layer between hardware and virtual machines, enabling virtualization.

**Type 1 Hypervisors (Bare Metal):**
- **Position:** Directly on hardware (no host OS)
- **Characteristics:** Lightweight, headless, web-managed
- **Use Case:** Large-scale deployments
- **Examples:** VMware ESXi, Proxmox, KVM, Xen

**Type 2 Hypervisors (Hosted):**
- **Position:** On top of existing operating system
- **Characteristics:** GUI-managed, application-based
- **Use Case:** End-user/developer environments
- **Examples:** VirtualBox, VMware Workstation, QEMU

**Answers:**
- VirtualBox type: `type 2`
- Type 1 alternative name: `bare metal hypervisors`

### Task 4: Containers

**Container Definition:** Lightweight virtualization technology that shares some properties with host OS while maintaining isolated filesystem, resources, and process space.

**Key Advantages:**
- **Lightweight:** Minimal resource overhead
- **Portable:** Easy to move and deploy
- **Robust:** Shared OS kernel provides stability

**Comparison with VMs:**
- **VMs:** Full hardware abstraction
- **Containers:** OS-level virtualization with shared kernel

**Answer:** Containers completely abstracted: `N`

### Task 5: Docker

**Docker Definition:** Popular container platform and engine for running container "images."

**Key Components:**
- **Docker Images:** Built from base images (Alpine, Ubuntu)
- **Dockerfile:** Defines container configuration and commands
- **Docker Hub:** Remote repository for container images

**Essential Commands:**
```bash
docker pull <user>/<image>      # Download container image
docker run <user>/<image>       # Run container
docker ps                       # List running containers
```

**Hands-On Deployment:**
- Deployed Flask web server in Docker container
- Used flags: `-d` (detach), `-p` (port mapping)
- Command: `docker run -p 5000:5000 -d cryillic/thm_example_app`
- Accessed web server at: `10.10.51.226:5000`

**Answer:** Web flag: `THM{this_is_running_in_docker}`

### Task 6: Kubernetes (K8s)

**Kubernetes Definition:** Container orchestration platform that extends container capabilities with advanced features.

**Key Features:**
- **Horizontal Scaling:** Add machines rather than resources
- **Extensibility:** Dynamic cluster modifications
- **Self-healing:** Automatic container management
- **Automated Rollouts:** Progressive deployment with rollback capability

**Kubernetes Components:**
- **Pods:** Smallest deployable units
- **Deployments:** Manage pod replicas
- **Services:** Network access to pods
- **ReplicaSets:** Ensure pod availability

**Hands-On Exploration:**
- Used `kubectl` commands to explore cluster
- Examined pods, deployments, services, and replica sets

**Answers:**
<img width="1435" height="761" alt="Screenshot 2025-11-12 at 10 14 43 PM" src="https://github.com/user-attachments/assets/4f32b03c-a5ea-4975-b419-b03126fab66f" />
<img width="1440" height="707" alt="Screenshot 2025-11-12 at 10 15 34 PM" src="https://github.com/user-attachments/assets/df4e9e71-814e-455c-a037-4fdf8bde8558" />
<img width="1417" height="149" alt="Screenshot 2025-11-12 at 10 20 01 PM" src="https://github.com/user-attachments/assets/759879f0-3e47-44d0-a2b0-5423b41dd83a" />
<img width="1439" height="741" alt="Screenshot 2025-11-12 at 10 19 17 PM" src="https://github.com/user-attachments/assets/97a41633-1782-4447-8d96-7e32c2a4ffde" />


- Running pods: `1`
- System pods: `7`
- Pod name: `hello-tryhackme-66c4d4d69d-gb9nz`
- Deployment name: `hello-tryhackme`
- Service port: `443`
- Replica sets: `1`
- Replica set name: `hello-tryhackme-66c4d4d69d`
- Delete command: `kubectl delete deployment hello-tryhackme`

## 🚀 Practical Applications

### Development & Testing
- **Isolated Environments:** Safe testing without affecting production
- **Rapid Deployment:** Quick environment setup and teardown
- **Consistency:** Identical environments across development stages

### Microservices Architecture
- **Lightweight Deployment:** Perfect for small, independent services
- **Scalability:** Easy horizontal scaling of individual components
- **Resource Efficiency:** Optimal resource utilization

### Enterprise Solutions
- **Cost Optimization:** Reduced hardware requirements
- **Disaster Recovery:** Easy backup and restoration
- **Legacy System Support:** Run older systems on modern hardware

## 📈 Personal Reflection

This room provided an excellent foundation in modern virtualization technologies, from traditional hypervisors to cutting-edge container orchestration.

**Key Insights Gained:**
- Clear understanding of the evolution from physical servers to VMs to containers
- Practical differences between Type 1 and Type 2 hypervisors
- Hands-on experience with Docker container deployment
- Introduction to Kubernetes orchestration capabilities

**Technical Skills Developed:**
- Docker container management and port mapping
- Kubernetes cluster exploration using kubectl
- Understanding of container networking and service exposure
- Deployment and verification of containerized applications

**Real-World Relevance:**
The knowledge gained directly applies to modern DevOps practices and cloud infrastructure management. Understanding these technologies is crucial for:
- Cloud security implementation
- Infrastructure as Code (IaC) development
- CI/CD pipeline optimization
- Microservices architecture design

**Areas for Further Study:**
- Advanced Kubernetes configurations and YAML definitions
- Container security best practices and vulnerability scanning
- Multi-cluster Kubernetes management
- Service mesh implementations (Istio, Linkerd)
- Cloud-native storage solutions

## 🎓 Professional Value

This room is essential for:
- **DevOps Engineers** implementing containerized solutions
- **Cloud Security Professionals** securing virtualized environments
- **System Administrators** managing modern infrastructure
- **Developers** working with containerized applications
- **IT Professionals** transitioning to cloud technologies

The hands-on approach with Docker and Kubernetes provides immediately applicable skills that are in high demand in today's job market.

---

*This writeup documents my comprehensive learning journey through the TryHackMe Virtualization and Containers room, providing practical knowledge of modern virtualization technologies that form the foundation of cloud computing and DevOps practices.*
