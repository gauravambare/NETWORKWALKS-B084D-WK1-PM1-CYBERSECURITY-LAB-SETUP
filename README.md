<div align="center">

# 🛡️ Cybersecurity Lab Setup

### VirtualBox • Kali Linux • Network Configuration

**Batch: Cybersecurity Int B084F | Week 1 — Practical Module 1**

<p>
  <img src="https://img.shields.io/badge/OS-Windows%2011-blue?style=for-the-badge&logo=windows" alt="Windows 11">
  <img src="https://img.shields.io/badge/Virtualization-VirtualBox-183A61?style=for-the-badge&logo=virtualbox" alt="VirtualBox">
  <img src="https://img.shields.io/badge/Linux-Kali%20Linux-557C94?style=for-the-badge&logo=kalilinux" alt="Kali Linux">
  <img src="https://img.shields.io/badge/Focus-Networking-red?style=for-the-badge" alt="Networking">
</p>

*A hands-on cybersecurity lab demonstrating virtual machine deployment, network configuration, IP addressing, and connectivity testing.*

</div>

---

## 📌 Table of Contents

* [Overview](#-project-overview)
* [Objectives](#-objectives)
* [Lab Environment](#-lab-environment)
* [Network Architecture](#-network-architecture)
* [Network Configuration](#-network-configuration)
* [Implementation](#-implementation)
* [Verification and Testing](#-verification-and-testing)
* [Screenshots](#-screenshots)
* [Challenges and Troubleshooting](#-challenges-and-troubleshooting)
* [Key Learnings](#-key-learnings)
* [Security and Ethical Use](#-security-and-ethical-use)
* [Project Information](#-project-information)

## 🎯 Project Overview

This project focuses on building a basic cybersecurity lab using **Oracle VirtualBox and Kali Linux** on a Windows 11 computer.

A dedicated NAT Network is configured to provide a virtual networking environment for the lab. The Kali Linux virtual machine is configured with a static IPv4 address, gateway, and DNS server.

The lab provides a foundation for learning virtualization, Linux networking, IP configuration, connectivity troubleshooting, and cybersecurity tools in a controlled environment.

## 🚀 Objectives

* Set up a virtualized cybersecurity lab.
* Install and use Oracle VirtualBox and 7-Zip.
* Import and configure a Kali Linux virtual machine.
* Create a NAT Network with a custom IPv4 subnet.
* Configure static IP addressing, gateway, and DNS.
* Verify network and internet connectivity.
* Configure virtual machine integration features.
* Create a snapshot of the configured virtual machine.
* Document the implementation with screenshots and command outputs.

## 💻 Lab Environment

### Host Machine

| Component        | Specification                   |
| ---------------- | ------------------------------- |
| Operating System | Windows 11 Home Single Language |
| Processor        | AMD Ryzen 7 7435HS              |
| Memory           | 24 GB RAM                       |
| Storage          | 512 GB                          |
| Architecture     | 64-bit                          |

### Virtualization Environment

| Component               | Configuration     |
| ----------------------- | ----------------- |
| Virtualization Platform | Oracle VirtualBox |
| Guest Operating System  | Kali Linux        |
| Network Mode            | NAT Network       |
| Network Name            | `NatNetwork`      |
| IPv4 Subnet             | `10.0.0.0/24`     |

## 🌐 Network Architecture

The lab uses a VirtualBox NAT Network to establish a virtual network for the Kali Linux environment.

```text
              HOST MACHINE
              Windows 11
                   |
           Oracle VirtualBox
                   |
          +-------------------+
          |    NatNetwork     |
          |  10.0.0.0/24      |
          +-------------------+
                   |
          +-------------------+
          |    Kali Linux     |
          |                   |
          | IP: 10.0.0.2/24   |
          | GW: 10.0.0.1      |
          | DNS: 8.8.8.8      |
          +-------------------+
                   |
             Network Testing
          Gateway / Internet / DNS
```

**Note:** The IP address, gateway, and DNS shown above are the configured values. Successful connectivity must be verified separately.

## ⚙️ Network Configuration

The following IPv4 configuration was entered for the Kali Linux network connection.

| Parameter       | Value          |
| --------------- | -------------- |
| Connection Type | Wired Ethernet |
| Network Name    | `NatNetwork`   |
| IPv4 Method     | Manual         |
| IP Address      | `10.0.0.2`     |
| Subnet Prefix   | `/24`          |
| Default Gateway | `10.0.0.1`     |
| DNS Server      | `8.8.8.8`      |

### Understanding the Configuration

* **IP Address:** Identifies the Kali Linux interface within the configured subnet.
* **Subnet Prefix:** `/24` corresponds to the subnet mask `255.255.255.0`.
* **Default Gateway:** Provides the configured route for traffic destined outside the local subnet.
* **DNS Server:** Resolves domain names into IP addresses.

> **Important:** Before relying on this configuration, verify that `10.0.0.2` is available and that the selected gateway matches the actual VirtualBox NAT Network configuration.

## 🛠️ Implementation

### Step 1 — Install the Required Software

Install Oracle VirtualBox and 7-Zip on the Windows host machine.

### Step 2 — Import Kali Linux

Import the Kali Linux virtual machine into VirtualBox and start it.

### Step 3 — Create the NAT Network

Create a NAT Network named `NatNetwork` with the IPv4 prefix:

```text
10.0.0.0/24
```

### Step 4 — Configure the Virtual Machine

Open the virtual machine's network settings and select `NatNetwork` as the network attachment.

### Step 5 — Configure the Kali Linux Interface

Configure the IPv4 settings using the IP address, gateway, and DNS values listed in the configuration table.

### Step 6 — Verify Connectivity

Run the network diagnostic commands listed below and inspect their output.

### Step 7 — Configure Integration Features

Configure clipboard sharing, drag-and-drop, and a shared folder if required. Install and configure Guest Additions when necessary.

### Step 8 — Create a Snapshot

After the configuration and connectivity checks succeed, create a snapshot so the virtual machine can be restored to its working state.

## 🧪 Verification and Testing

Run these commands in the Kali Linux terminal.

### 1. Inspect the Network Interface

```bash
ip a
```

**Purpose:** Check the interface state and assigned IP address.

### 2. Inspect the Routing Table

```bash
ip route
```

**Purpose:** Check the configured routes and default gateway.

### 3. Test Gateway Connectivity

```bash
ping -c 4 10.0.0.1
```

**Purpose:** Test whether the configured gateway responds.

### 4. Test Internet Connectivity

```bash
ping -c 4 8.8.8.8
```

**Purpose:** Test IP connectivity to a public destination.

### 5. Test DNS Resolution

```bash
nslookup networkwalks.com
```

**Purpose:** Check whether DNS can resolve the domain name.

### 6. Check Nmap Availability

```bash
nmap --version
```

**Purpose:** Check whether Nmap is installed and available.

### Verification Checklist

| Test                           | Status                    |
| ------------------------------ | ------------------------- |
| Kali Linux boots successfully  | Update after verification |
| Correct IP address is assigned | Configured; verify        |
| Gateway connectivity           | Pending verification      |
| Internet connectivity          | Pending verification      |
| DNS resolution                 | Pending verification      |
| Nmap availability              | Pending verification      |
| Snapshot created               | Update after completion   |

**Testing note:** Replace each status with the actual result after running the relevant command. A failed ping does not necessarily mean the entire network is broken; ICMP traffic may be filtered.

## 📸 Screenshots

Screenshots provide visual evidence of the lab configuration.

Create a `screenshots` folder in the repository and add your own images.

Suggested structure:

```text
B084F-WK1-PM1-CYBERSECURITY-LAB-SETUP/
│
├── README.md
└── screenshots/
    ├── 01-kali-linux-desktop.png
    ├── 02-nat-network-settings.png
    ├── 03-kali-ipv4-configuration.png
    ├── 04-network-connectivity.png
    └── 05-virtual-machine-snapshot.png
```

### Kali Linux Desktop

![Kali Linux Desktop](screenshots/01-kali-linux-desktop.png)

### VirtualBox NAT Network

![NAT Network Configuration](screenshots/02-nat-network-settings.png)

### Kali Linux IPv4 Configuration

![Kali IPv4 Configuration](screenshots/03-kali-ipv4-configuration.png)

### Network Connectivity Test

![Network Connectivity Test](screenshots/04-network-connectivity.png)

*Add the matching screenshot files to the `screenshots` folder. Until the files exist in the repository, these images will not render.*

## 🔧 Challenges and Troubleshooting

### Static IP Configuration

A static IP address was entered through the Kali Linux network settings.

If connectivity fails, check the interface configuration, subnet, gateway, routing table, and possible IP address conflicts.

### NAT Network Connectivity

The guest network settings must match the actual VirtualBox network configuration. Check that the correct NAT Network is selected and that the gateway is valid.

### DNS Resolution

If IP connectivity works but domain names do not resolve, inspect the DNS settings and test resolution with `nslookup`.

## 📚 Key Learnings

This practical exercise provides experience with:

* Virtual machine creation and management.
* VirtualBox NAT Network configuration.
* IPv4 addressing and subnet masks.
* Gateway and DNS configuration.
* Linux network diagnostic commands.
* Basic connectivity troubleshooting.
* Virtual machine snapshots and recovery.
* Technical documentation using GitHub.

## 🔐 Security and Ethical Use

This environment is intended for educational purposes and authorized cybersecurity practice.

Use network scanning and security tools only on systems and networks for which you have permission. Keep experiments within the intended lab environment unless broader testing has been explicitly authorized.

## 🧰 Tools and Technologies

| Tool                       | Purpose                                   |
| -------------------------- | ----------------------------------------- |
| Oracle VirtualBox          | Virtualization                            |
| Kali Linux                 | Linux-based cybersecurity environment     |
| 7-Zip                      | File extraction                           |
| Windows 11                 | Host operating system                     |
| GitHub                     | Version control and project documentation |
| Linux networking utilities | Network inspection and testing            |

## 👨‍💻 Project Information

| Field     | Details                 |
| --------- | ----------------------- |
| Project   | Cybersecurity Lab Setup |
| Batch     | Cybersecurity Int B084F |
| Practical | WK1-PM1                 |
| Platform  | VirtualBox              |
| Guest OS  | Kali Linux              |

---

<div align="center">

**Built as part of hands-on cybersecurity learning.**

*Learn • Configure • Test • Document*

</div>
