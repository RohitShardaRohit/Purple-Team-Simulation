# Purple Team Sim — Setup & Commands

This document describes how to build a small purple-team lab with two VMs (Kali attacker, Ubuntu victim) in VirtualBox, configure networking so the attacker can reach the victim, and run the exact commands used in the simulation.

> **Quick note:** This lab is for education and testing only. Run it on systems you own or where you have explicit permission to use.

---

## 1) Downloads (official pages)

- VirtualBox (host hypervisor):  
  https://www.virtualbox.org/wiki/Downloads

- Kali Linux (attacker ISO):  
  https://www.kali.org/get-kali/

- Ubuntu Desktop (victim ISO):  
  https://ubuntu.com/download/desktop

Download the correct ISO build for your host architecture (amd64 / arm64).

---

## 2) Create the VMs (VirtualBox quick steps)

1. Open VirtualBox → **New** → create two VMs:
   - **Kali (attacker)**  
     - Type: Linux, Version: Debian (64-bit)  
     - Recommended: 2+ CPUs, 2+ GB RAM, 20+ GB disk
   - **Ubuntu (victim)**  
     - Type: Linux, Version: Ubuntu (64-bit)  
     - Recommended: 2+ CPUs, 2+ GB RAM, 20+ GB disk

2. Attach the downloaded ISOs and install the OS on each VM.

3. (Recommended) After install and patching take snapshots to roll back later.

---

## 3) VirtualBox networking (recommended)

For reproducible results use a private network that both VMs share:

**Option A — Host-only Network (common & simple)**  
- VirtualBox → *File → Host Network Manager* → create a Host-only network (if none exists).  
- In each VM → Settings → Network:
  - Set one adapter to **Host-only Adapter** and choose the same host-only network for both VMs.
  - Optionally leave Ubuntu Adapter 1 as **NAT** so it keeps internet access.

**Option B — NAT Network (alternative)**  
- Create/use VirtualBox **NAT Network** and attach both VMs to that NAT network.

After powering VMs on, verify each VM has an IP on the private subnet:
```bash
 on each VM
ip -4 addr show
# or
hostname -I
```

You should see addresses like 192.168.56.x or 10.0.2.x. Note the Kali and Ubuntu IPs — you will use them in attacker commands.

## 4) Base packages & prep



