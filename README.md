# 🚀 Ansible Infrastructure Automation Framework

**Practical Ubuntu infrastructure automation with security hardening and monitoring**

![Ansible](https://img.shields.io/badge/Ansible-2.16.3-red)
![Ubuntu](https://img.shields.io/badge/Ubuntu-22.04-orange)
![CI/CD](https://img.shields.io/badge/CI%2FCD-GitHub_Actions-green)
![Testing](https://img.shields.io/badge/Testing-Idempotent-blue)
![License](https://img.shields.io/badge/License-MIT-blue)

## 📋 Overview

This project demonstrates **real, working Ansible automation** for Ubuntu infrastructure. Unlike theoretical examples, this code has been **tested and verified to work**, implementing practical DevOps patterns:

- **Configuration Management** - Automated Ubuntu server setup
- **Security Hardening** - CIS-aligned security practices
- **Monitoring Setup** - Prometheus Node Exporter with health checks
- **Infrastructure Testing** - Idempotent, repeatable automation

## 🎯 What This Project Demonstrates

Through this implementation, I've developed skills in:

- **Infrastructure as Code** with Ansible
- **Security automation** following industry best practices
- **Monitoring integration** for system observability
- **Idempotent playbook design** for reliable automation
- **Real-world problem solving** with working solutions

## 🔧 Features Implemented

### **✅ Working Infrastructure Automation**
- Ubuntu package management and system updates
- Service configuration and management
- User and permission automation
- File system configuration

### **✅ Real Security Hardening**
- SSH security configuration (root login disabled, key-based auth only)
- UFW firewall setup with proper rule management
- Automated security updates configuration
- Security tools installation (fail2ban, auditd)

### **✅ Actual Monitoring Implementation**
- Prometheus Node Exporter installation and configuration
- Custom health monitoring scripts
- Automated log rotation
- System health cron jobs

### **✅ Production Practices**
- Idempotent playbook design
- Modular role structure
- Configuration backup before changes
- Service validation and verification

## 📁 Project Structure
ansible-automation/
├── site.yml # Main playbook orchestrator
├── playbooks/ # Individual automation workflows
│ ├── provision.yml # System provisioning
│ ├── security.yml # Security hardening
│ └── monitoring.yml # Monitoring setup
├── inventories/ # Environment definitions
│ └── development/hosts # Local development targets
├── roles/ # Reusable components
│ ├── infrastructure/ # Base system tasks
│ ├── security/ # Security tasks
│ └── monitoring/ # Monitoring tasks
└── .github/workflows/ # CI/CD pipelines

text

## 🚀 Getting Started

### **Prerequisites**
- Ubuntu 22.04 LTS (or compatible)
- Ansible 2.16+
- Python 3.11+

### **Quick Start**
\`\`\`bash
# Clone the repository
git clone https://github.com/ashllybr/ansible-automation.git
cd ansible-automation

# Run complete infrastructure setup
ansible-playbook -i inventories/development/hosts site.yml --ask-become-pass

# Run individual components
ansible-playbook -i inventories/development/hosts playbooks/security.yml --ask-become-pass
ansible-playbook -i inventories/development/hosts playbooks/monitoring.yml --ask-become-pass
\`\`\`
