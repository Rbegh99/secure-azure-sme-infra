# Security Validation & Connectivity Testing

## Objective
Verify that network segmentation and NSG rules correctly protect the backend server.

---

## Test 1 — External Access to Backend

A connectivity test was performed from an external machine to the backend public IP:

Command used:
Test-NetConnection <backend-public-ip> -Port 80

Result:
- TCP connection failed
- Ping timeout

This confirms the backend server is not reachable from the internet.

Expected secure behavior: SUCCESS

---

## Test 2 — Direct Browser Access to Private IP

An attempt was made to access the backend private IP directly from a browser.

Result:
Connection timeout

This demonstrates that the backend server is not exposed outside the virtual network.

---

## Interpretation

The connection failure is intentional.

The NSG rules and subnet isolation successfully prevent direct access to internal resources.

A timeout in this scenario is not an error — it is proof of security enforcement.

---

## Verified Security Model

Allowed:
Internet → Web VM → App VM

Blocked:
Internet → App VM

This confirms the network segmentation architecture is working as designed.

