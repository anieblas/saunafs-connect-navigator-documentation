# **Installation & Setup – SaunaFS Navigator API**

This document provides instructions to install and set up **SaunaFS Navigator API**, a **Node.js + Express API** compiled into a `.deb` package to be installed on a Linux server. The API runs as a system service.

---

## **📥 Installation Instructions**

### **Step 1: Download the Installer**
1. Download the latest version of the **SaunaFS Navigator API Installer** from one of the following sources:
   - **GitHub Releases:** [GitHub Repository](https://github.com/anieblas/saunafs-navigator-api/releases)
   - **Leil Nexus Repository:** [Nexus Repository](<INSERT_NEXUS_REPO_URL_HERE>)
2. Ensure you have **root or sudo privileges** on the Linux server before proceeding.

### **Step 2: Install the Package**
Run the following command to install the `.deb` package:
```sh
sudo dpkg -i saunafs-navigator-api_<version>.deb
```
If there are missing dependencies, fix them by running:
```sh
sudo apt-get install -f
```

### **Step 3: Start and Enable the Service**
Once installed, the service will be registered under **systemd**. You can manage it using the following commands:

#### **Start the Service**
```sh
sudo systemctl start saunafs-navigator-api
```

#### **Enable the Service at Boot**
```sh
sudo systemctl enable saunafs-navigator-api
```

#### **Check Service Status**
```sh
sudo systemctl status saunafs-navigator-api
```

#### **Restart the Service**
```sh
sudo systemctl restart saunafs-navigator-api
```

---

## **🚀 Building and Deploying the `.deb` Package**

### **Building the `.deb` Package**
A script is provided to automate the building process:

```sh
./deb-build/build-deb-package.sh
```

This script:
- Installs dependencies (`npm install`)
- Checks for uncommitted changes in the Git repository
- Reads package metadata from `package.json`
- Compiles the TypeScript project
- Creates the `.deb` package
- Sets up necessary systemd service files and configurations

### **Deploying the `.deb` Package to a Server**

To deploy the `.deb` package to a target server, run:
```sh
./deploy-deb-package.sh <targetServer>
```
where `<targetServer>` is the IP or hostname of the remote server.

This script:
- Removes any existing `.deb` files on the local machine
- Builds the new `.deb` package
- Removes old `.deb` files from the target server
- Transfers the new package to the target server
- Installs the package using `dpkg`
- Fixes missing dependencies using `apt --fix-broken install`
- Restarts the service on the target machine
- Streams the service logs using `journalctl`

---

## **📡 API Documentation**
Once the SaunaFS Navigator API service is running, you can access the API documentation via Swagger:
```plaintext
http://<SERVER_IP>:<PORT>/api-docs
```
*(Replace `<SERVER_IP>` and `<PORT>` with the actual server IP and port number configured in the service. Default port is 3001)*

---

## **📧 Contact & Support**  
For support, open an issue in the official repository or contact the developer.

---
