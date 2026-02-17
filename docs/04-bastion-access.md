# Secure Administrative Access — Azure Bastion

## Objective
Provide remote administrative access to virtual machines without exposing management ports to the internet.

---

## Problem with Traditional Access

Normally administrators connect using:

- RDP (3389)
- SSH (22)

Opening these ports publicly exposes servers to:

- Automated internet scanning
- Brute-force attacks
- Credential stuffing attempts

Even strong passwords cannot prevent continuous attack attempts.

---

## Azure Bastion Implementation

Azure Bastion was deployed inside the virtual network and used as a secure jump host.

Administrators connect to the VMs directly from the Azure Portal over HTTPS (443).

No public IP addresses are required on the virtual machines.

---

## Access Flow

Admin → Azure Portal → Bastion → Private VM

The connection stays entirely within Azure's private network.

---

## Security Benefits

- No RDP/SSH ports exposed to the internet
- Prevents port scanning and brute-force attacks
- Centralized administrative access
- Reduced attack surface
- Follows Zero Trust administrative principles

---

## Result

Both web and application servers remain private while still being manageable.

The infrastructure is accessible to administrators but invisible to attackers.

