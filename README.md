Ryan's DevOps Infrastructure Lab
This repository documents the evolution of my professional DevOps homelab. The goal is to build a scalable, remote-managed development environment that mirrors real-world IT service desk and engineering workflows.

Workflow Philosophy
The goal of this lab is to achieve environment parity. The Windows Host acts as the primary IDE and development environment, while the Linux Node serves as an isolated test-bed. This ensures that code developed locally is verified against a production-like Linux environment before being considered "ready."

Architecture Note: Native Execution Approach
To ensure system stability and optimize resource usage on the target node, this lab follows a Native Execution pattern. Instead of containerization, applications are deployed directly to the Linux environment using automated synchronization. This allows for realistic performance testing and deeper familiarity with Linux service management (systemd) and native environment configuration.

The Stack
Control Plane (Host): Windows 11 Professional

Role: Primary development workstation, CLI management, and orchestration hub.

Target Infrastructure (Node): HP ProBook 430 G7 running Linux Mint

Role: Headless production-style server for testing services and automation.

Connectivity & Management
Primary: OpenSSH (Headless terminal access) — Validated

IDE: VS Code (via Remote-SSH extension) — Validated

Recovery: Parsec (for GUI-level diagnostic access)

Key Objectives
My focus is on shifting from manual configuration to Infrastructure as Code (IaC). This lab is built to practice:

Remote Administration: Managing Linux environments without physical keyboard/monitor interaction.

Configuration Management: Moving from ad-hoc setup to repeatable, automated provisioning.

Cross-Platform Workflow: Bridging Windows 11 and Linux ecosystems to create a seamless developer experience.

Roadmap
[x] Phase 1: Foundation - Stabilize SSH connectivity, SSH key auth, and remote VS Code integration.

[ ] Phase 2: Native Deployment - Configure the Linux Node for C# execution and implement systemd service management.

[ ] Phase 3: Automation - Implement Ansible playbooks for automated server provisioning.

[ ] Phase 4: Observability - Deploy a Prometheus/Grafana stack to monitor system performance.

[ ] Phase 5: CI/CD - Build a GitHub Actions pipeline that automates deployment to "Ryan."

Deployment Strategy
Code is maintained in a central GitHub repository. The Linux Node uses SSH-based authentication to pull the latest code directly.

Authentication: Managed via Ed25519 SSH keys for passwordless synchronization.

Workflow: Code is developed on the Windows Host, pushed to GitHub, and pulled natively onto the Linux Node for testing.

Node Configuration: .NET Runtime
Status: Installed
Version: .NET SDK 8.0
Method: Official Microsoft APT Repository
Purpose: Enables native execution of C# utility projects, allowing for performance benchmarking and testing directly on the Linux target without container overhead.
