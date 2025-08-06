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
![Bypass Microsoft Account](/assets/screenshot/)

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
- Ready to be joined to the domain or used for simulation tasks.

---

## 📸 Screenshots

> *(Optional: Add screenshots as needed for visual guidance. Place them under:)*  
> `/Documents/HomeLab/Enterprise101-Lab/assets/screenshot/`  
> Then reference in this file like:
```markdown

            