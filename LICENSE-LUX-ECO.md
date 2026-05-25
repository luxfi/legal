# Lux Ecosystem License (LicenseRef-Lux-Eco)

**SPDX Identifier:** `LicenseRef-Lux-Eco`
**Version:** 1.2, December 2025
**Canonical text:** [`LICENSE-LUX-ECO.txt`](./LICENSE-LUX-ECO.txt) — single source of truth, byte-perfect copy of the license body. SPDX scanners and license-detection tooling MUST resolve `LicenseRef-Lux-Eco` to this file.
**Last verified:** 2026-05-15

## How to use this license

Every Lux Ecosystem repo MUST do the following:

1. Place a `LICENSE` file at the repo root with the contents of `LICENSE-LUX-ECO.txt`, byte-for-byte.
2. Mark new source files with the SPDX header:

   ```
   // SPDX-License-Identifier: LicenseRef-Lux-Eco
   ```

3. Do NOT modify the license body. Wording, whitespace, headings, and the TL;DR section are all material — drift creates legal ambiguity.

## Repos under this license

The canonical Eco-licensed repos in the `luxfi` org (per the legal-templates agent's audit + corroborating commits in this directory):

- `luxfi/ai`
- `luxfi/bridge`
- `luxfi/consensus`
- `luxfi/corona`
- `luxfi/crypto`
- `luxfi/exchange`
- `luxfi/fhe`
- `luxfi/fhe-coprocessor`
- `luxfi/fpga`
- `luxfi/kms`
- `luxfi/lamport`
- `luxfi/lattice`
- `luxfi/mpc`
- `luxfi/precompile`
- `luxfi/ringtail`
- `luxfi/safe`
- `luxfi/threshold`
- `luxfi/wallet`
- `luxfi/wallet-foundation`
- `luxfi/warp`

## Drift audit (2026-05-15)

Each repo's `LICENSE` file was compared byte-for-byte against the canonical text using `cmp -s`. Canonical size: 4213 bytes, MD5 `5e4d025adefb2183c9b6b74f07dc8aa7`.

| Repo | Status |
|------|--------|
| ai | PASS |
| bridge | PASS |
| consensus | PASS (reference source) |
| corona | PASS |
| crypto | PASS |
| exchange | PASS |
| fhe | PASS |
| fhe-coprocessor | PASS |
| fpga | PASS |
| kms | PASS |
| lamport | PASS |
| lattice | PASS |
| mpc | PASS |
| precompile | PASS |
| ringtail | PASS |
| safe | PASS |
| threshold | PASS |
| wallet | PASS |
| wallet-foundation | PASS |
| warp | PASS |

**Drifts:** none. All 20 repos hold a byte-identical copy of the canonical text. No remediation required as of 2026-05-15.

## Future audits

Reproduce this audit with:

```sh
CANON=/Users/z/work/lux/legal/LICENSE-LUX-ECO.txt
for repo in ai bridge consensus corona crypto exchange fhe-coprocessor fhe \
           fpga kms lamport lattice mpc precompile ringtail safe threshold \
           wallet-foundation wallet warp; do
  REPO_LIC="$HOME/work/lux/$repo/LICENSE"
  if [ ! -f "$REPO_LIC" ]; then echo "ABSENT: $repo"; continue; fi
  if cmp -s "$CANON" "$REPO_LIC"; then echo "PASS: $repo"
  else echo "DRIFT: $repo"; fi
done
```

If a drift is reported, the canonical file in this directory is authoritative. Update the offending repo's `LICENSE` to match — never adjust the canonical text to absorb a repo's drift.

## References

- Full licensing policy: [`LICENSING-POLICY.md`](./LICENSING-POLICY.md)
- Open-source repo classification: [`OPEN-SOURCE-POLICY.md`](./OPEN-SOURCE-POLICY.md)
- Lux Proposal LP-0012: https://github.com/luxfi/lps/blob/main/LPs/lp-0012-ecosystem-licensing.md
- Commercial licensing contact: `licensing@lux.network`
