# 🧪 Enterprise101 - Home Lab Simulation

This project is a simulated enterprise network environment designed for hands-on cybersecurity practice. The goal is to understand how attacks occur, how defenders can detect them, and how enterprise systems interact in real-world scenarios.

## 🖥️ What’s Set Up So Far

The initial setup includes:
- ✅ VirtualBox VMs for each key role
- ✅ VirtualBox NAT network `project-x-network (10.0.0.0/24)`
- ✅ Windows Server 2025 (configured as Domain Controller)
- ✅ Windows 11 Enterprise (joined to domain)
- ✅ Kali Linux (attacker machine)
- ✅ Security Onion (monitoring — basic setup only)
- ✅ MailHog (mock internal email server)

> ⚠️ Ubuntu workstation not set up (skipped due to storage limits)

---

## 🧰 Tools & Technologies Used

- **VirtualBox** – Hypervisor to run all virtual machines
- **Windows Server 2025** – Active Directory, DNS, domain controller
- **Windows 11 Enterprise** – Enterprise user workstation
- **Kali Linux** – Red team/attacker machine
- **Security Onion** – Security monitoring & alerting
- **MailHog** – Fake mail server to simulate phishing vectors
- **NAT Network** – Custom `10.0.0.0/24` network used by all VMs


