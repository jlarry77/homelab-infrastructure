# Homelab Infrastructure & Automation Project

![Grafana Dashboard](https://github.com/your-username/your-repo-name/blob/main/path-to-your-screenshot.png)

## Overview
This homelab serves as a personal DevOps and Systems Administration playground — enabling continuous learning, full-stack experimentation, and self-hosted infrastructure. It supports the following real-world use cases:

- Hosts business web services using a Cloudflare Tunnel
- Provides remote access to a personal file server
- Enables performance, resource, and metric monitoring
- Supports container orchestration, scripting, and automation
- Facilitates network segmentation and security projects

My technical focus is on **DevOps, Systems Administration, metrics analysis, and networking**.

---

## 🔧 Infrastructure Overview

This project runs on a **4-node Proxmox VE cluster** with additional standalone machines. All hardware has been refurbished, upgraded with SSDs, NVMe, RAM, and cooling enhancements.

### Proxmox Cluster:
1. **deathStar** (Lenovo ThinkCentre 710 MT)
   - 500GB HDD, 500GB SSD, 500GB NVMe
   - 16GB RAM, Intel i5 (4-core)
   - Hosts: Proxmox VE, Primary Proxmox Backup Server

2. **red-one** (Dell Optiplex 3020)
   - 500GB HDD, 16GB RAM, Intel i5 (4-core)
   - Hosts: Proxmox VE

3. **hth** (Dell Inspiron 3650)
   - 1TB HDD, 16GB RAM, Intel i5 (4-core)
   - Hosts: Proxmox VE, Redundant PBS instance

4. **secondSun** (Toshiba Satellite s55T)
   - 500GB SSD, 16GB RAM, Intel i7 (8-core)
   - Hosts: Proxmox VE

### Standalone/Bare Metal:
- **Big Blue** (Gateway N557): Ubuntu Server – will host ELK stack
- **HP Pavilion G7**: Kali Linux – cybersecurity exploration
- **Windows 11 Dev Laptop** (Dell 5491 2n1): Docker Desktop, VS Code
- **MacBook Pro A1506**: Ubuntu Desktop w/ RDP client
- **MacBook Pro 2011**: macOS legacy system

All systems are connected via a managed switch.

---

## 🧠 Key Services

### 🚀 Core Technologies:
- **Proxmox Backup Server** (2 instances on VMs)
- **Docker Containers**: NGINX, Prometheus, Grafana
- **Kubernetes**:
  - `K3s` – 3-node cluster (Cloudflare-tunneled public site)
  - `K8s` – 5-node cluster (also public-facing)
- **Grafana + Prometheus**: Two separate dashboards
- **Suricata + Loki + Promtail**: Intrusion detection & log ingestion
- **Heimdall**: Dashboard for services
- **Jellyfin**: Personal media server
- **Cloudflare Tunnel**: Secure external access to web services
- **Tailscale**: Remote SSH and file access
- **LAMP stacks** for legacy website hosting

### 💻 File Sharing:
- Samba-based file server accessible through Tailscale

---

## ⚙️ Automation & Scripting

A large part of this project focuses on scripting and automation:

### Bash Scripts:
- `docker-containerd.sh`: Installs Docker and Containerd
- `docker-kube-deploy.sh`: Deploys changes to web content in pods
- `initial-git-setups.sh`: SSH key and repo initialization
- `kube-install.sh`: Installs Docker + Kubernetes tools (kubeadm, kubectl, kubelet)
- `lamp_install.sh`: LAMP stack setup
- `port_scanner.sh`: Nmap-based port scanner
- `prometheus-monitor.sh`: Auto-setup Prometheus on new VMs
- `tailscale-*.sh`: OS-specific Tailscale installers

### Other Automation:
- Automated full and incremental backups via PBS
- Daily motivational quote script to partner (just for fun 💬)

> ⚡️ Future automation plans include migrating to **Ansible** for full infrastructure-as-code.

---

## 🌐 Networking

- Migrating from flat network to **VLAN-aware segmented network**
- **OPNsense** configured as "router on a stick"
- Planned implementation of **CARP** for high-availability routing
- **Tailscale** and **Cloudflare Tunnel** provide encrypted external access

---

## 📊 Monitoring & Logging

- Dual **Grafana + Prometheus** setups
  - Instance 1: Laptops + desktops (Fedora Server via Docker Compose)
  - Instance 2: Homelab servers + nodes (Ubuntu Server VM)
- Custom dashboards for:
  - CPU usage & temperature
  - Drive lifecycle + temperature
  - Memory usage per node + VM
  - Real-time logging (via Loki/Suricata/Promtail)

---

## ⚠️ Challenges & Lessons Learned

### Struggles Overcome:
- **LVM** – initially intimidating, now foundational
- **VLANs** – working through OPNsense and interface bindings without bricking the cluster
- **Cloudflare Tunnels** – learned DNS + HTTPS edge routing
- **Systemd services** – powerful but error-prone
- **Kubernetes** – complex but rewarding

### Key Takeaway:
> You never understand a tool fully the first time. Repetition, rebuilding, and documenting is what turns knowledge into skill.

---

## 📌 Future Plans

- ✅ Finalize VLAN migration
- ✅ Set up ELK Stack on Ubuntu bare metal
- 🔄 Migrate ELK stack to K3s
- 🧪 Improve PBS to back up additional devices (Windows, bare metal)
- 🧠 Learn Ansible, improve Bash skills
- 🐳 Improve Docker + Kubernetes mastery
- 🐍 Learn more Python scripting

---

## 🖼 Screenshots
![Grafana Homelab Dashboard](./path-to-screenshot.png)

---

## 📬 Contact / Connect
- GitHub: [@jlarry77](https://github.com/jlarry77)
- LinkedIn: [linkedin.com/in/justynlarry](https://www.linkedin.com/in/justyn-larry-8402a7348/)

> *"Built not bought. Learned by breaking."*
