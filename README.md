# Practicing DevSecOps — SDLC

## 📚 Overview

**SDLC (Software Development Life Cycle)** is the process used to plan, design, develop, test, deploy, and maintain software.

From a cybersecurity perspective, security should **not be treated as the final step of development**. Instead, security should be integrated throughout the entire software development lifecycle.

This approach is known as **Secure SDLC** and is an important part of **DevSecOps**.

---

## 🔄 SDLC Phases

### 1. Planning

The initial phase where the project goals and scope are defined.

Key questions:

* What are we going to build?
* Who is the target user?
* What are the business requirements?
* What are the risks?
* What are the budget and resource requirements?

---

### 2. Requirements

The requirements define what the software should do and what constraints it must satisfy.

#### Functional requirements

Describe **what the system should do**.

Examples:

* User registration
* Login
* File upload
* Payment processing

#### Non-functional requirements

Describe **how the system should behave**.

Examples:

* Performance
* Availability
* Scalability
* Reliability

#### Security requirements

Define the security controls that need to be implemented.

Examples:

* MFA (Multi-Factor Authentication)
* Encryption
* RBAC (Role-Based Access Control)
* Password policies
* Secure session management

---

### 3. Design

The system architecture and technical solution are designed.

Security considerations include:

* Application architecture
* Database design
* API design
* Authentication and authorization
* Data flow
* Network architecture
* **Threat modeling**

Example threat-modeling question:

> What happens if an attacker sends malicious input to the application?

---

### 4. Development / Implementation

Developers implement the application based on the design and requirements.

Security practices include:

* Secure coding
* Code review
* Input validation
* Output encoding
* Dependency management
* **SAST (Static Application Security Testing)**

The goal is to identify and prevent security issues as early as possible.

---

### 5. Testing

The application is tested to verify that it works correctly and securely.

Testing can include:

* Unit testing
* Integration testing
* Security testing
* SAST
* **DAST (Dynamic Application Security Testing)**
* Penetration testing
* Vulnerability scanning

The goal is to identify vulnerabilities before the application reaches production.

---

### 6. Deployment

The application is deployed to the production environment.

Security considerations include:

* Secure configuration
* System hardening
* Secrets management
* Access control
* Secure CI/CD pipelines
* Infrastructure security
* Container security

---

### 7. Maintenance

Security does not end after deployment.

Ongoing security activities include:

* Monitoring
* Logging
* Vulnerability management
* Security patching
* Dependency updates
* Incident response
* CVE management
* Continuous security improvements

---

# 🛡️ SDLC vs. Secure SDLC

### Traditional SDLC

```text
Planning
   ↓
Requirements
   ↓
Design
   ↓
Development
   ↓
Testing
   ↓
Deployment
   ↓
Maintenance
```

### Secure SDLC

Security is integrated throughout the entire lifecycle:

```text
Security Requirements
        ↓
Threat Modeling
        ↓
Secure Coding
        ↓
Security Testing
        ↓
Secure Deployment
        ↓
Monitoring & Vulnerability Management
```

The key principle is:

> **Security is not a single phase of SDLC. Security is a layer across the entire SDLC.**

---

# 🔐 Security Activities Across SDLC

| SDLC Phase       | Cybersecurity Activities                                |
| ---------------- | ------------------------------------------------------- |
| **Requirements** | Security requirements, compliance requirements          |
| **Design**       | Threat modeling, security architecture                  |
| **Development**  | Secure coding, code review, SAST                        |
| **Testing**      | SAST, DAST, vulnerability scanning, penetration testing |
| **Deployment**   | Hardening, secrets management, secure CI/CD             |
| **Maintenance**  | Monitoring, patching, CVE management, incident response |

---

# 🚀 DevSecOps Connection

**DevSecOps** extends the DevOps philosophy by integrating security into the entire software development and delivery process.

Instead of:

```text
Development → Operations → Security
```

DevSecOps aims for:

```text
Development + Security + Operations
```

Security becomes a **shared responsibility** rather than something handled only by a dedicated security team at the end of development.

---

# 🎯 Learning Goals

Through this repository I am practicing and documenting:

* SDLC fundamentals
* Secure SDLC
* DevSecOps principles
* Security requirements
* Threat modeling
* Secure coding
* SAST and DAST
* Vulnerability management
* CVE management
* Secure CI/CD
* Application security

---

## 📝 Notes

This repository is part of my ongoing cybersecurity learning journey and serves as a practical collection of notes, exercises, and experiments related to **DevSecOps and application security**.
