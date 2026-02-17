# Virtual Machine Deployment — Secure Two-Tier Architecture

## Objective
Deploy two virtual machines in separate subnets to simulate a secure application environment with controlled exposure.

---

## VM Roles

### Web Tier — Public Entry Point
- VM: vm-web
- Subnet: web-subnet
- Public IP: Enabled

The web server is the only component exposed to the internet and acts as the entry point for external traffic.

---

### Application Tier — Private Backend
- VM: vm-app
- Subnet: app-subnet
- Public IP: None

The backend server is intentionally private and only reachable from the web subnet.

---

## Security Design Decision

The application VM does not have a public IP address.

This is not a configuration omission but a security control.

Removing public exposure prevents:
- Port scanning
- Brute force attempts
- Direct exploitation

Security is enforced at the network layer before firewall rules are evaluated.

---

## Traffic Flow

Internet → vm-web → vm-app   
Internet → vm-app → Blocked

---

## Validation Result

Connectivity tests confirmed:

- Web server reachable from internet
- Backend server unreachable from internet
- Backend accessible only through the web tier

A connection timeout is the expected secure behavior.

