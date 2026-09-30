# FiberOS R14.1 — Independent Verification Record

**This repository contains NO product source code.** It exists only to let a buyer verify,
by checksum, that the artifact they received is the exact build that passed the audit below.

## Verified artifact
- File: `FiberOS-R14.1-CLEAN-SALES-CORE-2026-09-30-AUDITED.zip`
- SHA-256: `1ba2cfee4798c713079dd87f02df735ca515f900e327fe61e0f03adf437dcbb1  FiberOS-R14.1-CLEAN-SALES-CORE-2026-09-30-AUDITED.zip`

## How to verify (buyer, 30 seconds)
```
sha256sum FiberOS-R14.1-CLEAN-SALES-CORE-2026-09-30-AUDITED.zip
```
If the printed hash equals the value above, you hold the audited build. If it differs, do not accept the file.

## Audit evidence (reproduced by the auditor on 2026-09-30 UTC)
| Check | Command | Result |
|---|---|---|
| Unit + contract test suite | `npm test` | 317 tests, **316 passed, 0 failed**, 1 skipped |
| JavaScript syntax | all `.js` files | **0 syntax failures** |
| JSON validity | all `.json` files | **0 parse failures** |
| Package manifest integrity | per-file SHA-256 map | every tracked file re-verified; byte total matched exactly |
| i18n key parity | 15 target locales | **101/101 keys each**, 0 empty values, 0 literal source copies |
| Secret scan | tokens/keys/passwords | no live credentials or private keys in shipped source |
| Placeholder scan | TODO/FIXME/HACK | none in shipped code |
| Backup/editor junk | `.bak/.orig/~/.tmp/.DS_Store` | none |

## Notes
- Third-party vendored assets (e.g. the OCR engine under `apps/*/public/vendor/`) are bundled
  under their own upstream licences and are listed in `SBOM.cdx.json`.
- Tests execute fully offline: the workspace is Node-only with zero external runtime dependencies
  (optional PostgreSQL/Redis adapters are integration-gated and skipped when absent).

## Licence
Proprietary commercial software. Redistribution, resale, or sublicensing is prohibited without a
signed written agreement with the copyright holder.
