Ryan's DevOps Infrastructure Lab
This repository documents the evolution of my professional DevOps homelab. The goal is to build a scalable, remote-managed development environment that mirrors real-world IT service desk and engineering workflows.

Core Architecture
I operate a Cross-Platform Control-Plane architecture. This setup separates my "Control Plane" (where I do the work) from my "Target Infrastructure" (where the services run).

The Stack
Control Plane (Host): Windows 11 Professional

Role: Primary development workstation, CLI management, and orchestration hub.

Target Infrastructure (Node): HP ProBook 430 G7 running Linux Mint

Role: Headless production-style server for testing services, containerization, and automation.

Connectivity & Management:

Primary: OpenSSH (Headless terminal access).

IDE: VS Code (via Remote-SSH extension).

Recovery: Parsec (for GUI-level diagnostic access).

Key Objectives
My focus is on shifting from manual configuration to Infrastructure as Code (IaC). This lab is built to practice:

Remote Administration: Managing Linux environments without physical keyboard/monitor interaction.

Configuration Management: Moving from ad-hoc setup to repeatable, automated provisioning.

Cross-Platform Workflow: Bridging Windows 11 and Linux ecosystems to create a seamless developer experience.

Roadmap
[X] Phase 1: Foundation - Stabilize SSH connectivity, SSH key auth, and remote VS Code integration.

[ ] Phase 2: Containerization - Migrate existing C# utility projects (Calculator, BMI) into Docker containers.

[ ] Phase 3: Automation - Implement Ansible playbooks for automated server provisioning.

[ ] Phase 4: Observability - Deploy a Prometheus/Grafana stack to monitor system performance.

[ ] Phase 5: CI/CD - Build a GitHub Actions pipeline that automates deployment to "Ryan."

## Current Status
**Phase 1 Complete:** The Control Plane (Windows 11) is fully integrated with the Target Infrastructure (Linux Mint) via SSH. Remote development via VS Code is operational. Currently transitioning to Phase 2 (Containerization).

### Connectivity & Management
*   **Primary:** OpenSSH (Headless terminal access) — **Validated**
*   **IDE:** VS Code (via Remote-SSH extension) — **Validated**
*   **Recovery:** Parsec (for GUI-level diagnostic access)
