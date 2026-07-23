Ryan’s DevOps Infrastructure Lab

A practical DevOps homelab built around a Windows workstation and a headless Linux Mint server.

The aim is to practise real administration and DevOps workflows: remote access, Linux configuration, Infrastructure as Code, native application testing, monitoring, and CI/CD.

## Setup

| System | Role |
|---|---|
| Windows 11 Pro PC | Main development machine, VS Code, Git, Ansible control node |
| HP ProBook 430 G7, Linux Mint | Headless Linux server used for testing, automation, and services |

The Linux machine is not used as a normal laptop. It runs headlessly and is managed remotely through SSH, VS Code Remote-SSH, and Ansible. Parsec is available only if GUI recovery is needed.

## Workflow

1. Develop code on Windows.
2. Commit and push changes to GitHub.
3. Pull code onto the Linux node.
4. Test it natively on Linux.
5. Use Ansible to keep the server configuration repeatable.

The lab currently uses native execution rather than containers. This keeps the Linux server lightweight and provides hands-on experience with Linux packages, services, permissions, SSH, and application deployment.

## Tools

- Windows 11 Professional
- Linux Mint
- OpenSSH
- VS Code Remote-SSH
- Ansible
- Git and GitHub
- Python 3.12
- .NET SDK 8.0
- Parsec for recovery access

## Completed Work

### Phase 1 — Foundation

- Configured SSH access to the Linux node
- Set up Ed25519 SSH key authentication
- Validated headless terminal access
- Connected through VS Code Remote-SSH

### Phase 2 — Native Deployment

- Installed .NET SDK 8.0 using the Microsoft APT repository
- Prepared the Linux node to run C# utilities and projects natively
- Established a Windows-to-Linux development and testing workflow

### Phase 3 — Ansible Automation

- Created an Ansible inventory for the Linux node
- Configured Ansible SSH authentication
- Built a role-based provisioning structure
- Used Ansible to manage packages, services, Python tooling, and directories
- Used sudo privilege escalation without storing passwords in the inventory
- Validated connectivity with Ansible ping
- Confirmed the playbook is idempotent

Successful connectivity test:

```text
device | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
```

First provisioning run:

```text
device : ok=13 changed=4 unreachable=0 failed=0
```

Second provisioning run:

```text
device : ok=13 changed=0 unreachable=0 failed=0
```

The second run made no changes, confirming that the configuration can be safely rerun.

## Ansible

The Ansible project is located at:

```text
~/EnterpriseCloudAdmin/Ansible
```

Run the baseline playbook with:

```bash
cd ~/EnterpriseCloudAdmin/Ansible
ansible-playbook -i inventory.ini site.yml --ask-become-pass
```

## Roadmap

- [x] Phase 1: SSH, SSH keys, and VS Code Remote-SSH
- [x] Phase 2: Native .NET deployment environment
- [x] Phase 3: Ansible provisioning and repeatable configuration
- [ ] Phase 4: Prometheus, Node Exporter, and Grafana monitoring
- [ ] Phase 5: GitHub Actions CI/CD pipeline

## What I’m Practising

- Headless Linux administration
- SSH troubleshooting and key authentication
- Remote development workflows
- Ansible inventories, playbooks, roles, and privilege escalation
- Idempotent Infrastructure as Code
- Linux package and service management
- Native .NET testing on Linux
- Git-based deployment workflows
- Monitoring and CI/CD design
