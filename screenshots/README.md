# Azure Public vs Private Networking (Azure Virtual Network)

## Overview
This project demonstrates how to design a secure Azure Virtual Network (VNet – Virtual Network) with a **public subnet** and a **private subnet**, apply different Network Security Group (NSG – Network Security Group) rules, and validate secure access using Secure Shell (SSH – Secure Shell).

---

## Architecture
Azure Virtual Network (VNet – Virtual Network)
- public-subnet (10.0.1.0/24)
  - public-vm (public IP + SSH)
  - public-nsg (allows SSH port 22)
- private-subnet (10.0.2.0/24)
  - private-vm (no public IP)
  - private-nsg (restricted access)

---

## Tools & Technologies Used
- Microsoft Azure Portal
- Azure Virtual Network (VNet)
- Subnets (public / private)
- Network Security Groups (NSGs)
- Azure Virtual Machine (VM – Virtual Machine)
- Ubuntu Linux
- Secure Shell (SSH)

---

## Build Steps (High Level)
1. Created a Resource Group (RG – Resource Group): `project2-network-rg`
2. Created a Virtual Network (VNet): `project2-vnet`
3. Created two Subnets:
   - `public-subnet` (10.0.1.0/24)
   - `private-subnet` (10.0.2.0/24)
4. Created two Network Security Groups (NSGs):
   - `public-nsg`
   - `private-nsg`
5. Attached NSGs to subnets:
   - `public-subnet` → `public-nsg`
   - `private-subnet` → `private-nsg`
6. Deployed Public VM: `public-vm` in `public-subnet`
7. Validated SSH access and networking

---

## Validation & Testing (Proof)
### SSH Connection
Connected to `public-vm` using Azure Cloud Shell and SSH.

### Identity & Private IP Verification
Commands run inside the VM:
```bash
hostname
ip a
