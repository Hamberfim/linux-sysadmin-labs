# Linux-Sysadmin-Labs

## Enterprise Linux System Administration & Infrastructure Lab Portfolio

Welcome to my infrastructure portfolio. This repository documents a comprehensive, 12-phase technical curriculum designed to build, secure, and monitor modern IT infrastructure. The practical labs, configurations, and automation scripts housed here demonstrate production-ready proficiencies required for hybrid Enterprise IT Support and Linux System Administration roles.

## ⚠️ Portfolio Status: Active & In-Progress
*This repository is a live workspace being updated in real-time as I progress. It serves as an architectural blueprint for my active roadmap. *

## 🚀 Core Technical Focus Areas
* **Linux System Administration:** Operational fluency in enterprise RHEL-compatible environments (AlmaLinux) and Debian/Ubuntu Server ecosystems.
* **IT Support & Troubleshooting:** Structured root-cause log analysis, automated system diagnostics via Bash scripting, and technical ticketing runbooks.
* **Networking & Firewalls:** Implementation of secure routing, multi-site network logic, and edge firewall security policies.
* **Cloud & Identity Infrastructure:** Hybrid directory services management utilizing AWS VPCs, EC2 architectures, and cloud identity management platform lifecycles.

## 🛠️ Sandbox Lab Architecture
All projects are staged, tested, debugged, and documented inside a multi-node hypervisor infrastructure to mimic true enterprise deployments.

* **`admin01` (AlmaLinux):** Primary operations server (User management, systemd services, secure SSH access).
* **`dns01`  (AlmaLinux):** Authoritative internal network DNS provider utilizing `BIND`.
* **`web01`  (AlmaLinux):** Production-grade reverse proxy and web-host utilizing `Nginx`.
* **`client01` (Ubuntu Desktop):** Diagnostic tier-1 test workstation simulating remote end-user environments.

## 📂 Curriculum & Project Breakdown Plan - Element to Come

### [Phase 1: Linux Foundations](./Phase-01-Foundations/)
* **Focus:** Command-line diagnostics, log file navigation (`/var/log/`), and remote support prerequisites.
* **Featured Deliverable:** [Real Project 1: Linux Health Inspection Script](./Phase-01-Foundations/healthcheck.sh) - A Bash script gathering critical runtime metrics (IP, disk, memory, uptime) and outputting formatted diagnostic payloads.

### [Phase 2: Files, Permissions, & Identity Auditing](./Phase-02-Permissions/)
* **Focus:** POSIX permissions, ownership allocation, and securing multi-tenant infrastructure.
* **Featured Deliverable:** [Real Project 2: Role-Based Access Model](./Phase-02-Permissions/access_model.md) - Design architecture logic configuring secure ACLs (`chmod`/`chown`) restricting proprietary data directories exclusively to active operations and support staff.

### [Phase 3: Text Processing & Security Incident Investigation](./Phase-03-TextProcessing/)
* **Focus:** Data extraction via `grep`, `sed`, and `awk` to parse verbose service outputs.
* **Featured Deliverable:** [Real Project 3: Brute-Force Log Analysis Report](./Phase-03-TextProcessing/incident_report.md) - A security escalation audit analyzing authentication logs to track, count, and isolate malicious persistent IP addresses.

### [Phase 4: Process Management & Performance Analysis](./Phase-04-ProcessManagement/)
* **Focus:** Kernel status tracking, memory leak profiling, and service orchestration via `top`, `ps`, and `kill`.
* **Featured Deliverable:** [Real Project 4: Application Server Root-Cause Document](./Phase-04-ProcessManagement/rca_report.md) - A technical summary breaking down a simulated application hang, zombie process capture, and performance mitigation steps.

### [Phase 5: Shell Scripting & Infrastructure Automation](./Phase-05-ShellScripting/)
* **Focus:** Variables, loops, and error-handling matrices to handle repetitive system audits.
* **Featured Deliverable:** [Real Project 5: Daily Infrastructure Audit Tool](./Phase-05-ShellScripting/daily_audit.sh) - An automated script evaluating disk constraints, parsing critical service uptimes, and prepping automated status reports.

### [Phase 6: Enterprise Networking & Firewalls](./Phase-06-Networking/)
* **Focus:** Deep troubleshooting of the TCP/IP stack (`ip`, `route`, `dig`, `traceroute`).
* **Featured Deliverable:** [Real Project 6: Multi-Site Hybrid Network Architecture](./Phase-06-Networking/network_map.md) - Comprehensive mapping document aligning a local Office LAN through an edge firewall interface, over a secure VPN Gateway, directly into a cloud backend.

### [Phase 7: Production Service Hardening](./Phase-07-LinuxAdmin/)
* **Focus:** Systemd target orchestration, boot sequence logging, and package dependency management.
* **Featured Deliverable:** [Real Project 7: Production Web Server Build Guide](./Phase-07-LinuxAdmin/nginx_hardening.md) - A step-by-step technical standard operating procedure (SOP) deploying an audited, high-availability Nginx deployment.

### [Phase 8: Cloud Infrastructure Administration](./Phase-08-AWS/)
* **Focus:** Cloud security groups, elastic compute nodes, and multi-tier Virtual Private Clouds (VPC).
* **Featured Deliverable:** [Real Project 8: Secure Cloud Architecture](./Phase-08-AWS/vpc_setup.md) - Infrastructure map separating private backend subnets from public ingress pathways via a dedicated bastion host.

### [Phase 9: Identity & Directory Services](./Phase-09-Identity/)
* **Focus:** User provisioning lifecycles, enterprise mailbox handling, and strict Role-Based Access Control (RBAC) policies.
* **Featured Deliverable:** [Real Project 9: Automated Onboarding Lifecycle](./Phase-09-Identity/user_lifecycle.md) - Standardized workflow automating organizational group mapping, software seat licensing, and formal offboarding strategies.

### [Phase 10: Security Operations & Centralized Logging](./Phase-10-Security/)
* **Focus:** Network monitoring footprint reductions, explicit software firewalls, and persistent auditing.
* **Featured Deliverable:** [Real Project 10: Small SOC Environment Baseline](./Phase-10-Security/soc_setup.md) - Implementation plan deploying a unified log aggregation node tracking remote authentication attempts and system events.

### [Phase 11: Enterprise Virtualization Sandboxing](./Phase-11-Virtualization/)
* **Focus:** Hypervisor resource optimization, snapshot policies, and data-center cluster modeling.
* **Featured Deliverable:** [Real Project 11: Simulated On-Premises Data Center](./Phase-11-Virtualization/datacenter_sim.md) - A multi-VM local laboratory managing a central Directory Services Controller, dedicated internal DNS nodes, and an enterprise Linux processing environment.

### [Phase 12: Standard Operating Procedures Portfolio](./Phase-12-Documentation/)
* **Focus:** Professional documentation designed to be transferred cleanly into corporate knowledge bases.
* **Featured Deliverable:** [The Enterprise IT Technician Support Playbook](./Phase-12-Documentation/playbook/) - A collection of production-ready operational runbooks including:
  1. *Linux Provisioning & Server Hardening Standard*
  2. *Cloud Identity Multi-Tenant Provisioning Procedure*
  3. *Enterprise Firewall Change Request Checklist*
  4. *Proprietary Hardware Device Diagnostic & Recovery Runbook*

## 📈 Final Capstone Project: Complete Enterprise Ecosystem
The culmination of this curriculum integrates an active firewall interface routing local client networks safely over encrypted links to a cloud VPC environment, managed alongside modern identity standards, and validated via persistent incident response mock testing.

---
*This repository represents active, practical documentation of a rigorous engineering skillset.*
