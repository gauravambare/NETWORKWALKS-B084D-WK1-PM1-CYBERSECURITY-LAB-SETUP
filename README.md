# Cybersecurity Lab Setup — B084F

## 1. Project Overview

This project demonstrates the setup of a basic cybersecurity lab using Oracle VirtualBox and Kali Linux on a Windows 11 host machine.

The lab uses a NAT Network to provide network connectivity to virtual machines while allowing them to communicate within the configured virtual network.

This project is part of the **Cybersecurity Int B084F** batch practical work.

## 2. Objectives

* Install and configure Oracle VirtualBox.
* Import and configure a Kali Linux virtual machine.
* Create a NAT Network in VirtualBox.
* Configure IP addressing, gateway, and DNS.
* Test network connectivity and internet access.
* Configure virtual machine integration features.
* Create a clean virtual machine snapshot.
* Document the setup with screenshots.

## 3. Purpose of the Lab

The purpose of this lab is to understand virtualization and basic network configuration in a controlled environment.

It provides practical experience with virtual machines, private virtual networking, IP addressing, connectivity testing, and virtual machine snapshots.

## 4. Lab Architecture

The lab consists of the following components:

* **Host OS:** Windows 11 Home Single Language
* **Virtualization Software:** Oracle VirtualBox
* **Guest OS:** Kali Linux
* **Network Mode:** NAT Network
* **Network Name:** NatNetwork
* **IPv4 Network:** `10.0.0.0/24`
* **Kali Linux IP:** `10.0.0.2/24` (configured; verify connectivity)
* **Gateway:** `10.0.0.1` (configured; verify connectivity)
* **DNS Server:** `8.8.8.8`

### Network Diagram

```text
+--------------------------------------+
|           Host Computer              |
|             Windows 11               |
|                                      |
|        Oracle VirtualBox             |
|                 |                    |
|        NAT Network: NatNetwork       |
|          10.0.0.0/24                 |
|                 |                    |
|          +---------------+           |
|          |  Kali Linux   |           |
|          |  10.0.0.2/24  |           |
|          +---------------+           |
+--------------------------------------+
```

## 5. System Requirements

### Hardware

* Processor: AMD Ryzen 7 7435HS
* Memory: 24 GB RAM
* Storage: 512 GB

### Software

* Windows 11
* Oracle VirtualBox
* Kali Linux virtual machine
* 7-Zip

## 6. Lab Configuration

The following network configuration was used for the lab.

| Parameter       | Configuration |
| --------------- | ------------- |
| Network Name    | NatNetwork    |
| Network Type    | NAT Network   |
| IPv4 Prefix     | `10.0.0.0/24` |
| IP Address      | `10.0.0.2`    |
| Subnet Prefix   | `/24`         |
| Default Gateway | `10.0.0.1`    |
| DNS Server      | `8.8.8.8`     |

**Note:** The network configuration has been entered in Kali Linux. Successful connectivity must be verified after applying the static IP settings.

## 7. Lab Setup Procedure

### Step 1: Install 7-Zip

Installed 7-Zip to extract the compressed virtual machine files when required.

### Step 2: Install VirtualBox

Installed Oracle VirtualBox on the Windows 11 host computer.

### Step 3: Create a NAT Network

Created a NAT Network named `NatNetwork` with the IPv4 prefix `10.0.0.0/24`.

### Step 4: Import Kali Linux

Imported the Kali Linux virtual machine into VirtualBox.

### Step 5: Configure Network Settings

Configured the virtual machine's network adapter to use the `NatNetwork` NAT Network.

### Step 6: Configure the Kali Linux IP Address

Configured the network connection with the following values:

* IP address: `10.0.0.2/24`
* Gateway: `10.0.0.1`
* DNS: `8.8.8.8`

### Step 7: Verify Network Connectivity

Network connectivity can be tested using the following commands in the Kali Linux terminal.

Check the IP address:

```bash
ip a
```

Check the gateway:

```bash
ping -c 4 10.0.0.1
```

Test internet connectivity:

```bash
ping -c 4 8.8.8.8
```

Test DNS resolution:

```bash
nslookup networkwalks.com
```

Check Nmap installation:

```bash
nmap --version
```

Successful output should be captured in screenshots and added to this repository after testing.

### Step 8: Configure VirtualBox Integration

Configure clipboard sharing, drag-and-drop, and the shared folder if supported by the installed guest environment and Guest Additions.

### Step 9: Create a Virtual Machine Snapshot

After verifying the configuration and connectivity, create a snapshot of the working Kali Linux virtual machine.

A snapshot provides a restore point that can be used if the virtual machine configuration needs to be recovered.

## 8. Screenshots

Screenshots documenting the lab setup will be included below.

| Screenshot                               | Description                          |
| ---------------------------------------- | ------------------------------------ |
| `1-screenshot-title-image.png`           | Kali Linux virtual machine           |
| `2-screenshot-network-settings-1.png`    | VirtualBox NAT Network configuration |
| `3-screenshot-kali-linux.png`            | Kali Linux desktop                   |
| `4-screenshot-kali-network-settings.png` | Kali Linux IP configuration          |

Place your own screenshots in the repository and update the filenames in this section if necessary.

To display screenshots directly in the README, use:

```markdown
![Kali Linux Desktop](screenshots/3-screenshot-kali-linux.png)
```

## 9. Problems Encountered and Solutions

### Static IP Configuration

A static IP address was configured through the Kali Linux network settings.

Connectivity must be tested after applying the settings. If the gateway or internet connection fails, inspect the NAT Network configuration, IP address conflicts, and routing settings.

### Virtual Machine Network Connectivity

VirtualBox NAT Network settings and the Kali Linux network configuration must be compatible for connectivity to work correctly.

Connectivity testing helps identify network configuration problems.

## 10. What I Learned

Through this practical exercise, I gained experience with:

* Installing and using virtualization software.
* Importing and configuring a Kali Linux virtual machine.
* Creating a NAT Network in VirtualBox.
* Configuring IP addresses, gateways, and DNS.
* Testing network connectivity using Linux commands.
* Understanding the purpose of virtual machine snapshots.
* Documenting a technical lab using GitHub.

## 11. Tools and Technologies

* Oracle VirtualBox
* Kali Linux
* Windows 11
* 7-Zip
* GitHub
* Basic Linux networking commands

## 12. Security and Ethical Use

This lab is intended for educational purposes and authorized cybersecurity practice.

Network testing and security tools should only be used on systems and networks for which permission has been granted.

## 13. Author

**Batch:** Cybersecurity Int B084F
**Project:** Week 1 — Practical Module 1
**Topic:** Cybersecurity Lab Setup

---

*This repository documents the setup and configuration of a basic cybersecurity lab using VirtualBox and Kali Linux.*
