# Architecture Overview

## System Design

┌─────────────────────────────────────────────┐
│ Ansible Control Node │
│ (Ubuntu 22.04 + Ansible 2.16.3) │
└─────────────────────────────────────────────┘
│
▼
┌─────────────────────────────────────────────┐
│ Target Ubuntu Servers │
│ (Ubuntu 22.04 LTS) │
│ │
│ ┌─────────────┐ ┌─────────────┐ │
│ │ Provision │ │ Security │ │
│ │ Layer │ │ Layer │ │
│ │ │ │ │ │
│ │ • Packages │ │ • SSH │ │
│ │ • Services │ │ Hardening │ │
│ │ • Users │ │ • UFW │ │
│ │ • Files │ │ • fail2ban │ │
│ └─────────────┘ └─────────────┘ │
│ │ │
│ ▼ │
│ ┌─────────────────────────────┐ │
│ │ Monitoring Layer │ │
│ │ │ │
│ │ • Node Exporter │ │
│ │ • Health Checks │ │
│ │ • Log Rotation │ │
│ └─────────────────────────────┘ │
└─────────────────────────────────────────────┘


## Workflow

1. **Provisioning** → Base system setup
2. **Security** → Hardening and firewall
3. **Monitoring** → Observability setup
4. **Validation** → Verification of changes

## Technology Choices

- **Ansible**: Agentless, idempotent, widely adopted
- **Ubuntu 22.04 LTS**: Stable, well-documented, enterprise-friendly
- **UFW**: Simple firewall management for Ubuntu
- **Prometheus Node Exporter**: Standard for system metrics
- **fail2ban**: Lightweight intrusion prevention

## Design Principles

1. **Idempotence**: Safe to run multiple times
2. **Modularity**: Roles for separation of concerns
3. **Security First**: Default secure configuration
4. **Observability**: Built-in monitoring
5. **Simplicity**: Clear, maintainable code
