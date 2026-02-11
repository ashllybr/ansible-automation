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

⚠️ **Scope**: This repository focuses on demonstrating infrastructure automation patterns rather than full-scale production orchestration. The emphasis is on repeatability, security baselines, and operational workflows.

## 🔑 Key Engineering Concepts Demonstrated

- **Idempotent infrastructure automation** - Safe re-execution without side effects
- **Security baseline enforcement** - Consistent security configuration across systems
- **Configuration consistency** - Uniform deployment across environments
- **Operational validation workflows** - Automated verification of system state

## 🏗️ Architecture Overview

[Ansible Control Node]
        ↓
[Multi-Environment Automation]
        ↓
[Ubuntu Infrastructure Provisioning]
        ↓
[Security Hardening] + [Monitoring Setup]
        ↓
[Verification & Operational Validation]

This layered workflow models typical infrastructure automation pipelines used in DevOps environments, emphasizing validation, repeatability, and operational safety.

## 🎯 What This Project Demonstrates

This implementation demonstrates practical experience in:

- **Infrastructure as Code** with Ansible
- **Security automation** following industry best practices
- **Monitoring integration** for system observability
- **Idempotent playbook design** for reliable automation
- **Real-world problem solving** with working solutions

## ⚙️ Design Decisions

Key architectural and technology choices reflect production engineering considerations:

- **UFW selected** for native Ubuntu integration and simplicity over complex firewall solutions
- **Node exporter chosen** for lightweight monitoring footprint and Prometheus ecosystem compatibility
- **Role-based structure** used to ensure modularity, reuse, and separation of concerns
- **Idempotent playbooks** designed for safe re-execution and configuration consistency
- **Ubuntu 22.04 LTS** as target platform for stability and enterprise support lifecycle
- **Modular playbook design** allowing independent execution of infrastructure components
- **Configuration validation** implemented at each stage to ensure system integrity

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

## 📊 Expected Outcome

After successful execution, the target system will have:

- ✅ **SSH Security**: Root login disabled, password authentication disabled
- ✅ **Firewall**: UFW active with minimal allowed ports (22, 80, 443)
- ✅ **Monitoring Service**: Node Exporter running on port 9100
- ✅ **Security Packages**: fail2ban and auditd installed and configured
- ✅ **Automated Updates**: Security updates configured via unattended-upgrades
- ✅ **Health Monitoring**: System health checks running every 5 minutes
- ✅ **System Compliance**: Baseline configuration aligned with security best practices

## 📁 Project Structure

\`\`\`bash
ansible-automation/
├── site.yml                    # Main playbook orchestrator
├── playbooks/                  # Individual automation workflows
│   ├── provision.yml          # System provisioning
│   ├── security.yml           # Security hardening
│   └── monitoring.yml         # Monitoring setup
├── inventories/               # Environment definitions
│   └── development/hosts     # Local development targets
├── roles/                     # Reusable components
│   ├── infrastructure/       # Base system tasks
│   ├── security/            # Security tasks
│   └── monitoring/          # Monitoring tasks
├── docs/                      # Documentation
│   └── architecture.md       # Architecture details
└── .github/workflows/        # CI/CD pipelines
\`\`\`

## 🚀 Getting Started

### **Prerequisites**
- Ubuntu 22.04 LTS (or compatible)
- Ansible 2.16+
- Python 3.11+

### **Quick Start**
\`\`\`bash
# Clone repository
git clone https://github.com/ashllybr/ansible-automation.git
cd ansible-automation

# Run complete setup
ansible-playbook -i inventories/development/hosts site.yml --ask-become-pass

# Or run individual components
ansible-playbook -i inventories/development/hosts playbooks/security.yml --ask-become-pass
ansible-playbook -i inventories/development/hosts playbooks/monitoring.yml --ask-become-pass
\`\`\`

## 🧪 Verification

After running the playbooks, verify the deployment:

\`\`\`bash
# Check SSH security
sudo grep "PermitRootLogin\|PasswordAuthentication" /etc/ssh/sshd_config

# Check firewall status
sudo ufw status

# Check monitoring service
systemctl status prometheus-node-exporter

# View health logs
sudo tail -f /var/log/system-health.log
\`\`\`

## 🔄 Trade-offs & Design Considerations

- **Simulated environment** chosen instead of real cloud deployment to focus on automation patterns.
- **UFW used** instead of enterprise firewalls to keep implementation lightweight and Ubuntu-native.
- **Node exporter selected** for simplicity rather than full observability stack integration.
- **Static inventories** used for clarity rather than dynamic cloud discovery in this demonstration.

## ⚙️ Engineering Constraints

- Designed for single-node Ubuntu environments for demonstration clarity.
- Avoids external SaaS dependencies to maintain simplicity and focus.
- Prioritizes readability and maintainability over advanced orchestration features.
- Emphasizes educational value and repeatability over production-scale deployment.

## 🔄 Execution Flow

1. **Provision system baseline** - Package management and essential tools
2. **Apply security hardening** - SSH, firewall, automated updates
3. **Configure monitoring** - Node exporter, health checks, log rotation
4. **Validate operational state** - Service verification and compliance checks

## 📝 Notes

This is a **practical demonstration project** showcasing real Ansible automation skills. The implementations focus on:

- **Educational value**: Demonstrating actual working automation
- **Professional practices**: Following industry standards
- **Real-world relevance**: Solving common infrastructure challenges
- **Learning transparency**: Clear, understandable code

## 📜 License

MIT License

## 👤 Author

Alex Brian - Cloud & DevOps Engineer
GitHub: [ashllybr](https://github.com/ashllybr)

---

*This project represents real, working infrastructure automation code that has been tested and verified. It demonstrates practical DevOps engineering skills through implementation rather than theoretical examples.*
<- Automated security updates GitHub markdown render refresh -->
