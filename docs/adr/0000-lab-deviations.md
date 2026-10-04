# ADR-0000: Lab deviations from production posture

- Status: Accepted
- Date: 2026-09-29

## Context
Personal lab on a $50-150/month budget, synthetic data only, Azure Southeast Asia.

## Decision
The primary workspace is a Serverless Azure Databricks workspace. Classic-compute topics
(compute policies, job clusters, spot, Spark UI) use a temporary Hybrid workspace
(SCC off, same metastore) during Week 2.

## Consequences
- No managed resource group, no NAT gateway, no idle VM cost.
- No classic clusters in the primary workspace; budgets are detective, so preventive
  controls are job timeouts, standard performance mode and small warehouses with auto-stop.

## Lab deviations vs production
| Area | Lab | Production |
|---|---|---|
| Workspace | Serverless + temporary Hybrid (managed VNet, SCC off) | VNet-injected Hybrid and/or serverless with NCC |
| Network | Public endpoints, Entra-only auth | SCC, Private Link (front/back end), storage private endpoints |
| Storage redundancy | LRS | GZRS / RA-GZRS |
| Encryption keys | Microsoft-managed | Customer-managed keys in Key Vault |
