# 🛡️ BIoT-DM: Blockchain-Based IoT Device Management System

[![Go Version](https://img.shields.io/badge/Go-1.22+-00ADD8)](https://golang.org/)
[![React Version](https://img.shields.io/badge/React-18+-61DAFB)](https://reactjs.org/)
[![License](https://img.shields.io/badge/License-Educational-lightgrey)](LICENSE)

📡 **Status:** Active Development

👨‍💻 **Developer:** Md Abdullah Rajeeb (MotionProgramming)

🏗️ **Architecture:** Native Go Backend + MySQL Database + React.js Frontend + Ethereum PoA Blockchain

---

## 📘 Project Overview

**BIoT-DM** is an advanced IoT management platform designed to provide **secure, scalable, and real-time control** for industrial, smart city, and critical IoT deployments.

It combines:

* **Go Backend:** High-performance, concurrent processing
* **MySQL Database:** ACID-compliant, optimized storage
* **React Frontend:** Interactive dashboards and real-time analytics
* **Ethereum PoA Blockchain:** Immutable audit trails and device identity verification

**Key Highlights:**

* **Security-First:** Blockchain-based device identity, JWT authentication, and role-based access control
* **Real-Time Monitoring:** WebSocket and MQTT telemetry for instant insights
* **Device Lifecycle Management:** Registration, activation, suspension, decommission, and firmware version tracking
* **Immutable Auditability:** Secure logging of all actions with blockchain verification
* **Scalable & High-Performance:** Handles thousands of devices with sub-100ms response times
* **User-Centric Dashboard:** Analytics, notifications, and exportable reports

---

## 🎯 Core Objectives

| Category                      | Objectives                                                                                                  |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------- |
| **Security & Compliance**     | Device identity on blockchain, immutable logs, JWT authentication, RBAC (Admin, Developer, Auditor, Device) |
| **Performance & Reliability** | High-performance Go backend, concurrent handling, sub-100ms API responses, scalable architecture            |
| **User Experience**           | Real-time dashboards, multi-device support, interactive analytics, exportable reports                       |

---

## 🛠️ Technology Stack

| Layer              | Technology                                             |
| ------------------ | ------------------------------------------------------ |
| Backend Language   | Go 1.22+ (Standard Library, no frameworks)             |
| HTTP Routing       | net/http, http.ServeMux                                |
| Authentication     | JWT (HS256), SHA-256 password hashing                  |
| Database           | MySQL (optimized, ACID-compliant)                      |
| Blockchain         | Ethereum PoA (private chain)                           |
| Real-Time Comm     | MQTT (IoT devices), WebSocket (dashboard), TLS-secured |
| Frontend UI        | React.js 18+                                           |
| Data Visualization | Chart.js, D3.js                                        |
| API Documentation  | Swagger/OpenAPI                                        |
| DevOps             | Docker, Docker Compose, GitHub Actions CI/CD           |
| Security           | HTTPS/TLS, Input validation, Rate limiting, RBAC       |

---

## ✨ Core Features

### 🔐 Security

* Multi-layer JWT authentication
* Two-Factor Authentication (TOTP)
* Role-based access control
* Session management with auto-expiration and concurrency control

### 💻 Device Management

* Device registration, activation, suspension, decommissioning
* Firmware versioning with on-chain hash verification
* Real-time telemetry ingestion and monitoring

### 💸 Command & Transaction Engine

* Secure, atomic device commands
* Filter telemetry/commands by device, type, or timestamp
* Audit logs with blockchain verification

### 📊 Analytics & Dashboard

* Real-time telemetry visualization
* Categorized analytics by device type and location
* Exportable CSV/PDF reports
* Admin dashboards for system health and activity metrics

### ⚡ Notifications

* WebSocket-based instant alerts
* Broadcast maintenance or security events
* Read/unread tracking

### ⏰ Automation

* Scheduled device commands
* Automated firmware updates with blockchain verification
* Compliance reporting

---

## 🏗️ System Architecture

**Request Flow:**
`Client → Go Router → Auth Middleware → Business Logic → MySQL → WebSocket → Response`

**Database Philosophy:**

* Normalized, ACID-compliant design
* Optimized for device & telemetry data
* Immutable audit logs

**Security Measures:**

* Input validation on all endpoints
* SQL injection prevention with prepared statements
* Rate limiting
* TLS encryption

---

## 📊 Database Schema

| Table         | Key Columns                                                                |
| ------------- | -------------------------------------------------------------------------- |
| users         | user\_id, username, email, password\_hash, role, 2fa\_enabled, created\_at |
| devices       | device\_id, public\_key, firmware\_version, status, registered\_at         |
| telemetry     | id, device\_id, data, timestamp                                            |
| commands      | command\_id, device\_id, payload, status, executed\_at                     |
| notifications | notification\_id, user\_id, message, is\_read, created\_at                 |
| audit\_logs   | log\_id, user\_id, action, details, ip\_address, timestamp                 |

---

## 🔌 API Layer

* RESTful endpoints with modular architecture
* JWT authentication and RBAC
* Swagger/OpenAPI documentation

**Example Endpoint:**

```
POST /api/devices/register
Headers: Authorization: Bearer <JWT>
Body:
{
  "device_id": "iot-001",
  "public_key": "0xABC..."
}
```

---

## 🎛️ Frontend (React.js)

* **Tech Stack:** React 18+, Context API, React Router, Chart.js/D3.js
* **Features:** Admin dashboard, telemetry charts, device mapping, exportable reports

**Structure:**

```
frontend/
├── public/
├── src/
│   ├── components/
│   ├── pages/
│   ├── services/
│   ├── utils/
│   ├── App.js
│   ├── index.js
│   └── styles.css
```

---

## 👥 User Roles & Permissions

| Role            | Permissions                                     |
| --------------- | ----------------------------------------------- |
| 🔧 Admin        | Full CRUD on devices, commands, telemetry, logs |
| 🧑‍💻 Developer | Test devices, view telemetry                    |
| 📡 Device       | Telemetry reporting, status updates             |
| 🔍 Auditor      | Read-only logs, blockchain records, telemetry   |

---

## 📈 Roadmap

| Phase      | Goals                                                                               |
| ---------- | ----------------------------------------------------------------------------------- |
| ✅ Phase 1  | Core MVP: Device registration, command push, React admin panel, WebSocket telemetry |
| 🔄 Phase 2 | Smart Control: Smart contract policies, scheduled firmware rollouts, auto-suspend   |
| 🚀 Phase 3 | Edge Intelligence: Anomaly detection, blockchain federation, ML integration         |

---

## 🚀 Quick Start

**Backend**

```bash
git clone https://github.com/MotionProgramming/BIoT-DM.git
cd BIoT-DM/backend
go mod tidy
cp .env.example .env
# Configure MySQL credentials
go run main.go
```

**Frontend**

```bash
cd ../frontend
npm install
npm start
```

**Access:**

* API: [http://localhost:5000/api](http://localhost:5000/api)
* UI: [http://localhost:3000](http://localhost:3000)

**Prerequisites:** Go 1.22+, Node.js 18+, MySQL, Ethereum PoA blockchain, Git

---

## 🔒 License & Usage

* **Educational Use:** Free for personal learning and study
* **Commercial Use:** License required; contact the developer
* **Security Disclaimer:** Not recommended for production without audit

---

👨‍💻 **Developer:** Md Abdullah Rajeeb
💻 GitHub: [MotionProgramming](https://github.com/MotionProgramming)

**Summary:** BIoT-DM is a **high-security, blockchain-enabled IoT device management platform** built with MySQL and native Go, designed for industrial-grade performance, auditability, and real-time control.

---
Do you want me to do that next?
