##  PMI / CJP / Employee Management

> The following screenshots illustrate the system’s **Human-Machine Interfaces (HMI)** and backend management tools:  
> **PMI (Production Management Interface)**, **CJP (Control & Job Processing)**, and the **Employee Management System**.  
> Together, they form a closed-loop flow of **Management → Control → Personnel**, supported by RS485 + Modbus communication, real-time scheduling, and database integration.

---

### 1) PMI — Production Management Interface

<p align="center">
<img width="677" height="424" alt="image" src="https://github.com/user-attachments/assets/13423e88-d049-48c1-96e4-b2a342da398d" />
</p>
<p align="center">〈Fig: PMI interface (orders, scheduling, WIP tracking, KPI dashboard)〉</p>

**Focus**: Planning and management layer. Provides order/work order tracking, production scheduling, WIP (Work-In-Progress), and KPI dashboards.  

**Key Features**
- **Scheduling**: Generate plans based on order priority, due dates, and process times. Supports manual fine-tuning and scenario simulation.  
- **WIP Tracking**: Station entry/exit, takt times, yield, and bottleneck analysis.  
- **KPI Dashboard**: OEE, throughput, yield, and downtime analysis.  
- **Data Integration**: Syncs with CJP for equipment data and with quality/inspection records.  

**Integration**
- Sends work orders and schedules to **CJP**; receives machine status, output, and alarms.  
- Syncs with **Employee Management** for workforce assignments and responsibility tracking.  

---

### 2) CJP — Control & Job Processing

<p align="center">
<img width="677" height="423" alt="image" src="https://github.com/user-attachments/assets/0c412521-62ed-4270-afb0-69388be67fb1" />
</p>
<p align="center">〈Fig: CJP interface (machine status, job dispatch, alarm monitoring)〉</p>

**Focus**: Shop-floor control layer. Directly connects to machines for job dispatching, recipe download, monitoring, and alarm handling.  

**Key Features**
- **Communication**: RS485 (half-duplex differential) + **Modbus protocol**, enabling long-distance multi-machine synchronization.  
- **Job Dispatch**: Implements **Round-Robin / Priority Scheduling** for fair and efficient task allocation.  
- **Parameter Monitoring**: Real-time collection of temperature, pressure, speed, etc. Triggers threshold-based alarms.  
- **Alarm Handling**: Downtime/recovery workflows, alarm classification, and feedback to work orders (pause/rework/scrap).  

**Integration**
- Receives schedules and orders from **PMI**, returns real-time production results.  
- Authenticates user access via **Employee Management** (role-based HMI access).  

---

### 3) Employee Management System

<p align="center">
<img width="473" height="265" alt="image" src="https://github.com/user-attachments/assets/63e1ab83-894e-41b4-8ad8-a7b1ced017d3" />
</p>
<p align="center">〈Fig: Employee Management interface (users, shifts, roles, audit trail)〉</p>

**Focus**: Personnel and access control. Provides accounts, shift scheduling, skill certification, and audit logging.  

**Key Features**
- **RBAC (Role-Based Access Control)**: Operator / Engineer / Admin tiers; permissions down to machine or station level.  
- **Shift Management**: Scheduling, overtime, and substitutions; feeds into **PMI** for workforce planning.  
- **Skills & Training**: Certification tracking, renewal reminders, qualification management.  
- **Audit Trail**: Logs login, command execution, and parameter changes for traceability and compliance.  

**Integration**
- Provides login/authorization for **CJP HMI**; restricts commands by user role.  
- Feeds workforce and skill availability to **PMI** for accurate scheduling.  

---

## 🔗 System Data Flow (Overview)

1. **CJP** exchanges machine data (status, parameters, alarms) via RS485 + Modbus and dispatches jobs using **Round-Robin / Priority Scheduling**.  
2. **PMI** sends work orders and schedules, collects CJP feedback (output, downtime), and updates **WIP/KPI dashboards**.  
3. **Employee Management** controls login, permissions, and skill/shift data, constraining both CJP operations and PMI scheduling.  

Together they form a closed loop:  
**Planning (PMI) → Control (CJP) → Feedback (Results & Personnel) → Re-planning (PMI)**, ensuring production stability and traceability.

---

## ✅ Suggested Captions (for quick reference under each figure)
- `PMI: Production Management interface for orders, scheduling, WIP, and KPI dashboards.`  
- `CJP: Production Control interface for real-time job dispatch and monitoring (RS485 + Modbus).`  
- `Employee Management: User, shift, and permission system with full audit trail.`
