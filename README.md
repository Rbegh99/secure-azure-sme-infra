# Azure Secure Two-Tier Infrastructure (AZ-104 Hands-On Project)

This project implements a secure two-tier Azure architecture where the frontend is publicly accessible while the backend remains fully private.

The environment demonstrates real network isolation, controlled inter-tier communication, secure administrative access using Azure Bastion, and VM protection using Azure Backup.

All security controls were validated through connectivity tests.

---

## Project Overview
The goal is to simulate a small business cloud environment using proper network segmentation, governance, secure administration, and backup configuration.

---

## Implemented Architecture

- Segmented virtual network (10.0.0.0/16)
- Public web tier (10.0.1.0/24)
- Private application tier (10.0.2.0/24)
- Bastion management subnet (10.0.3.0/26)
- Network Security Groups enforcing layer isolation
- Web VM (public entry point)
- App VM (private backend)
- Azure Bastion secure administration
- Recovery Services Vault protection

---

## Security Principles Applied
- No public management ports (RDP/SSH)
- Subnet-level segmentation
- Least privilege network access
- Secure jump host administration
- Data protection via backup

---

## Security Validation

The architecture was validated through real connectivity tests:

- Direct internet access to backend fails
- Private IP unreachable externally
- Only web tier can reach application tier
- Administrative access performed via Bastion only
- Recovery point successfully created

This confirms effective network segmentation and reduced attack surface.

---

## Project Evidence
Detailed implementation steps and validation screenshots are available in the `/docs` folder.
