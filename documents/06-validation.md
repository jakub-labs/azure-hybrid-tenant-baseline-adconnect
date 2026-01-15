# 06 — Validation

## Identity
- [ ] Only 3 cloud-only admin accounts exist (bg-admin, admin-id, admin-ops)
- [ ] Admin MFA policy enforced (CA-001)
- [ ] Legacy auth blocked (CA-002)
- [ ] Break-glass sign-in tested and logged

## Hybrid
- [ ] Only scoped OUs sync
- [ ] At least 1 user from each dept syncs successfully (once enabled)
- [ ] No persistent sync errors

## Azure
- [ ] Resources deployed in West Europe
- [ ] VM-JT-ADCONNECT-01 is Standard_D2s_v3
- [ ] No permanent inbound RDP from the internet
