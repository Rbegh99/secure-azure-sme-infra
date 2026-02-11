# secure-azure-sme-infra
Secure Azure infrastructure project demonstrating AZ-104 networking, security and governance best practices.
# Secure Azure Infrastructure for a Small Business

## Project Overview
This project demonstrates the design and deployment of a secure Azure infrastructure aligned with AZ-104 objectives and security best practices.

The goal is to simulate a small business cloud environment using proper network segmentation, governance, secure administration, and backup configuration.

---

## Architecture Components

- Resource Group (with tagging strategy)
- Virtual Network (10.0.0.0/16)
- Web Subnet (10.0.1.0/24)
- App Subnet (10.0.2.0/24)
- AzureBastionSubnet (10.0.3.0/26)
- Network Security Groups (NSGs)
- Virtual Machines (no public inbound access)
- Azure Bastion
- Recovery Services Vault (backup policy)
- Azure Monitor & Log Analytics
- Network Watcher (diagnostics & troubleshooting)

---

## Security Approach
- No public RDP/SSH exposure
- Subnet segmentation
- Least privilege principle
- Governance via tagging
- Backup enabled for resilience

---

## Documentation
See the `/docs` folder for architecture details and screenshots.
