# 03 — Azure core infrastructure (West Europe, minimal)

## Outcome
A minimal Azure footprint that supports management, logging, and AD Connect.

## Resource Groups
- `RG-JT-Core-weu-01`
- `RG-JT-Network-weu-01`
- `RG-JT-Security-weu-01`
- `RG-JT-Compute-weu-01`

## Networking
VNET:
- `VNET-JT-Core-weu-01` : `10.10.0.0/16`

Subnets:
- `SNET-JT-Mgmt-01` : `10.10.1.0/24`
- `SNET-JT-Servers-01` : `10.10.2.0/24`
- `AzureBastionSubnet` (optional)

NSG baseline
- Default deny inbound
- Prefer Bastion for RDP
- If temporary RDP is required: allow only your public IP, time-boxed, logged

## Compute
- `VM-JT-ADCONNECT-01` (Windows Server) — **Standard_D2s_v3** minimum
- Disk: Standard SSD is sufficient for lab unless you know you need more IOPS

## Evidence
- Screenshots: RGs, VNET/subnets, NSG rules, VM overview
- Log any inbound exceptions in evidence/changelog.md
