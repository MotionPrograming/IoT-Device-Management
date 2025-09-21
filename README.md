# 🛡️ BIoT-DM: Blockchain-Based IoT Device Management System

[![Go Version](https://img.shields.io/badge/Go-1.22+-00ADD8)](https://golang.org/)
[![React Version](https://img.shields.io/badge/React-18+-61DAFB)](https://reactjs.org/)
[![License](https://img.shields.io/badge/License-Educational-lightgrey)](LICENSE)

📡 **Status:** Active Development

👨‍💻 **Developer:** Md Abdullah Rajeeb (MotionProgramming)

🏗️ **Architecture:** Native Go Backend + MySQL Database + React.js Frontend + Ethereum PoA Blockchain

---

## 📘 Project Overview

**BIoT-DM** is a **high-security, enterprise-grade IoT device management platform** built for:

* Smart cities, industrial IoT, and critical IIoT environments
* Blockchain-based device identity verification and zero-trust security
* Real-time device telemetry monitoring via WebSocket/MQTT
* Immutable audit logging for operational and regulatory compliance

> Built from scratch for **performance, transparency, and full control**. Minimal dependencies and fully extensible.

---

## 🎯 Core Objectives

**Security & Compliance**

* Blockchain-based device identity and immutable logs
* JWT authentication for all API endpoints
* Role-based access control (Admin, Developer, Auditor, Device)

**Performance & Reliability**

* High-performance Go backend with concurrent request handling
* Sub-100ms response times for device queries and telemetry
* Scalable architecture with zero-downtime deployments

**User Experience**

* Real-time dashboards for device monitoring
* Multi-device support (web, tablet, desktop)
* Interactive analytics and reporting

---

## 🛠️ Technology Stack

| Layer              | Technology Stack                                      |
| ------------------ | ----------------------------------------------------- |
| Backend Language   | Go 1.22+ (Standard Library, no frameworks)            |
| HTTP Routing       | `net/http`, `http.ServeMux`                           |
| Authentication     | JWT (HS256) with SHA-256 password hashing             |
| Database           | MySQL (ACID-compliant, optimized queries)             |
| Blockchain         | Ethereum PoA (private chain)                          |
| Real-Time Comm     | MQTT (IoT devices), WebSocket (dashboard) TLS-secured |
| Frontend UI        | React.js 18+                                          |
| Data Visualization | Chart.js / D3.js                                      |
| API Documentation  | Swagger/OpenAPI                                       |
| DevOps             | Docker & Docker Compose, GitHub Actions CI/CD         |
| Security           | HTTPS/TLS, Input validation, Rate limiting, RBAC      |

---

## ✨ Core Features & Capabilities

### 🔐 Authentication & Security

* Multi-layer JWT authentication
* Two-Factor Authentication (2FA) using TOTP
* Role-based access control (Admin, Developer, Auditor, Device)
* Session management with auto-expiration and concurrency control

### 💻 Device Management

* Device registration, activation, suspension, decommission
* Firmware versioning with **on-chain hash verification**
* Real-time telemetry ingestion & visualization
* Device status monitoring and alerting

### 💸 Transaction & Command Engine

* Send commands to devices securely and atomically
* Filter commands and telemetry by device, type, or time
* Audit logs with IP tracking, timestamps, and blockchain verification

### 📊 Analytics & Dashboard

* Real-time telemetry visualization
* Categorized analytics for device types and regions
* Exportable CSV/PDF reports
* Admin dashboards with system health and user activity metrics

### ⚡ Real-Time Notifications

* WebSocket-powered instant alerts
* System-wide broadcasts for maintenance or security events
* Read/unread notification tracking

### ⏰ Automated Operations

* Scheduled commands for devices
* Automated firmware updates and blockchain verification
* Compliance reporting for regulatory purposes

---

## 🏗️ System Architecture

**Request Flow**

```
Client → Go Router → Auth Middleware → Business Logic → MySQL Database → WebSocket → Response
```

**Database Design Philosophy**

* Normalized relational design optimized for device & telemetry data
* ACID-compliant transactions ensuring consistency and reliability
* Audit logs stored immutably for security and traceability

**Security Implementation**

* Input validation at all API endpoints
* SQL injection prevention via prepared statements and ORM protections
* Rate limiting to prevent abuse
* TLS encryption for transport

---

## 📊 Database Schema Overview

**Core Tables**

* `users`: user\_id, username, email, password\_hash, role, 2fa\_enabled, created\_at
* `devices`: device\_id, public\_key, firmware\_version, status, registered\_at
* `telemetry`: id, device\_id, data, timestamp
* `commands`: command\_id, device\_id, payload, status, executed\_at
* `notifications`: notification\_id, user\_id, message, is\_read, created\_at
* `audit_logs`: log\_id, user\_id, action, details, ip\_address, timestamp

---

## 🔌 API Layer

* RESTful endpoints with modular architecture
* JWT authentication + Role-based access control
* Swagger/OpenAPI spec for development and testing

**Sample Endpoint:**

```http
POST /api/devices/register
Headers: Authorization: Bearer <JWT>
Body: {
  "device_id": "iot-001",
  "public_key": "0xABC..."
}
```

---

## 🎛️ Frontend (React.js)

**Tech Stack**: React 18+, Context API, React Router, Chart.js / D3.js

**Features**:

* Admin dashboard for device management
* Telemetry charts, device mapping
* Export logs & reports (CSV/PDF)

**Frontend Structure**:

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

| Phase      | Goals                                                                                       |
| ---------- | ------------------------------------------------------------------------------------------- |
| ✅ Phase 1  | Core MVP: Device registration, command push, React admin panel, WebSocket telemetry         |
| 🔄 Phase 2 | Smart Control: Smart contract policy enforcement, scheduled firmware rollouts, auto-suspend |
| 🚀 Phase 3 | Edge Intelligence: Anomaly detection, blockchain federation, ML integration                 |

---

## 🚀 Quick Start Guide

### Backend (Go)

```bash
git clone https://github.com/MotionProgramming/BIoT-DM.git
cd BIoT-DM/backend
go mod tidy
cp .env.example .env
# Configure MySQL credentials in .env
go run main.go
```

### Frontend (React.js)

```bash
cd ../frontend
npm install
npm start
```

**Access:**

* API: `http://localhost:5000/api`
* UI: `http://localhost:3000`

**Prerequisites:**

* Go 1.22+
* Node.js 18+
* MySQL
* Ethereum PoA blockchain
* Git

---

## 🔒 License & Usage

* **Educational Use Only:** Free for personal learning, study, and non-commercial academic purposes.
* **Commercial Use:** License required for production or commercial deployment. Contact the developer.
* **Security Disclaimer:** Not recommended for production without security audit.

---

## 👨‍💻 Developed By

**Md Abdullah Rajeeb**
💻 GitHub: [MotionProgramming](https://github.com/MotionProgramming)
📧 [contact@motionprogramming.dev](mailto:contact@motionprogramming.dev)

> *BIoT-DM: High-Security Blockchain IoT Device Management with MySQL & Native Go.*

