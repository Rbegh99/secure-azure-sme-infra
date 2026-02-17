# Network Design & Segmentation

## Objective
Design a segmented Azure virtual network to isolate public and private workloads and reduce the attack surface.

---

## Virtual Network Architecture

A dedicated virtual network was created to host a two-tier application:

- Web tier (public entry point)
- Application tier (private backend)

The network uses subnet-level isolation instead of relying only on host-based firewalls.

---

## Addressing Strategy

| Subnet | Purpose | Exposure |
|------|------|------|
| web-subnet | Internet-facing services | Public |
| app-subnet | Backend services | Private |

The backend subnet is intentionally not reachable from the internet.

This ensures attackers cannot directly access internal services even if the public server is compromised.

---

## Security Design Rationale

Instead of protecting each VM individually, the security boundary is moved to the network layer.

Benefits:
- Prevent lateral movement
- Centralized access control
- Predictable traffic flow
- Cloud security best practice

This network segmentation prepares the environment for NSG-based filtering and secure access using Azure Bastion.

