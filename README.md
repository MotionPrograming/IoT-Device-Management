# 🛡️ Q-BIoT-DM: Quantum-Resistant Blockchain-Based IoT Device Management System

**Status:** Active Development

**Developer:** Md Abdullah Rajeeb (MotionProgramming)

---

### 📘 Project Overview

Q-BIoT-DM is a cutting-edge IoT management platform built for the post-quantum era, integrating **quantum-safe cryptography**, **blockchain-powered auditability**, and **real-time telemetry**. It targets smart cities, critical infrastructure, and industrial IoT deployments.

---

### ⚙️ Architecture Overview

| Layer          | Technology                                      |
| -------------- | ----------------------------------------------- |
| Backend        | Go 1.22+ (net/http, no frameworks)              |
| Authentication | Post-Quantum Cryptography (SPHINCS+, Dilithium) |
| Identity       | Quantum-resistant blockchain-based device IDs   |
| Database       | MySQL (ACID-compliant, normalized schema)       |
| Real-Time      | MQTT (IoT), WebSocket (dashboard), TLS          |
| Frontend       | React.js 18+, Chart.js, Context API             |
| Blockchain     | Ethereum PoA with Post-Quantum Signature Layer  |
| DevOps         | Docker, GitHub Actions, CI/CD                   |

---

### 🔑 Core Features (Quantum-Ready)

* **Security:** PQ signatures for device identity, layered JWT + TOTP (2FA), RBAC (Admin, Developer, Device, Auditor), blockchain-verified logs, HTTPS/TLS security
* **Device Lifecycle:** Register, activate, suspend, decommission devices with blockchain-verified firmware versioning and smart contract update policies
* **Audit:** Immutable, tamper-evident logs with PQ signatures and auditor access
* **Automation:** Scheduled commands, smart contract–enforced compliance, automatic firmware rollback on integrity failure
* **Analytics:** Live telemetry via WebSocket, device status dashboards, exportable CSV/PDF reports

---

### 🧬 Post-Quantum Cryptography Stack

| Function              | Algorithms                            |
| --------------------- | ------------------------------------- |
| Device Signatures     | SPHINCS+, Dilithium                   |
| Auth Tokens           | JWT (HS256, with optional PQ upgrade) |
| Firmware Integrity    | SHA3, BLAKE3                          |
| Blockchain Signatures | Falcon, XMSS                          |

---

### 📈 System Architecture Diagram (Simplified)

```
Device → MQTT → Go Backend → MySQL + Blockchain → WebSocket → Frontend
                   ↓
          Post-Quantum Signature Verifier
                   ↓
          Blockchain Audit Logger
```

---

### 📊 Database Schema (Including PQ Identity Fields)

| Table       | Key Fields                                             |
| ----------- | ------------------------------------------------------ |
| users       | user\_id, username, password\_hash, role, 2fa\_enabled |
| devices     | device\_id, pq\_public\_key, firmware\_hash, status    |
| telemetry   | id, device\_id, data, timestamp                        |
| commands    | id, device\_id, command, status, signed\_by, timestamp |
| audit\_logs | id, user\_id, action, pq\_signature, timestamp         |

---

### 🧑‍💻 User Roles & Permissions

| Role      | Permissions                                               |
| --------- | --------------------------------------------------------- |
| Admin     | Full device and user management, all audit logs           |
| Developer | View devices, telemetry, push test commands               |
| Device    | Send telemetry, receive signed commands, firmware updates |
| Auditor   | Read blockchain audit logs, verify device compliance      |

---

### 🚀 Roadmap (Quantum Security Focused)

| Phase      | Goals                                                                 |
| ---------- | --------------------------------------------------------------------- |
| Phase 1 ✅  | Core MVP: device registration, PQ signature authentication, telemetry |
| Phase 2 🔄 | Smart contracts for firmware control, quantum-proof consensus testing |
| Phase 3 🔐 | Decentralized blockchain ID and federation (cross-chain logs)         |
| Phase 4 🧠 | AI-driven quantum threat detection and anomaly logging                |

---

### 🛠️ Quick Start

**Backend Setup**

```bash
git clone https://github.com/QuantumSecure/Q-BIoT-DM.git
cd backend
go mod tidy
cp .env.example .env
go run main.go
```

**Frontend Setup**

```bash
cd frontend
npm install
npm start
```

**Access**

* API: `http://localhost:5000/api`
* UI: `http://localhost:3000`

---

### 🔐 License

* **Educational Use:** Free
* **Enterprise Use:** License required
* **Security Notice:** Pre-production; cryptographic audit needed before production use

---

### 👨‍💻 Developer

Md Abdullah Rajeeb
GitHub: [MotionProgramming](https://github.com/MotionProgramming)

---
