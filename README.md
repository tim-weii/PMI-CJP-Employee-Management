##  PMI / CJP / Employee Management

[![VB.NET](https://img.shields.io/badge/VB.NET-Visual%20Basic-blueviolet?logo=dotnet)](https://learn.microsoft.com/en-us/dotnet/visual-basic/) 
[![VBA](https://img.shields.io/badge/VBA-Microsoft-green?logo=microsoft)](https://learn.microsoft.com/en-us/office/vba/api/overview/) 
[![PHP](https://img.shields.io/badge/PHP-8.0-blue?logo=php)](https://www.php.net/) 
[![MySQL](https://img.shields.io/badge/MySQL-8.0-blue?logo=mysql)](https://www.mysql.com/) 
[![RS485 MODBUS](https://img.shields.io/badge/RS485%20%20Modbus-Communication-orange)](https://modbus.org/) 
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

> The following screenshots illustrate the system’s **Human-Machine Interfaces (HMI)** and backend management tools:  
> **PMI (Production Management Interface)**, **CJP (Control & Job Processing)**, and the **Employee Management System**.  

---

- **PMI (Production Management Interface)** → Process planning & scheduling  
- **CJP (Control & Job Processing)** → Machine-level control & job dispatch  
- **Employee Management** → Personnel, shifts, and access control  

---

### 1) PMI — Production Management Interface

<p align="center">
<img width="677" height="424" alt="image" src="https://github.com/user-attachments/assets/ea4005cb-119b-4eea-9cc2-3eb7f025dade" />
</p>
<p align="center">〈Fig. PMI: Work orders, process planning, scheduling, WIP & KPI dashboards〉</p>

**Focus**:  
PMI handles **production planning and scheduling**, including workpiece design, drilling path planning, and progress monitoring.  

**Key Features**
- **Workpiece & Process Planning**: Import drawings, plan hole positions, dimensions, and machining sequences.  
- **Scheduling**: Generate plans based on order priority, deadlines, and process times; supports manual tuning and simulation.  
- **WIP Tracking**: Station entry/exit, takt times, bottleneck detection, and progress visualization.  
- **KPI Dashboard**: OEE, throughput, yield, and downtime analysis.  
- **Data Integration**: Syncs with CJP for machine data and with quality/inspection records.  

---

### 2) CJP — Control & Job Processing

<p align="center">
<img width="677" height="423" alt="image" src="https://github.com/user-attachments/assets/249fbcbc-f6c3-4b0d-9065-dc41d834d312" />
</p>
<p align="center">〈Fig. CJP: Machine control, job parameters, synchronization & alarms〉</p>

**Focus**:  
CJP is the **shop-floor control layer**, transforming PMI schedules into machine instructions and returning real-time feedback.  

**Key Features**
- **Parameter Setup**: Define length, quantity, and machining depth for each job.  
- **Real-Time Monitoring**: Collect machine parameters (speed, pressure, temperature), trigger threshold-based alarms.  
- **Job Dispatching**: Uses **Round-Robin / Priority Scheduling** for balanced and efficient job allocation.  
- **Multi-Machine Sync**: RS485 (half-duplex differential) + **Modbus protocol**, enabling long-distance synchronization.  
- **Alarm Handling**: Downtime management, recovery workflows, and feedback to PMI.  

---

### 3) Employee Management

<p align="center">
<img width="473" height="265" alt="image" src="https://github.com/user-attachments/assets/3a31ab7b-0d76-406c-8511-459bc2d66a98" />
</p>
<p align="center">〈Fig. Employee Management: Accounts, shifts, roles, audit trail〉</p>

**Focus**:  
This module manages **workforce, scheduling, and access control**, ensuring secure operations and optimized labor allocation.  

**Key Features**
- **RBAC (Role-Based Access Control)**: Operators / Engineers / Admin roles; permissions down to station level.  
- **Shift Management**: Planning, overtime, substitution; feeds into PMI for accurate scheduling.  
- **Skills & Certification**: Track qualifications and reminders for renewal.  
- **Audit Trail**: Logs of login, command execution, and parameter changes for compliance.  
- **Integration**:  
  - With **PMI** → Provides workforce/skills data for scheduling.  
  - With **CJP** → Restricts HMI operations by role/permission.  

---
