

> 🛡️ **Q-BIoT-DM**: Quantum-Resistant Blockchain-Based IoT Device Management System

---

### 📘 Project Overview

**Q-BIoT-DM** is a next-generation IoT management platform integrating **quantum-safe cryptography**, **blockchain auditability**, and **real-time telemetry**, purpose-built for **smart cities, critical infrastructure, and industrial IoT** in the post-quantum era.

---

### ⚙️ Architecture Overview

| Layer         | Technology                                           |
| ------------- | ---------------------------------------------------- |
| 🔙 Backend    | Go 1.22+ (No frameworks, net/http)                   |
| 🔐 Auth Layer | Post-Quantum Cryptography (SPHINCS+/Dilithium)       |
| 🧠 Identity   | Blockchain-based device identity (Quantum-Resistant) |
| 🛢 Database   | MySQL (ACID-compliant, normalized)                   |
| ⚡ Real-Time   | MQTT (IoT), WebSocket (Dashboard), TLS               |
| 🖥️ Frontend  | React.js 18+, Chart.js, Context API                  |
| ⛓ Blockchain  | Ethereum PoA with Post-Quantum Signature Layer       |
| 🧪 DevOps     | Docker, GitHub Actions, CI/CD                        |

---

### 🔑 Core Features (Quantum-Ready)

#### 🔐 Security

* Post-Quantum Signatures (SPHINCS+ or Dilithium) for device identity
* Multi-layered JWT + TOTP (2FA)
* RBAC (Admin, Developer, Device, Auditor)
* Blockchain-verified logs
* HTTPS/TLS, rate-limiting, and session controls

#### 🔄 Device Lifecycle Management

* Register, Activate, Suspend, Decommission devices
* Firmware versioning with **blockchain-based hash verification**
* Smart contract-controlled update policy

#### 🕵️ Blockchain-Powered Audit

* Immutable logs with quantum-safe signatures
* Auditor role with full access to verified logs
* Tamper-evident telemetry storage

#### ⚙️ Automation & Control

* Scheduled commands
* Smart contract–driven compliance actions
* Automated firmware rollback if integrity fails

#### 📊 Real-Time Analytics

* Live telemetry via WebSocket
* Categorized dashboard by device type, status, and location
* Export CSV/PDF

---

### 🧬 Post-Quantum Cryptography Stack

| Function                | Algorithm                        |
| ----------------------- | -------------------------------- |
| Device Signatures       | SPHINCS+ / Dilithium             |
| Auth Tokens             | JWT (HS256, optional PQ upgrade) |
| Firmware Integrity Hash | SHA3 / BLAKE3                    |
| Blockchain Signature    | Falcon / XMSS                    |

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

### 📊 Database Schema (Extra Columns for PQ Identity)

| Table       | Key Fields                                             |
| ----------- | ------------------------------------------------------ |
| users       | user\_id, username, password\_hash, role, 2fa\_enabled |
| devices     | device\_id, pq\_public\_key, firmware\_hash, status    |
| telemetry   | id, device\_id, data, timestamp                        |
| commands    | id, device\_id, command, status, signed\_by, ts        |
| audit\_logs | id, user\_id, action, pq\_signature, timestamp         |

---

### 🧑‍💻 User Roles & Permissions

| Role      | Permissions                                                 |
| --------- | ----------------------------------------------------------- |
| Admin     | Full device + user control, all audit logs                  |
| Developer | Can view devices, telemetry, push test commands             |
| Device    | Sends telemetry, receives signed commands, updates firmware |
| Auditor   | Can read blockchain audit logs, verify device compliance    |

---

### 🚀 Project Roadmap (Quantum Security Focused)

| Phase      | Goals                                                                        |
| ---------- | ---------------------------------------------------------------------------- |
| ✅ Phase 1  | Core MVP: Device registration, PQ signature auth, telemetry                  |
| 🔄 Phase 2 | Smart contracts for firmware control, quantum-proof consensus test           |
| 🔐 Phase 3 | Fully decentralized blockchain ID + blockchain federation (inter-chain logs) |
| 🧠 Phase 4 | AI-based quantum threat detection, anomaly logging                           |

---

### 🛠️ Quick Start

**Backend**

```bash
git clone https://github.com/QuantumSecure/Q-BIoT-DM.git
cd backend
go mod tidy
cp .env.example .env
go run main.go
```

**Frontend**

```bash
cd frontend
npm install
npm start
```

📍 Access:

* API: `http://localhost:5000/api`
* UI: `http://localhost:3000`

---

### 🔐 License

* **Educational Use**: Free
* **Enterprise Use**: License Required
* **Security Warning**: Pre-production; requires cryptographic audit

---

### 👨‍💻 Developer

> **Md Abdullah Rajeeb**
> 💼 GitHub: [MotionProgramming](https://github.com/MotionProgramming)
