# **Installation & Setup – SaunaFS Connect & SaunaFS Connect API**

This document provides instructions to install and set up **SaunaFS Connect** (Windows desktop app) and **SaunaFS Connect API** (Windows service). Both are installed together using an **Inno Setup installer**.

---

## **📥 Installation Instructions**

### **Step 1: Download the Installer**
1. Download the latest version of the **SaunaFS Connect Installer** from one of the following sources:
   - **GitHub Releases:** [GitHub Repository](https://github.com/anieblas/saunafs-connect-gui/releases)
   - **Leil Nexus Repository:** [Nexus Repository](https://repo2.saunafs.com/#browse/browse:saunafs-windows-connect)
   - **Leil Nexus Dev Repository:** [Nexus Repository](https://repo2.saunafs.com/#browse/browse:saunafs-windows-connect-dev)
2. Ensure you have **administrator privileges** on the Windows machine before proceeding.

### **Step 2: Run the Installer**
1. Double-click the downloaded `.exe` installer.
2. Follow the on-screen instructions in the setup wizard.
3. Click **Install** and wait for the installation process to complete.

### **Step 3: Post-Installation Setup**
Once installed, the setup will:
- **Install the SaunaFS Connect desktop application**.
- **Register and start the SaunaFS Connect API as a Windows service**.

---

## **🚀 Running the Applications**

### **Starting SaunaFS Connect (Desktop App)**
- After installation, **SaunaFS Connect** will launch automatically and run in the **system tray** (Windows notification area).
- The app will start **minimized** in the system tray to avoid interrupting the user experience.
- It will automatically connect to the **SaunaFS Connect API**.
- The application is set to **autostart** each time the computer is powered on.
- You can access it by clicking the **SaunaFS Connect** icon in the system tray.

### **Managing SaunaFS Connect API (Windows Service)**
The API is installed as a **Windows service**, which starts automatically. 

---

## **🛠 Configuration**
Configuration files for the API and desktop application are located in:
```plaintext
C:\Users\YOUR_USER\AppData\Roaming\SaunaFSConnect\api-url.json
C:\Users\YOUR_USER\AppData\Roaming\SaunaFSConnect\settings.json
```

### **API URL Configuration**
- When you log in for the first time, you will be prompted to enter the **IP address** where the `saunafs-navigator-api` is running.
- This URL will be stored in the `api-url.json` file and used automatically for all future connections.
- If the stored API URL becomes unreachable, the application will prompt you to enter a new URL before proceeding.

### **Settings Configuration**
- The `settings.json` file stores user preferences such as:
  - **Theme mode**: dark or light mode.
  - Other small configuration preferences.
- You can manually edit this file to update settings, but changes will require a restart of the application.

---

## **📡 API Documentation**
Once the SaunaFS Connect API service is running, you can access the API documentation via Swagger:
```plaintext
http://localhost:<PORT>/api-docs
```
*(Replace `<PORT>` with the actual port number configured in the service. Default 3001)*
