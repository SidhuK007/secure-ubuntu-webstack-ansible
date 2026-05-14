# Secure Ubuntu Web Stack Automation with Ansible

## Overview

This project automates the deployment and hardening of a secure Ubuntu-based web stack using Ansible.

The playbook installs and configures:

- Apache
- PHP
- MySQL
- Redis
- Python
- Flask support
- Apache virtual hosts
- Reverse proxy setup
- UFW firewall
- SSH hardening
- Apache hardening
- Redis security configuration
- MySQL security configuration

The goal of this project is to demonstrate practical DevSecOps, Linux administration, infrastructure automation, and cybersecurity hardening concepts.

---

# Features

## Infrastructure Automation

- Automated Ubuntu server provisioning
- Idempotent Ansible playbooks
- Package management automation
- Service management automation

## Web Stack Deployment

- Apache web server setup
- PHP integration
- Python environment setup
- Flask support
- Reverse proxy configuration

## Database & Cache

- MySQL installation and database creation
- Redis installation and hardening
- Local-only service binding

## Security Hardening

- SSH hardening
- Root login disabled
- Password authentication disabled
- Apache information disclosure reduction
- Directory listing disabled
- UFW firewall configuration
- Redis password protection
- MySQL localhost restriction

---

# Technologies Used

- Ubuntu Server
- Ansible
- Apache2
- MySQL
- Redis
- PHP
- Python
- Flask
- UFW Firewall

---

# Project Structure

```text
.
├── inventory.ini
├── site.yml
├── README.md
```

---

# Lab Environment

This project was tested in:

- Ubuntu Server VM
- VMware environment

---

# Installation

## 1. Clone Repository

```bash
git clone https://github.com/yourusername/secure-ubuntu-webstack-ansible.git

cd secure-ubuntu-webstack-ansible
```

---

## 2. Install Ansible

```bash
sudo apt update
sudo apt install ansible -y
```

---

## 3. Install Required Collection

```bash
ansible-galaxy collection install community.mysql
```

---

## 4. Configure Inventory

Edit:

```ini
inventory.ini
```

Example:

```ini
[webservers]
192.168.1.100 ansible_user=ubuntu
```

---

## 5. Test Connectivity

```bash
ansible webservers -i inventory.ini -m ping
```

---

## 6. Run Playbook

```bash
ansible-playbook -i inventory.ini site.yml
```

---

# What Gets Configured

## Apache

- Virtual hosts
- Reverse proxy support
- Security hardening
- Logging configuration

## PHP

- PHP modules
- Apache integration

## MySQL

- Database creation
- User creation
- Local-only binding

## Redis

- Protected mode enabled
- Password authentication
- Local-only access

## SSH

- Root login disabled
- Password authentication disabled
- Public key authentication enabled

## Firewall

- UFW enabled
- HTTP/HTTPS allowed
- SSH allowed

---

# Security Notes

This project focuses on defensive system administration and secure infrastructure deployment.

The following hardening measures are implemented:

- Reduced Apache fingerprinting
- Restricted service exposure
- Secure SSH configuration
- Firewall enforcement
- Disabled directory indexing
- Redis authentication
- Localhost-only database binding

---

# Notes About HTTPS

Certbot is installed but not configured because local domains such as:

- example.local
- api.local

are not publicly valid domains.

For local lab testing:
- Use HTTP
OR
- Use self-signed certificates

---

# Future Improvements

Planned enhancements:

- Ansible roles
- Jinja2 templating
- Ansible Vault integration
- Gunicorn service automation
- Docker support
- CI/CD integration
- Fail2Ban
- Monitoring and logging stack
- Backup automation

---

# Learning Objectives

This project demonstrates:

- Linux system administration
- Infrastructure as Code (IaC)
- DevSecOps fundamentals
- Web server hardening
- Service configuration
- Secure automation practices
- Ansible automation
- Reverse proxy architecture

---

# Disclaimer

This project is intended for:
- Educational purposes
- Lab environments
- Cybersecurity learning
- DevSecOps practice

Always review configurations before using in production environments.

---

# License

MIT License
