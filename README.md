# 📊 SIPEKA - Dinsos PM Kalimantan Utara

**SIPEKA** (*Sistem Pelaporan dan Kinerja Anggaran*) is a comprehensive budget reporting and performance monitoring system developed for the **Department of Social Services and Community Empowerment (Dinsos PM) of North Kalimantan Province**.

---

## 📝 About the Project

SIPEKA is designed to streamline, track, and optimize the submission and evaluation of budget implementation and financial performance reports. By integrating a native PHP backend (connected to phpMyAdmin) with a cross-platform Flutter mobile application, the system ensures real-time reporting, unified API endpoints, and seamless data synchronization.

---

## 🛠️ Tech Stack & Architecture

### Backend & Web Admin Portal
- **PHP Native** — Core backend logic, routing, and database handlers
- **MySQL / phpMyAdmin** — Relational database management system for structured data storage
- **Bootstrap / HTML5 / CSS3** — Web administrator dashboard interface
- **RESTful API Architecture** — JSON-based endpoints shared between web and mobile clients

### Mobile Application
- **Flutter** — Cross-platform framework for iOS and Android deployment
- **Dart** — Primary mobile programming language
- **HTTP / Dio** — Networking library to consume the unified PHP REST APIs
- **SharedPreferences** — Local token and session caching

---

## 🔗 Backend & API Synchronization Concept

To ensure both the web portal and the Flutter mobile application work seamlessly, **the backend utilizes a unified REST API structure connected to phpMyAdmin**:

1. **Database (phpMyAdmin):** All tables (`users`, `reports`, `budgets`, `realizations`) are centralized in MySQL via phpMyAdmin.
2. **PHP Native API Controllers:** Instead of only rendering HTML views, specific routes output JSON data responses (`Content-Type: application/json`) using standard PHP headers.
3. **Unified Endpoint Matching:** The Flutter mobile app hits the exact same API endpoints used by the web frontend logic (e.g., `/api/login.php`, `/api/submit_report.php`, `/api/get_realization.php`).

---

## 💎 Key Features

### 🌐 Web Admin Portal (PHP Native)
- **Dashboard & Analytics:** Real-time summary of budget realization and departmental metrics.
- **phpMyAdmin Data Management:** Direct relational data tracking, exports, and backups.
- **Verification & Approval Workflow:** Review and approve field reports submitted via the mobile app.
- **Role-Based Access Control (RBAC):** Secure administration levels for staff and department heads.

### 📱 Mobile Application (Flutter)
- **Unified Login API:** Authenticates credentials against the shared PHP/MySQL backend user table.
- **Field Report Submission:** POSTs activity logs and financial execution data directly to the server.
- **Document & Media Upload:** Uploads operational proofs and receipts processed by PHP file handlers.
- **Real-Time Synchronization:** Fetches live updates from the shared database.

---

## 📐 System Architecture & Workflow

```text
[ Mobile App (Flutter) ]  ---(REST API / JSON)--->  [ PHP Native Backend ]
                                                             |
[ Web Admin Portal ]      <----------------------------------+
                                                             |
                                                             v
                                                   [ MySQL / phpMyAdmin ]
