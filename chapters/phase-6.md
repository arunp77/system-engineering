## 7. Phase 6 — Operations Engineering and System Monitoring (Months 9–12)

### 7.1 Overview

Operations engineering is the discipline of preparing, supporting, and optimising the operational use of a system. At EUMETSAT, this covers everything from preparing for the launch of a new satellite through to monitoring the daily performance of all operational systems and managing anomalies. It is particularly relevant to the "System Operations Engineer" and "Operations Preparation Engineer" roles.

### 7.2 Mission Operations Concepts

**Launch and Early Operations Phase (LEOP)**

LEOP begins at launch and covers the first days to weeks of a satellite's life, during which it is deployed from the launch vehicle, initial telemetry is acquired, the satellite is activated and stabilised, instruments are switched on for the first time, and initial orbit manoeuvres are performed. LEOP is the highest-risk phase of a mission. Systems engineers involved in LEOP must understand the satellite's modes, contingency procedures, and the decision-making process under real-time operational constraints.

**In-Orbit Commissioning (IOC)**

After LEOP, the satellite enters commissioning, during which all instruments are fully characterised, calibrated, and validated. IOC can last from several months to over a year for complex missions like MTG. During IOC, the operations procedures developed during operations preparation are executed for the first time in the real operational environment.

**Routine Operations**

Once a mission is declared operational, it enters routine operations — the continuous 24/7 cycle of satellite monitoring, data acquisition, product generation, and delivery. Systems engineers support routine operations by maintaining and improving monitoring systems, resolving anomalies, and managing ground system updates.

### 7.3 Operations Preparation

Operations preparation is the work done before launch to ensure that the mission can be operated safely and effectively once in orbit. It is a major SE activity covering:

**Operations Concept Definition**: Describing how the system will be operated at a high level — orbital manoeuvre strategy, instrument scheduling philosophy, contact scheduling, degraded mode operations.

**Operations Procedures Development**: Writing detailed step-by-step procedures for all foreseeable operational tasks — nominal operations, contingency operations, maintenance activities. These procedures must be verified through simulation before launch.

**Timeline Development**: Defining the repeating schedule of operations activities — contact windows, calibration sequences, housekeeping data dumps, orbit manoeuvres.

**Simulation and Rehearsal**: Testing operations procedures against spacecraft simulators and ground segment test environments before launch. Critical for anomaly response procedures.

### 7.4 SCOS-2000

SCOS-2000 (Satellite Control and Operations System) is the mission control system standard developed by ESA and used at EUMETSAT and other European space agencies for spacecraft monitoring and control. Knowledge of SCOS is explicitly required in EUMETSAT operations engineering job postings.

SCOS-2000 provides capabilities for: receiving and processing satellite telemetry, sending telecommands, managing command sequences, event-driven automation (on-board and ground), and historical telemetry archiving and playback.

Understanding SCOS from a systems engineer's perspective means knowing how to: define the Mission Database (MDB) that describes the satellite's telemetry parameters and commands, define monitoring rules and event triggers, design command sequences, and interface SCOS with other ground segment elements.

### 7.5 System Monitoring

End-to-end system monitoring is the capability to observe the health and performance of all elements of the EUMETSAT system — space segment, ground stations, data processing, and dissemination — and to detect and react to anomalies before they impact operational services.

From a SE perspective, system monitoring has its own requirements, architecture, and V&V process. Key aspects include:

**Mission Performance Monitoring**: Tracking product quality indicators (timeliness, completeness, accuracy) against service commitments defined in Service Level Specifications (SLS). Your Python and SQL skills are directly applicable to developing performance monitoring dashboards, automated quality checking scripts, and reporting tools.

**Telemetry Monitoring**: Watching satellite housekeeping parameters (temperatures, voltages, currents, event counters) for out-of-limit conditions. Requires defining nominal ranges, defining alert thresholds, and designing escalation procedures.

**Ground Segment Monitoring**: Monitoring the health of all ground-based systems — servers, networks, processing pipelines, storage systems, and communication links.

**Harmonised Monitoring Across Missions**: A key challenge at EUMETSAT is harmonising monitoring tools and metrics across a growing fleet of diverse missions. This is an active engineering area and an opportunity for Python-driven automation and tooling.