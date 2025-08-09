# 🖥️ Windows 11 Workstation Setup - `project-x-sec-work`

This guide outlines the steps followed to set up the Windows 11 workstation VM as part of the **Enterprise101 Home Lab**.

---

## 🛠️ Installation Process

1. **Start the Windows 11 Installation.**
2. Proceed through language and keyboard layout selection screens.

---

## 🚫 Bypass Microsoft Account Creation

To avoid Microsoft account sign-up:

1. **Temporarily change the network type:**
   - Go to VirtualBox → VM Settings → **Network**.
   - Change **Adapter 1** from `NAT Network` to `Host-only Adapter`.

2. **Open Command Prompt:**
   - On the “Let’s connect you to a network” screen, press: `Shift + F10`.

3. **Bypass Internet Requirement:**
   - In the command prompt, enter:
     ```
     oobe\bypassnro
     ```
   - The VM will restart.
![Bypass Microsoft Account](/assets/screenshot/bypass.jpg)

4. Proceed again with the language and region setup.

5. On the network screen, you should now see:
   - Click **“I don’t have Internet”**.
   - Click **“Continue with limited setup.”**

---

## 👤 Create Local Account

1. **Account Name:**  
    --project-x-sec-work
2. **Password:**  
    --project@123

3. **Privacy Settings:**  
- Turn off **all toggles** for privacy settings.

4. Let Windows finish setting up the system.

---

## 🌐 Reconnect to NAT Network

1. After setup and reaching the desktop:
- Go back to VirtualBox → VM Settings → **Network**.
- Change **Adapter 1** back to `NAT Network`.
- Select the custom network:
  ```
  project-x-network
  ```

---

## ✅ Final Result

- Windows 11 Workstation successfully installed and isolated from Microsoft sign-in.
- Device is configured for enterprise network simulation in the home lab.
- Ready to be joined to the domain 

# Connect Windows 11 Enterprise (project-x-win-client) to Windows Domain Controller

## Prerequisites
- Ensure **Windows Server 2025** (`project-x-dc`) is running.
- Domain: `corp.project-x-dc.com`
- Domain Controller IP: `10.0.0.5`

---

## Step 1: Set Static IP Address
1. Open **Control Panel** (`Windows + X` → *Network and Sharing Center*).
2. Select **Change adapter settings**.
3. Right-click **Ethernet** → *Properties*.
4. Select **Internet Protocol Version 4 (TCP/IPv4)** → *Properties*.
5. Enter the following:
   -IP address: 10.0.0.100
   -Subnet mask: 255.255.255.0
   -Default gateway: 10.0.0.1
   -Preferred DNS server: 10.0.0.5
6. Click **OK** and close the settings.

---

## Step 2: Join the Domain
1. Search for **Change workgroup name** in Windows search.
2. Click **Change** in *System Properties*.
3. Under **Member of**, select **Domain** and enter:corp.project-x-dc.com
4. When prompted, enter:
   -Username: johnd@corp.project-x-dc.com
   -Password: @password123!
5. A welcome message should appear:  
![Bypass Microsoft Account](/assets/screenshot/adding.jpg)
----

**Welcome to the corp.project-x-dc.com domain**.
6. Click **OK** and restart the computer.
![Bypass Microsoft Account](/assets/screenshot/domainadded.jpg)
---

✅ **Result:** Windows 11 client `project-x-win-client` is successfully connected to the Windows Server 2025 domain.


  

            