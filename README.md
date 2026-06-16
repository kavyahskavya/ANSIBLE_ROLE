# DevOps Automation with Ansible Roles

## Overview

This repository contains a collection of reusable Ansible roles designed to automate the provisioning and configuration of DevOps environments. The roles help streamline the installation of commonly used tools such as AWS CLI, Docker, Trivy, Java, Maven, NPM, and Git.

These roles are suitable for:

* DevOps Engineers
* Cloud Engineers
* CI/CD Pipeline Setup
* Build Servers
* Application Servers
* Security Scanning Environments

---

# Repository Components

## 1. AWS CLI Installation Role

### Purpose

Installs AWS CLI inside a dedicated Python virtual environment.

### Tasks Performed

* Install `python3-pip`
* Install `python3-venv`
* Create Python virtual environment
* Install latest AWS CLI
* Validate AWS CLI installation

### Verification

```bash
/opt/awscli-venv/bin/aws --version
```

---

## 2. Docker & Trivy Installation Role

### Purpose

Installs Docker Engine and Trivy vulnerability scanner.

### Tasks Performed

* Update package cache
* Install Docker Engine
* Install required dependencies
* Start Docker service
* Add user to Docker group
* Download Trivy package
* Install Trivy
* Remove temporary installation files

### Verification

```bash
docker --version
```

```bash
trivy --version
```

### Sample Image Scan

```bash
trivy image nginx:latest
```

---

## 3. JDK 17, Maven & Git Installation Role

### Purpose

Prepares Java development and build servers.

### Installed Packages

* OpenJDK 17
* Apache Maven
* Git

### Verification

```bash
java -version
```

```bash
mvn -version
```

```bash
git --version
```

### Use Cases

* Jenkins Build Servers
* Spring Boot Applications
* Java Development Environments
* CI/CD Agents

---

## 4. JRE 17, NPM & Git Installation Role

### Purpose

Prepares frontend and runtime application servers.

### Installed Packages

* OpenJDK 17 JRE
* NPM
* Git

### Verification

```bash
java -version
```

```bash
npm -v
```

```bash
git --version
```

### Use Cases

* React Applications
* Angular Applications
* Node.js Applications
* Frontend Build Servers

---

# Directory Structure

```text
ansible-devops-roles/
├── awscli-role/
├── docker-trivy-role/
├── java-maven-git-role/
├── jre-npm-git-role/
└── README.md
```

---

# Example Playbook

```yaml
---
- name: Configure DevOps Server
  hosts: all
  become: yes

  roles:
    - awscli-role
    - docker-trivy-role
    - java-maven-git-role
    - jre-npm-git-role
```

---

# Prerequisites

* Ubuntu 20.04 or later
* Debian-based Linux Distribution
* Ansible 2.9+
* Sudo Privileges
* Internet Connectivity

---

# Execution

Run the playbook using:

```bash
ansible-playbook -i inventory site.yml
```

---

# Benefits

* Automated Infrastructure Provisioning
* Consistent Environment Setup
* Faster Server Configuration
* Reduced Manual Effort
* Reusable Ansible Roles
* Production-Ready Automation

---

# Technologies Used

* Ansible
* AWS CLI
* Docker
* Trivy
* OpenJDK 17
* Apache Maven
* Git
* NPM
* Linux Administration

---

# Author

**Gowtham**

DevOps Engineer

📞 Contact: +91 6385592816

---

# Skills Demonstrated

* Configuration Management
* Infrastructure Automation
* CI/CD Enablement
* Docker Administration
* Container Security Scanning
* Cloud Automation
* Linux System Administration
* Java Build Environment Setup

---

# License

This project is open for learning, development, and operational use. Feel free to customize the roles according to your organizational requirements.
