# 01 — Identity model

## Outcome
A strict identity model:
- 3 cloud-only admins
- Everyone else on-prem AD -> synced to Entra ID

## Cloud-only admin accounts
1) `bg-admin@jakubtech.co.uk`
- Use: emergency only
- Controls: excluded from CA, monitored, long password stored securely

2) `admin-id@jakubtech.co.uk`
- Use: Entra ID identity admin tasks
- Controls: MFA enforced, least privilege

3) `admin-ops@jakubtech.co.uk`
- Use: Azure build and operations
- Privilege Model (Lab Context):
  Permanent elevated roles for ease of testing and deployment
- Privilege Model (Production via PIM):
  No permanent high-privilege roles. All elevation handled through PIM with approval and time-bound sessions.

## On-prem user naming
- UPN: `firstname@jakubtech.co.uk`
- SamAccountName: `firstname`
- Mail: `firstname@jakubtech.co.uk` 

## Group strategy (simple)
- Department groups mastered on-prem
- RBAC/admin groups cloud-only

## Evidence
- Screenshot: Entra users list showing only the 3 cloud admins as cloud-only
- Export: Entra role assignments (stored in evidence/exports/)
