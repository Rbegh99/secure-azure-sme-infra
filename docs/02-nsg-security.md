
# Network Security Groups (NSG)

## Objective
Implement subnet-level security controls to restrict inbound traffic and enforce network segmentation.

---

## NSGs Created

- **nsg-web**
  - Associated to: **web-subnet**
  - Purpose: Protect internet-facing web tier

- **nsg-app**
  - Associated to: **app-subnet**
  - Purpose: Protect private backend tier

---

## NSG Association (Subnet-level)

Associations:
- web-subnet → nsg-web
- app-subnet → nsg-app

Subnet-level NSGs provide centralized traffic filtering for all VMs/NICs in the subnet.

---

## NSG-Web Inbound Rule — Allow HTTP

Rule Name: **Allow-HTTP**  
Priority: **100**  
Protocol: **TCP**  
Destination Port: **80**  
Source: **Internet (or Any for lab)**  
Action: **Allow**

Purpose:
Allow inbound HTTP traffic to the web tier. All other inbound traffic remains blocked by default (`DenyAllInBound`).

---

## NSG-App Inbound Rule — Allow Web → App (HTTP)

Rule Name: **Allow-Web-To-App**  
Priority: **100**  
Protocol: **TCP**  
Destination Port: **80**  
Source: **10.0.1.0/24 (web-subnet)**  
Action: **Allow**

This enables controlled communication from the web tier to the application tier while maintaining segmentation.

---

## NSG-App Inbound Rule — Deny Internet → App (HTTP)

Rule Name: **Deny-Internet-To-App**  
Priority: **200**  
Protocol: **TCP**  
Destination Port: **80**  
Source: **Internet (Service Tag)**  
Action: **Deny**

This prevents direct access to the backend from the internet and enforces a secure two-tier model.

---

## Expected Traffic Flow

Internet → Web VM (HTTP)  
Web subnet → App subnet (HTTP)  
Internet → App subnet (blocked)

