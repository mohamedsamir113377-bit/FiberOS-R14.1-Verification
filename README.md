# FiberOS R14.1 — Independent Verification Record

**This repository contains NO product source code.** It exists so a buyer can confirm, by
checksum, that the file delivered by the store is the exact build that passed the audit below.

## Verified artifact
- File: `FiberOS-R14.1-CLEAN-SALES-CORE-FINAL.zip`
- SHA-256: `4a88f59ad7dd859348d84659b934febb1d1212de2c5eb978f333a5f8b1799668`

## Verify in 30 seconds
```
sha256sum FiberOS-R14.1-CLEAN-SALES-CORE-FINAL.zip
```
If the printed hash equals the value above, you hold the audited build. If it differs, do not accept the file.

## Reproduced audit results (2026-09-30 UTC)
| Check | Result |
|---|---|
| Full test suite | 317 tests — **316 passed, 0 failed**, 1 skipped |
| JavaScript syntax (all .js) | **0 failures** |
| JSON validity (all .json) | **0 failures** |
| Package manifest (per-file SHA-256) | every tracked file re-verified; byte total matched |
| i18n key parity (15 locales) | **101/101 keys each**, 0 empty, 0 literal source copies |
| Secret / private-key scan | none present in shipped source |
| TODO/FIXME · .bak/.tmp junk | none |

## Notes
- The product source code is **not** published here and is not downloadable from this repository.
- Optional PostgreSQL/Redis adapters are integration-gated and skipped when absent; the suite runs fully offline.
- Third-party vendored assets remain under their own upstream licences (see `SBOM.cdx.json`).

## Licence
Proprietary commercial software. Redistribution, resale, or sublicensing is prohibited without a
signed written agreement with the copyright holder.
