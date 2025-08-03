# 🖥️ Windows Server Setup – Project X Lab


---
## 🔧 Setup Details

### 🧱 VirtualBox NAT Network Configuration

- **Network Name:** `project-x-network`
- **IP Address Range:** `10.0.0.0/24`
- **DHCP Scope:** `10.0.0.100 – 10.0.0.200`
- **IPv6:** Disabled

> ✅ **Note:** An issue was initially caused by the Windows Server VM using the wrong NAT Network (`NAT Network` instead of `project-x-network`). Once corrected, DNS and internet access started working properly.

---

### 🖥️ Windows Server VM Configuration

- **Operating System:** Windows Server 2025
- **Static IP Address:** `10.0.0.5`
- **Subnet Mask:** `255.255.255.0`
- **Default Gateway:** `10.0.0.1`

---

### 🔌 Installed Roles and Features

Via **Server Manager** → *Add Roles and Features*:
- Active Directory Domain Services (AD DS)
- DNS Server
- DHCP Server
- File and Storage Services
- Web Server (IIS)

![Active Directory Setup](assets/screenshot/server services.avif)

---

### 🧩 Active Directory Domain Services

- **Action:** Promoted server to Domain Controller
- **Domain Type:** New Forest
- **Root Domain Name:** `corp.project-x-dc.com`
- **NetBIOS Name:** `CORP`

---

### 🌐 DNS and Internet Connectivity

- Configured DNS Forwarders:
  - Added `8.8.8.8` in DNS Manager → Server → Properties → **Forwarders**
- Verified DNS and internet were **not working initially** due to network misconfiguration
- ✅ **Fixed** by properly attaching VM to `project-x-network`

---

## ✅ Status

- Windows Server is now a functional Domain Controller.
- Network settings and DNS are working.
- Ready for integration with client machines and security servers.

