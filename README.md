# FiberOS R14.1 — Public Verification Record

**This repository contains NO product source code and NO delivery archive.**
Its purpose: let a prospective buyer confirm — *before paying* — that the exact release tree passed its
test suite and its release gates. The product archive is delivered by the sales platform after
purchase; the buyer then compares its SHA-256 with the value in section 2.

---

## 1. Verified release tree

| Field | Value |
|---|---|
| Product | FiberOS R14.1 — Sales Core (Commercial Operations Platform) |
| Package version | `1.0.0-rc.1+commercial.2026-09-25` |
| Source tree commit | `768a83122df5288ecdd5c15822ca723c6e9697cf` (branch `main`) |
| Source tree date | 2026-09-30 |
| Required runtime | Node.js v24.21.0 (`.nvmrc`, `engines.node >= 24.21.0`) |
| Production migrations | 001–116 |

## 2. Release archive

| Field | Value |
|---|---|
| Archive | `FiberOS-R14.1-FINAL-2026-09-30.zip` |
| **SHA-256** | `601fee6df1bcbca736c5ba8fd96aa6d35cb13b2672c8eb8b24c1703c16d1702e` |
| Files in archive | 1154 |
| Archive bytes | 16200535 |

After purchase, run `sha256sum FiberOS-R14.1-FINAL-2026-09-30.zip` on the archive you received and compare it with the
value above. If it differs, the archive has been altered — do not install it.

## 3. Verification environment (exact)

| Field | Value |
|---|---|
| Node.js | v24.21.0 |
| npm | 11.19.0 |
| OS | Linux x86-64 |
| Dependency install | `npm ci --ignore-scripts --no-audit --no-fund` |
| Test command | `node --test --test-reporter=tap packages/*/test/*.test.js services/*/test/*.test.js apps/*/test/*.test.js` |

Dependencies were installed from the committed `package-lock.json` **before** testing, on the Node.js
version the package declares. An earlier draft of this record reported *304 passed / 5 failed /
1 skipped*; that run was made on a host using Node.js 22.16.0 where `npm ci` had not been executed, so
`redis`, the OpenTelemetry packages and one workspace package were simply absent. It is **not
reproducible** on this tree and must not be quoted.

## 4. Test results

| Metric | Count |
|---|---|
| Tests | 316 |
| Passed | 315 |
| Failed | 0 |
| Skipped | 1 |

## 5. Release gates

| Gate | Result | Exit code |
|---|---|---|
| `manifest-parity` | **PASS** | 0 |
| `architecture` | **PASS** | 0 |
| `architecture-map` | **PASS** | 0 |
| `syntax` | **PASS** | 0 |
| `release` | **PASS** | 0 |
| `pre-db-final` | **PASS** | 0 |
| `migration-sequence` | **PASS** | 0 |
| `production-console` | **PASS** | 0 |
| `root-cause` | **PASS** | 0 |
| `formal` | **PASS** | 0 |
| `capabilities` | **PASS** | 0 |
| `domain` | **PASS** | 0 |
| `i18n:quality` | **PASS** | 0 |
| `manifest` | **PASS** | 0 |
| `commercial` | **PASS** | 0 |
| `npm-run-verify` | **PASS** | 0 |
| `npm-test` | **PASS** | 0 |

`npm-run-verify` is the repository's own canonical release chain (`npm run verify`), which runs all of
the gates above in the required order and ends with the commercial-release gate.

## 6. What this record does NOT certify

Unit and static verification does not certify buyer-owned infrastructure: the PostgreSQL/PostGIS
instance, row-level-security behaviour in the buyer database, the OIDC/JWKS identity provider,
TLS/ingress, Redis high availability, object storage, KMS/HSM, vendor NMS adapters, backups and
disaster recovery, or the production deployment itself. Those require runtime acceptance evidence in
the buyer environment.

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

This repository is public and readable by anyone. It deliberately contains no source file, no archive,
no credential and no key. Nothing here can be used to run or copy the product.
