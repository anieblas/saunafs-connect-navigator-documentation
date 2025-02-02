# **SaunaFS Project Suite** 🚀

Welcome to the **SaunaFS Project Suite**, a collection of tools designed to enhance and manage the **SaunaFS file system** and its Windows client. This suite consists of **four interconnected projects**, each serving a specific role.

---

## **🗂 Project Overview**  

| Project | Description |
|---------|------------|
| **saunafs-connect-gui** | A **React + Electron desktop application** for Windows that acts as a wrapper for the SaunaFS Windows client and SaunaFS file system. |
| **saunafs-connect-api** | A **Node.js + Express API** deployed as a Windows service. This API provides backend functionality for `saunafs-connect-gui`. |
| **saunafs-navigator-web** | A **React-based web application** for administrators to manage users, mount points, user groups, and other configurations. |
| **saunafs-navigator-api** | A **Node.js + Express API** that serves `saunafs-navigator-web` and also handles requests from `saunafs-connect-api`. It is the central data store for the system. |

---

## **🛠 How They Work Together**  

1. **Users run saunafs-connect-gui** on their Windows machines, which consists of:
   - **saunafs-connect-gui** (React + Electron desktop app) for user interaction.
   - **saunafs-connect-api** (Node.js + Express service) that communicates with the central SaunaFS system.

2. **saunafs-connect-api** sends requests to **saunafs-navigator-api**, which acts as the main backend storing user information, configurations, and access control settings.

3. **saunafs-navigator-api** processes and stores data, ensuring all connected clients receive updates. It also interacts with the **saunafs-navigator-web (hosted web application)**, which serves as the admin panel.

4. **saunafs-navigator-web (hosted web application)** allows administrators to manage:
   - Users, mount points, and access groups.
   - System-wide configurations.
   - Real-time changes that propagate to all connected instances.

5. **Real-time Updates with Socket.io**:
   - Any changes made via the **saunafs-navigator-web application** or **client interactions** are broadcasted to all connected clients using **Socket.io**.
   - This ensures that all users see up-to-date information across multiple machines.

6. **Multiple Clients (Users) Can Connect**:
   - Users on different machines (e.g., `User1, User2, User3`) each have their own saunafs-connect-gui instance running.
   - They all communicate with the **central saunafs-navigator-api**, ensuring synchronized data across all connected devices.

### **System Architecture Diagram**
Below is a schematic representation of how the SaunaFS projects interact:

![SaunaFS Architecture](assets/images/saunafs-suite-architecture.png)

---

## **📥 Installation & Setup**  
This section provides an overview of the installation process for the SaunaFS components. Each project has its own setup requirements, which are detailed in separate installation guides. Please refer to the respective guide based on the components you are setting up.

### **Installation Guides** ( in progress )
- **SaunaFS Connect & Connect API Installation:** [Installation Guide](./SUANAFS-CONNECT-SETUP.md) – Covers the installation of the Windows desktop application and its API service.
- **saunafs-navigator-web & saunafs-navigator-api Installation:** [Installation Guide](./SUANAFS-NAVIGATOR-SETUP.md) – Covers the installation of the web-based administration tool and its API.  

---

## **📡 API Documentation**  

The API documentation for **saunafs-connect-api** and **saunafs-navigator-api** is automatically generated using Swagger. After starting the respective applications, you can access the API documentation at:

- **saunafs-connect-api:** `http://localhost:<PORT>/api-docs`
- **saunafs-navigator-api:** `http://localhost:<PORT>/api-docs`

*(Replace `<PORT>` with the actual port number configured in each service. Default its 3001)*

---

## **📄 License**  

> 📝 *To be defined*

---

## **📧 Contact & Support**  

For issues or questions, open an issue in the respective GitHub repository.  

---

## **🔗 Quick Links**  
- [SaunaFS Website](#) *(Add the real link if applicable)*  

