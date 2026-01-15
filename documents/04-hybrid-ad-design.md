# 04 — Hybrid AD design (OU layout + sync boundary)

## Outcome
An OU layout that matches departments and a strict sync boundary for AD Connect.

## Recommended OU structure
DC=jakubtech,DC=local
└── OU=JT
    ├── OU=Users
    │   ├── OU=Legal
    │   ├── OU=Compliance
    │   ├── OU=Operations
    │   ├── OU=Finance
    │   ├── OU=HR
    │   └── OU=IT
    ├── OU=Groups
    │   ├── OU=Dept
    │   └── OU=Access
    └── OU=ServiceAccounts

## Sync scope (start small)
Phase 1:
- Sync only `OU=JT\Users\IT` (one test user)
Phase 2:
- Sync `OU=JT\Users` (all business users)
Optional:
- Sync `OU=JT\Groups` only if you need group mastering from on-prem

Do NOT sync:
- `OU=ServiceAccounts` (unless required)

## UPN alignment
- Ensure users have UPN suffix `@jakubtech.co.uk` on-prem so cloud sign-in matches your real domain.
