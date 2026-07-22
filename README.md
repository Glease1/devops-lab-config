Ryan's DevOps Infrastructure Lab
This repository documents the evolution of a professional DevOps homelab. The objective is to build a scalable, remote-managed development environment that mirrors real-world IT service desk and engineering workflows.

Workflow Philosophy
The goal of this lab is to achieve environment parity. The Windows host acts as the primary IDE and development environment, while the Linux node serves as an isolated test-bed. This ensures that code developed locally is verified against a production-like Linux environment before being considered deployment-ready.

Architecture: Native Execution Approach
To ensure system stability and optimize resource usage on the target node, this lab follows a Native Execution pattern. Applications are deployed directly to the Linux environment using automated synchronization rather than containerization. This approach allows for realistic performance testing and deeper familiarity with Linux service management (systemd) and native environment configuration.

The Stack
Control Plane (Host): Windows 11 Professional. Role: Primary development workstation, CLI management, and orchestration hub.

Target Infrastructure (Node): HP ProBook 430 G7 running Linux Mint. Role: Headless production-style server for testing services and automation.

Connectivity and Management
Primary Access: OpenSSH (Headless terminal access) — Validated.

IDE: VS Code (via Remote-SSH extension) — Validated.

Recovery: Parsec (for GUI-level diagnostic access).

Key Objectives
The focus is on transitioning from manual configuration to Infrastructure as Code (IaC) to practice the following:

Remote Administration: Managing Linux environments without physical keyboard or monitor interaction.

Configuration Management: Moving from ad-hoc setup to repeatable, automated provisioning.

Cross-Platform Workflow: Bridging Windows 11 and Linux ecosystems to create a seamless developer experience.

Roadmap
[x] Phase 1: Foundation - Stabilize SSH connectivity, SSH key authentication, and remote VS Code integration.

[x] Phase 2: Native Deployment - Configure the Linux node for C# execution and implement systemd service management.

[ ] Phase 3: Automation - Implement Ansible playbooks for automated server provisioning.

[ ] Phase 4: Observability - Deploy a Prometheus/Grafana stack to monitor system performance.

[ ] Phase 5: CI/CD - Build a GitHub Actions pipeline that automates deployment.

Deployment Strategy
Code is maintained in a central GitHub repository. The Linux node uses SSH-based authentication to pull the latest code directly.

Authentication: Managed via Ed25519 SSH keys. (Currently transitioning from password-based to passwordless authentication).

Workflow: Code is developed on the Windows host, pushed to GitHub, and pulled natively onto the Linux node for testing.

Node Configuration: .NET Runtime
Status: Installed.

Version: .NET SDK 8.0.

Method: Official Microsoft APT Repository.

Purpose: Enables native execution of C# utility projects, allowing for performance benchmarking and testing directly on the Linux target without container overhead.
