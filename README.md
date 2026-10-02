# ⚠️ SUPERSEDED — use the canonical verification repository

This repository is **retired**. It previously published the fingerprint of an intermediate build that is
**not the delivery artifact**. Leaving it live would publish a second, conflicting number, so it is
reduced to this pointer.

**Canonical verification record → https://github.com/mohamedsamir113377-bit/FiberOS-R14.1-Verification-Proof**

The single canonical fingerprint is recorded there and in the private seller record:

| Field | Value |
|---|---|
| Artifact | `FiberOS-R14.1-Sales-Core-dac01a2-deterministic.zip` |
| SHA-256 | `6abd1fa870dbf5ddbe7369da08e3b901764a42e55f3a5c98ce42c08d95eb87ff` |
| Reference commit | `dac01a2ef20b37f5262af151bb200479e2e32e75` |
| Rebuild | `python3 scripts/build-delivery-archive.py --output out.zip --commit <commit>` → byte-identical ZIP |

No other SHA-256, no intermediate build fingerprint, and no archive is published from this repository.
It contains no product source code and no downloadable artifact.
