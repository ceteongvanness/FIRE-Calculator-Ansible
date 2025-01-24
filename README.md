# FIRE Calculator - Ansible Infrastructure

## Project Structure
```
fire-calculator-ansible/
│
├── inventories/
│   ├── production/
│   │   ├── hosts
│   │   └── group_vars/
│   └── staging/
│       ├── hosts
│       └── group_vars/
│
├── roles/
│   ├── fire-calculator/
│   │   ├── tasks/
│   │   ├── handlers/
│   │   ├── templates/
│   │   └── vars/
│   └── azure-infrastructure/
│       ├── tasks/
│       └── vars/
│
├── playbooks/
│   ├── deploy.yml
│   ├── setup.yml
│   └── secure.yml
│
├── files/
│   ├── scripts/
│   └── configs/
│
├── scripts/
│   ├── vault-decrypt.sh
│   └── validate-config.sh
│
└── .github/
    └── workflows/
        └── ansible-deploy.yml
```

## Overview
Ansible playbooks for deploying FIRE Calculator application on Azure.

## Prerequisites
- Ansible 2.10+
- Azure CLI
- Python 3.8+
- Azure service principal

## Setup
```bash
# Install dependencies
pip install -r requirements.txt
ansible-galaxy install -r requirements.yml

# Configure Azure credentials
export AZURE_SUBSCRIPTION_ID=your-subscription-id
export AZURE_CLIENT_ID=your-client-id
export AZURE_CLIENT_SECRET=your-client-secret
```

## Deployment
```bash
# Verify inventory
ansible-inventory -i inventories/production --list

# Deploy to production
ansible-playbook -i inventories/production playbooks/deploy.yml
```

## Key Features
- Multi-environment support
- Secure credential management
- Automated infrastructure deployment
- CI/CD integration

## Security
- Encrypted vault for sensitive data
- Role-based access control
- Minimal privilege principles
