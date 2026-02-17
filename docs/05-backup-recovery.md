# Backup & Recovery — Azure Recovery Services Vault

## Objective
Protect the virtual machine against data loss and ensure service recovery in case of deletion, corruption, or ransomware.

---

## Backup Architecture

Azure Backup was implemented using a Recovery Services Vault located in the same region as the virtual machines.

The vault stores recovery points and acts as the centralized restore location.

---

## Backup Policy Design

Backup type: Virtual Machine  
Policy: Standard (daily backup)

Reasoning:
- Provides sufficient protection for non-critical workloads
- Reduces storage cost
- Demonstrates real production trade-off between cost and resilience

---

## Protection Workflow

Enabling backup does not immediately protect the VM.

Protection starts only after the first recovery point is successfully created.

Backup process:

1. Disk snapshot is taken
2. Snapshot is transferred to the Recovery Services Vault
3. Recovery point is created

Only after this stage the VM becomes officially protected.

---

## Verification

Backup job status was monitored in the Backup Jobs panel.

Successful completion confirmed:
- Recovery points available
- VM restorable
- Backup configuration functional

---

## Key Cloud Concepts Demonstrated

- Backup ≠ Protected until recovery point exists
- Recovery Services Vault stores restore points
- Snapshot used before vault storage
- Backup policy impacts cost and RPO

This ensures the environment is not only secure but also recoverable.

