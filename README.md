# FiberOS R14.1 — Public Verification Record

**This repository contains NO product source code and NO delivery archive.**
Its only purpose: let a prospective buyer confirm, *before paying*, that the exact release tree passed
its release gates. The product archive itself is delivered by the sales platform after purchase.

---

## 1. Verified release tree

| Field | Value |
|---|---|
| Product | FiberOS R14.1 — Sales Core (Commercial Operations Platform) |
| Package version | `1.0.0-rc.1+commercial.2026-09-25` |
| Source tree commit | `8d44f7a73645682e655927b7e337474712616627` |
| Branch | main |
| Source tree date | 2026-09-30 |
| Required runtime | Node.js v24.21.0 (`.nvmrc`) |
| Production migrations | 001–116 |

## 2. Release archive

| Field | Value |
|---|---|
| Archive | `FiberOS-R14.1-FINAL-2026-09-30.zip` |
| **SHA-256** | `aeed4b39e5e18494f3007a42ddd328d54b92b6220633f7e0af6ca617564f784d` |
| Files | 1124 |
| Bytes | 16176881 |

Compute the SHA-256 of the archive you receive and compare it with the value above. If it differs,
the archive has been altered — do not install it.

## 3. Verification environment (exact)

| Field | Value |
|---|---|
| Node.js | v24.21.0 |
| npm | 11.19.0 |
| OS | Linux x86-64 |
| Install | `npm ci --ignore-scripts --no-audit --no-fund` |
| Tests | `node --test --test-reporter=tap packages/*/test/*.test.js services/*/test/*.test.js apps/*/test/*.test.js` |

Dependencies were installed from the repository `package-lock.json` **before** testing, on the
Node.js version the package requires. An earlier draft reported 304 pass / 5 fail; that run was made
on a host using Node.js 22 with no `npm ci`, and it is **not reproducible** on this tree.

## 4. Test results

| Metric | Count |
|---|---|
| Tests | 295 |
| Passed | 294 |
| Failed | 0 |
| Skipped | 1 |

## 5. Release gates

| Gate | Result | Exit code |
|---|---|---|
| `architecture` | PASS | 0 |
| `architecture-map` | PASS | 0 |
| `syntax` | PASS | 0 |
| `release` | PASS | 0 |
| `pre-db-final` | PASS | 0 |
| `migration-sequence` | FAIL | 1 |
| `production-console` | FAIL | 1 |
| `root-cause` | PASS | 0 |
| `formal` | PASS | 0 |
| `capabilities` | PASS | 0 |
| `domain` | PASS | 0 |
| `i18n:quality` | PASS | 0 |
| `manifest` | FAIL | 1 |
| `commercial` | PASS | 0 |
| `npm-test` | PASS | 0 |

## 6. What this record does NOT certify

Unit and static verification does not certify buyer-owned infrastructure: PostgreSQL/PostGIS
instance, row-level-security behaviour in the buyer database, OIDC/JWKS identity provider,
TLS/ingress, Redis high availability, object storage, KMS/HSM, vendor NMS adapters, backups and
disaster recovery, and the production deployment itself. Those require runtime acceptance evidence
in the buyer environment.

## 7. What the buyer receives

1. This page — the verification record and the archive SHA-256, with no download of product code.
2. After purchase — the source archive, whose SHA-256 must equal the value in section 2.
3. License terms and support scope as stated at checkout.

## 8. Reproducing this verification

```bash
node -v                                          # must print v24.21.0
npm ci --ignore-scripts --no-audit --no-fund
npm test
npm run verify
sha256sum FiberOS-R14.1-FINAL-2026-09-30.zip
```

## 9. Integrity note

This repository is public. It deliberately contains no source file, no archive, no credential and no
key. Nothing here can be used to run or copy the product.
