# secure-azure-sme-infra
Secure Azure infrastructure project demonstrating AZ-104 networking, security and governance best practices.
# Secure Azure Infrastructure for a Small Business

## Project Overview
This project demonstrates the design and deployment of a secure Azure infrastructure aligned with AZ-104 objectives and security best practices.

The goal is to simulate a small business cloud environment using proper network segmentation, governance, secure administration, and backup configuration.

---

## Architecture Components
- Resource Group with tagging strategy
- Virtual Network (10.0.0.0/16)
- Frontend Subnet (10.0.1.0/24)
- Backend Subnet (10.0.2.0/24)
- Network Security Groups (NSGs)
- Azure Bastion (secure admin access)
- Virtual Machine (no public inbound access)
- Recovery Services Vault (backup policy)

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
