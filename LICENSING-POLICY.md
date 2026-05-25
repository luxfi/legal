# Lux Industries Inc. — Licensing Policy

Internal canonical reference for how Lux Industries Inc. licenses its intellectual property.

## Three-Tier Strategy

Lux IP is divided into three tiers. Each tier has a distinct license, distribution channel, and commercial posture.

### Tier 1 — Commodity (BSD-3-Clause)

Code that is widely useful, has no defensible moat, and benefits Lux through broad adoption.

- License: BSD-3-Clause.
- Distribution: public repositories under `github.com/luxfi/*`.
- Commercial use: free, no restrictions beyond BSD-3 attribution.
- Patents: not patent-protected by Lux at the source level. Standard BSD-3 patent treatment applies.
- Examples: protocol bindings, common utilities, reference clients, documentation tooling.

### Tier 2 — Eco (Patent-Protected, Source-Available)

Code where Lux holds patentable inventions and reserves commercial rights, but publishes source for inspection, research, audit, and non-commercial use.

- License: Lux Eco License (custom source-available license; see template language in commercial license).
- Distribution: public repositories under `github.com/luxfi/*` with `LICENSE` clearly marked.
- Permitted without commercial license: inspection, research, education, internal evaluation, non-commercial development, security audit.
- Restricted without commercial license: production use generating revenue, distribution as part of a commercial product, hosting as a paid service.
- Patents: explicitly retained by Lux Industries Inc. Commercial license includes a patent grant.
- Stance: there are **no planned migrations of Eco repos to BSD-3**. Eco is the surface for commercial license sales and reflects the long-term commercial posture for these repos.

### Tier 3 — Closed (Private Moat)

Code that is competitively decisive and never published externally.

- License: proprietary, all rights reserved.
- Distribution: private GitHub organization `lux-private/*`. Pull access by invitation only.
- Commercial access: only via a commercial license that explicitly references the private addendum (see [COMMERCIAL-LICENSE-PRIVATE-MOAT-ADDENDUM.md](COMMERCIAL-LICENSE-PRIVATE-MOAT-ADDENDUM.md)).
- Patents: explicitly retained.
- Examples: GPU kernels, DEX matching engine, FPGA designs.

## Runtime Gate vs License Tier

A common point of confusion internally and externally: **every Lux artifact is licensed**. The question is not "is there a license" — it is "which license, and is there a runtime token check on top of it". The table below separates those two concerns.

| Layer | Code license | Runtime token? | Enforcement model |
|-------|--------------|----------------|-------------------|
| BSD-3-Clause commodity | BSD 3-Clause | None | Permissive open source; commercial use and forks unrestricted under BSD-3 attribution. |
| Patent-protected source-visible (Eco) | Lux Ecosystem License v1.2 (and the Lux Research License with Patent Reservation / Lux Genesis License variants) | None | Contract-only — source is visible so prior art is fixed and Authorized Networks can fork; commercial use outside Authorized Networks legally requires a signed paid license (Confluent Server / MongoDB SSPL pattern). |
| Closed performance moat | Commercial License Only (`lux-private/*`, not on public GitHub) | **`luxfi/license` token verified at startup** | Fail-closed runtime check (HashiCorp Vault EE / NVIDIA cuDNN pattern) — token signed by Lux Industries Inc., verified offline against an embedded public key. No phone-home. |

Two things this table makes explicit:

1. **The public CPU binary is not "unlicensed"**. It ships under BSD-3-Clause (or, for vendored upstreams, the inherited Apache / MIT / GPL / LGPL / MPL / BSL). What it lacks is a runtime token check, because there is nothing in that binary to gate.
2. **The runtime token gate at `cevm v0.50.0` and later only fires on tier-3 GPU/FPGA backends**. CPU paths run unmodified under their actual public licenses. Removing or bypassing the token does not make the closed code free — the closed code never shipped in the public binary in the first place (two-binary distribution).

## Per-Repo Classification (Representative)

The following table reflects Lux Industries Inc.'s current repo classification. The authoritative list is maintained alongside repo configuration; this table is a representative snapshot and may lag.

| Org / Repo | Tier | License | Notes |
|------------|------|---------|-------|
| `luxfi/node` | Eco | Lux Eco License | Core node implementation; patent-protected consensus and crypto |
| `luxfi/consensus` | Eco | Lux Eco License | Quasar / Ringtail / Snow consensus families |
| `luxfi/crypto` | Eco | Lux Eco License | Post-quantum primitives, MPC, threshold signing |
| `luxfi/cli` | BSD-3 | BSD-3-Clause | Operator tooling |
| `luxfi/sdk` | BSD-3 | BSD-3-Clause | Client SDKs (Go, TypeScript, Python) |
| `luxfi/wallet` | BSD-3 | BSD-3-Clause | Reference HD wallet |
| `luxfi/genesis` | BSD-3 | BSD-3-Clause | Genesis tooling |
| `luxfi/explorer` | BSD-3 | BSD-3-Clause | Block explorer fork |
| `luxfi/docs` | BSD-3 | BSD-3-Clause | Documentation site |
| `lux-private/gpu-kernels` | Closed | Proprietary | GPU acceleration kernels |
| `lux-private/dex` | Closed | Proprietary | DEX matching engine |
| `lux-private/fpga` | Closed | Proprietary | FPGA designs |

TODO[counsel-review]: confirm Eco license text complies with target jurisdictions (US, EU, UK, Singapore, Cayman, BVI). Confirm BSD-3 patent treatment of Lux-held patents in each jurisdiction.

## License Headers

- BSD-3 repos: short BSD-3 SPDX header in every source file. `SPDX-License-Identifier: BSD-3-Clause`.
- Eco repos: short Eco SPDX header pointing to LICENSE file. `SPDX-License-Identifier: LicenseRef-Lux-Eco`.
- Closed repos: proprietary header. `Copyright (c) Lux Industries Inc. All rights reserved. Proprietary and confidential.`

## Acceptance of Outside Contributions

- BSD-3 repos: accepted under existing BSD-3 terms. CLA optional for trivial contributions, required for substantial contributions per [CONTRIBUTOR-AGREEMENT.md](CONTRIBUTOR-AGREEMENT.md).
- Eco repos: CLA required for any contribution. Contribution is licensed back to Lux under the same Eco terms with patent grant.
- Closed repos: contributions accepted only from Lux employees or contracted parties under separate work-for-hire agreement.

## Commercial Licensing Workflow

1. Inquiry to **licensing@lux.network**.
2. Scope determination: which Eco repos, which deployment scale, whether private moat is in scope.
3. Draft license starts from [COMMERCIAL-LICENSE-TEMPLATE.md](COMMERCIAL-LICENSE-TEMPLATE.md).
4. If private moat is in scope, attach [COMMERCIAL-LICENSE-PRIVATE-MOAT-ADDENDUM.md](COMMERCIAL-LICENSE-PRIVATE-MOAT-ADDENDUM.md).
5. Counsel review. No license is signed without counsel review.
6. License token issuance per the addendum (if applicable) on execution.

## Cross-references

- [COMMERCIAL-LICENSE-TEMPLATE.md](COMMERCIAL-LICENSE-TEMPLATE.md)
- [COMMERCIAL-LICENSE-PRIVATE-MOAT-ADDENDUM.md](COMMERCIAL-LICENSE-PRIVATE-MOAT-ADDENDUM.md)
- [PATENT-POLICY.md](PATENT-POLICY.md)
- [OPEN-SOURCE-POLICY.md](OPEN-SOURCE-POLICY.md)
- [CONTRIBUTOR-AGREEMENT.md](CONTRIBUTOR-AGREEMENT.md)

Last reviewed: TODO[counsel-review] — date of most recent counsel sign-off.
