# Liquidity OSS License & IP Audit

**Prepared for:** Lux Industries Inc. legal team
**Subject company:** Liquidity.io (operated by Satschel) — US ATS / BD / TA
**Audit date:** 2026-05-25
**Scope:** All Go modules, npm packages, Solidity submodules, Rust crates, and
container base images consumed by `~/work/liquidity/*` from upstream
`luxfi/*` (`~/work/lux`) and `hanzoai/*` (`~/work/hanzo`) sources.

---

## 1. Executive Summary

Liquidity consumes upstream Lux IP under seven license regimes:
permissive (BSD-3, MIT, Apache), copyleft (LGPL-3.0, GPL-3.0),
source-available (BUSL-1.1), and two proprietary Lux licenses — **Lux
Ecosystem License v1.2** ("LEL") and **Lux Research License with Patent
Reservation v1.0** ("LRL-PR"). LEL/LRL-PR cover ~25 directly-consumed
modules (consensus, crypto, MPC, threshold, FHE, ringtail, VM, EVM
precompile registry). They are not SPDX-recognized; grant rights only to
"Authorized Networks"; reserve all patents. A formal license between Lux
Industries Inc. and Satschel/Liquidity is required to operate Liquid EVM
commercially without ambiguity.

**Secondary exposure**: LGPL-3.0 (`luxfi/evm`, `evmgpu`) and GPL-3.0
(`luxfi/erc-3643`, `onchain-id`, `safe-frost`, and per package.json
`@luxfi/wallet`). LGPL §6 requires source-on-request and re-link
permission; GPL §5 propagates to combined works.

**Tertiary exposure**: third-party DeFi contracts under
`contracts/lib/standard/lib/` (BUSL-1.1: Aave V3, Compound V3, GMX V2,
Uni V3, Morpho; GPL: Balancer, Lido, Uni V2, Account Abstraction;
LGPL-3.0: safe-modules; MIT: OpenZeppelin, Solmate). None deployed today,
present in build tree.

Hanzo side is cleaner: `base`, `dbx`, `orm`, `commerce`, `tasks`,
`gateway`, `ingress`, `kms` MIT; `iam`, `authz`, `pubsub-go`, `age`,
`datastore` Apache-2.0. Trap: `hanzoai/mpc` ships under LEL.

**Top risks**: (1) LEL/LRL-PR coverage gap for Liquid EVM; (2) LGPL
source-offer obligations on the Liquid EVM binary; (3) GPL propagation
through ERC-3643 + OnchainID into every SecurityToken.

**Clean wins**: (1) BSD-3 foundation (`node`+`sdk`+`geth`+`api`+
`database`+`p2p`); (2) Hanzo MIT/Apache stack; (3) OpenZeppelin
underpins every deployed token.

---

## 2. Method

Extracted direct `luxfi/*` / `hanzoai/*` / `@luxfi/*` / `@hanzo*/*`
dependencies across 28 Go modules, >40 npm workspace packages, 1 Cargo
manifest, and 1 Foundry project. Located upstream source in `~/work/lux`
and `~/work/hanzo`; read each `LICENSE`; cross-checked `package.json`
`"license"` field; traced Dockerfile base images; walked
`contracts/lib/` tree.

---

## 3. License Posture by Upstream Module

### 3.1 Custom Lux licenses (LEL v1.2 / LRL-PR v1.0)

Highest-risk category. Bespoke licenses at `~/work/lux/{module}/LICENSE`.

- **LEL v1.2** (`~/work/lux/consensus/LICENSE:1-122`): royalty-free for
  Research Use, operation on Lux Primary Network (NetworkID=1, ChainID=
  96369), Lux testnets/devnets, "L1/L2/L3 chains descending from the Lux
  Primary Network", and Lux-ecosystem apps. Forbids forks, competing
  networks, commercial use outside Lux ecosystem. "Zero tolerance for
  unauthorized forks" (§4). Patents reserved (§5). Terminates on breach
  (§8). Delaware law.
- **LRL-PR v1.0** (`~/work/lux/vm/LICENSE:1-159`): research-only by
  default; commercial use of patented tech requires separate license;
  §5 auto-licenses node operation on Lux mainnet/testnet only (no
  Descending Chain carve-out); §6 demands patent assignment on
  contributions.

**LEL-licensed modules consumed by Liquidity**: `consensus`, `crypto`,
`mpc`, `threshold`, `ringtail`, `fhe`, `lattice/v7`, `quasar`, `hsm`,
`captable`, `broker`, `treasury`, `transfer`, `compliance`, `corona`,
`warp`, `aml`, `exchange` (npm), `precompile`, `ai`, plus `hanzoai/mpc`.

**LRL-PR-licensed modules consumed by Liquidity**: `luxfi/vm` (direct:
evm/, dex/, fhe/), `dex` (Go matching engine), `sampler`, `staking`.

Direct importers per service in Appendix A.

**Risk**: Liquid EVM chains use primary networkID=1/2/3/1337 + EVM ChainID
8675309/10/12, with their own validator set, LQDTY token, and no
consensus-security derivation from Lux mainnet. Whether they qualify as
"Descending Chains" under LEL §1 is a fact question about chain
anchoring. Without written confirmation, LEL §3(c)-(e) (no-commercial-
outside-ecosystem, no-competing-networks) activate and §8 termination
applies on breach. Explicit recognition/license letter needed.

**Patent reservation**: LEL §5 + LRL-PR §4 reserve all patents.
`luxfi/vm/LICENSE:13-26` enumerates patent-pending claims: Unified VM
Execution Interface, PQ State Verification, AI-Optimized Bytecode,
Cross-Chain VM Sync, Deterministic Gas Metering, Modular VM Architecture.
Liquid EVM uses these. Separate patent grant required.

### 3.2 Copyleft Lux licenses (LGPL-3.0 / GPL-3.0)

| Upstream | License | Direct importers | Trigger |
|---|---|---|---|
| `luxfi/evm` | LGPL-3.0 (`~/work/lux/evm/LICENSE:1-3`) | `evm/go.mod:8`, lqd node binary | §6: re-link permission, source on request, mark modifications |
| `luxfi/evmgpu` | LGPL-3.0 | optional GPU build | Same |
| `luxfi/erc-3643` | GPL-3.0 (`~/work/lux/erc-3643/LICENSE.md`) | vendored at `contracts/lib/erc-3643/`, every SecurityToken | §5 propagation to combined work |
| `luxfi/onchain-id` | GPL-3.0 (`~/work/lux/onchain-id/LICENSE.md`) | `contracts/lib/onchain-id/`, every investor identity | Same |
| `@luxfi/wallet` npm | **CONFLICT** — `package.json:"license":"GPL-3.0-or-later"` vs LICENSE file LEL v1.2 | `exchange/apps/web/package.json:41`, `wallet/apps/extension/package.json:30` | Treat as GPL until reconciled |
| `luxfi/safe-frost` | GPL-3.0 | indirect | Distribution of derivative |

**LGPL-3.0** for `luxfi/evm`: server-side static-link Go binary satisfies
§6 by distributing corresponding source (Lux publishes at
github.com/luxfi/evm) plus build instructions. Liquidity's own app code is
not affected. Required: (a) LGPL notice in distributed binary, (b)
source available on request, (c) mark modifications. `liquidityio/node`
is a derivative — confirm its release artifacts carry the LGPL notice and
a corresponding-source pointer.

**GPL-3.0** for ERC-3643 + OnchainID: §5 propagates to combined works.
Liquidity's 12,796 deployed SecurityTokens (devnet, per
`contracts/CLAUDE.md`) inherit GPL on bytecode. Public-chain deployment
is "distribution" under most readings; bytecode is freely re-usable
under GPL. This is in tension with LEL's proprietary stance on the rest
of the Lux stack — consistency check needed.

### 3.3 Permissive Lux licenses (BSD-3, MIT, Apache-2.0)

Attribution only.
- **BSD-3-Clause** (~50 modules): the entire `luxfi/node` + `sdk` + `geth`
  + `api` + `database` + `p2p` + `codec` core plus all infra utilities
  (`log`, `ids`, `keys`, `keychain`, `genesis`, `go-bip32/39`, `utxo`,
  `protocol`, `math`, `cache`, `chains`, `metric`, `rpc`, `tls`, `trace`,
  etc.). Full list extractable from `~/work/lux/*/LICENSE` headers.
- **MIT**: `luxfi/dwallet`, `mock`, `indexer`, `pq`.
- **Apache-2.0**: `luxfi/zapdb`, `pulsar`, `securities`, `iam`, `magnetar`,
  `ledger`, `qzmq`, `pqsafe`, `pqrns`.
- **Dual MIT OR Apache-2.0**: `luxfi/p3q-evm`, `pq-profile-ids`.
- **No LICENSE file**: `luxfi/p3q` plus modules in Appendix B.

### 3.4 Hanzo modules

- **MIT**: `hanzoai/base` (ats/bd/ta/mpc), `dbx` (ats/ta/mpc), `orm` (mpc),
  `commerce` (bd), `tasks`, `gateway`, `ingress`, `kms` (Hanzo-authored,
  derived from Infisical MIT per `~/work/hanzo/kms/LICENSE:1-15`).
- **Apache-2.0**: `hanzoai/iam` (basis of `liquidity/iam`, pinned at fork
  `liquidityio/iam v1.14.29`), `authz`, `authzstore`, `pubsub-go`, `age`,
  `datastore`, `datastore-go`.
- **BSD-2-Clause via go-redis**: `hanzoai/kv-go/v9` (mpc).
- **`hanzoai/replicate`**: has LICENSE; SPDX needs verification with Hanzo
  legal. Used in ats/bd.
- **`hanzoai/mpc`**: namespace says Hanzo, LICENSE file
  (`~/work/hanzo/mpc/LICENSE:1`) is **Lux Ecosystem License v1.2**. Track
  who owns the copyright; treat as Lux-licensed.
- **No LICENSE file** (each needs explicit upstream LICENSE or written
  grant to Liquidity): `hanzoai/rollout` (used directly by
  `liquidity/operator`), `hanzoai/sqlite`, `hanzoai/s3`, `hanzoai/ltx`,
  `hanzoai/lz4`, `hanzoai/futures` — all part of the production
  replication stack. Default copyright law grants no rights absent a
  license; must be fixed before mainnet.

### 3.5 Solidity third-party libraries under `contracts/lib/`

`lux/standard` (BSD-3) is vendored at `contracts/lib/standard/` and itself
vendors DeFi protocol code at `lib/standard/lib/`. `foundry.toml` remaps
these as `@openzeppelin/...` and `@luxfi/standard/...`.

- **MIT (clean)**: `openzeppelin-contracts`, `openzeppelin-contracts-upgradeable`
  (basis of every deployed token), `prb-math`, `solmate`, `alchemix-v2/v3`,
  `base64`, `gmx-v1`.
- **BUSL-1.1**: `aave-v3`, `compound-v3`, `gmx-v2`, `uni-v3`, `pendle`
  (parameters), `morpho-blue` (dual GPL-2.0 OR BUSL-1.1).
- **GPL-2.0/3.0**: `lido`, `balancer`, `uni-v2`, `uni-v3-periphery`,
  `uni-lib`, `account-abstraction`, `safe-frost`.
- **LGPL-3.0**: `safe-modules`, `safe-smart-account`.
- **Proprietary/reference-only**: `seaport` (Ozone Networks), `curve`
  (Swiss Stake AG), `compound-v2`, `layerzero-v2`.
- **No top-level LICENSE**: `chainlink`, `pyth`, `manifoldxyz` — per-file
  SPDX headers; review file-by-file if imported.

Per `contracts/CLAUDE.md`, only `src/` contracts (USDL, WLQDTY,
LiquidToken, TokenSwap, OracleMirroredAMM, LiquidityPool, BatchTransfer,
SBA7Token, AssetNFT, MultisigWallet, LoanRegistry, SubstrateMigration)
plus `SecurityToken` (from `@luxfi/standard/securities/factory`) are
deployed today. None of the BUSL/GPL DeFi protocols are. They are
present in the tree and `remappings.txt` resolves them — recommend a CI
lint rule denying imports from `lib/standard/lib/{aave-v3,compound-v3,gmx-v2,uni-v3,morpho-blue,pendle,lido,balancer,uni-v2,uni-v3-periphery,uni-lib,account-abstraction,safe-modules,safe-smart-account,safe-frost}`.

### 3.6 Container base images

- Frontend (`exchange`, `platform`, `superadmin`, `swap`):
  `FROM ghcr.io/hanzoai/spa:1.2.0` — Hanzo SPA base, license per Hanzo
  (likely MIT, confirm).
- Static doc sites (`papers`, `contracts`, `proofs`, `docs`, `internal`):
  Liquidity-built `liquidityio/static`.
- Chain validator `liquidityio/lqd-node`: `golang:1.26` → `alpine`/`debian`;
  statically links LGPL-3.0 (`luxfi/evm`) + LEL (`consensus`, `mpc`,
  `precompile`) + Apache (`zapdb`) + many BSD-3 modules.
- Backend services (`ats`, `bd`, `ta`, `kms`, `gateway`, `ingress`,
  `operator`, `fhe`, `explorer`, `goa`): built from source via cloud
  build, inherit upstream licenses.

---

## 4. Three Buckets

### Bucket 1 — Free OSS (attribution only)

All BSD-3, MIT, Apache-2.0, dual MIT/Apache, and BSD-2 modules listed in
§3.3 and §3.4, plus the MIT Solidity libraries listed in §3.5
(OpenZeppelin, prb-math, Solmate, base64, gmx-v1, alchemix-v2/v3). No
license action required beyond attribution / LICENSE bundling in
distributed artifacts.

**Action**: ensure each distributed Liquidity binary carries the bundled
LICENSE notices (Go practice: a `NOTICES` file or embedded `go-licenses`
output). Confirm tooling ships NOTICES in lqd, ats, bd, ta, mpc, operator
container images.

### Bucket 2 — OSS with compliance obligations

- **`luxfi/evm` + `luxfi/evmgpu` (LGPL-3.0)**: embedded in lqd validator.
  Ship LGPL notice in image, make modified source available, permit
  re-link. Liquidity app code unaffected. Confirm `liquidityio/node`
  Dockerfile bundles LGPL notice + corresponding-source pointer.
- **`luxfi/erc-3643` + `luxfi/onchain-id` (GPL-3.0)**: every deployed
  SecurityToken and investor OnchainID inherits GPL on bytecode.
  Acknowledge in publication; Solidity source must be available on
  request.
- **`luxfi/safe-frost` (GPL-3.0)**: if shipped, same as ERC-3643. Indirect
  only today.
- **`@luxfi/wallet` npm (GPL-3.0-or-later per package.json, LEL per
  LICENSE)**: reconcile with Lux. Until then treat as GPL and bundle
  source notice in exchange + wallet SPAs.
- **Solidity third-party BUSL/GPL/LGPL libs** (§3.5): not deployed today;
  present in build tree. Add CI lint denying imports from the listed
  directories.

### Bucket 3 — Custom / commercial license required

- **All LEL v1.2 modules** consumed by Liquidity (~21, listed in §3.1).
  Agreement must cover: (a) recognition that Liquid EVM mainnet/testnet/
  devnet (chain IDs 8675309/8675310/8675312, primary networkIDs 1/2/3/
  1337) are "Authorized Networks" / "Descending Chains" under LEL §1;
  OR (b) a separate commercial license outside the ecosystem-restricted
  grant; (c) attribution; (d) treatment of contributions.
- **All LRL-PR v1.0 modules** (`luxfi/vm`, `dex` Go, `sampler`, `staking`).
  Must include explicit patent license under current and future Lux
  patents covering Unified VM Execution, PQ State Verification,
  AI-Optimized Bytecode, Cross-Chain VM Sync, Deterministic Gas Metering,
  Modular VM Architecture, and any Quasar/Ringtail/FHE methods. Without
  this, Lux can assert patent infringement against Liquidity's commercial
  use.
- **Modules with NO LICENSE FILE** (default copyright, no rights granted).
  Each needs upstream LICENSE or written grant. Full list in Appendix B.
- **`@luxfi/wallet` LICENSE-vs-package.json conflict** — resolve before
  shipping exchange/wallet bundles.

---

## 5. Per-License Rollup

| License | # modules | Liquidity services touched | Action |
|---|---|---|---|
| BSD-3-Clause | ~50 | ats, bd, ta, mpc, cli, node, evm, dex, fhe, contracts, operator, sdk-go, genesis, iam, kms, gateway, ingress | Attribution; bundle NOTICES |
| MIT | ~15 | all Go services + all Solidity tokens | Attribution |
| Apache-2.0 | ~10 | iam, kms, mpc, validators | Attribution + state-of-modifications |
| Dual MIT OR Apache-2.0 | 2 | indirect | Pick one (MIT) |
| BSD-2-Clause | 1 (kv-go) | mpc | Attribution |
| **LGPL-3.0** | 2 (evm, evmgpu) | lqd node, evm service | Bundle LGPL notice + source pointer + re-link |
| **GPL-3.0** | 3 (erc-3643, onchain-id, safe-frost) + `@luxfi/wallet` npm | every SecurityToken; exchange + wallet SPA | Publish source on request |
| **BUSL-1.1** | 5 (aave-v3, compound-v3, gmx-v2, uni-v3, morpho-blue) | not deployed; in build tree | CI guardrail |
| **LEL v1.2** | ~21 | every Go service; lqd node; exchange UI | **Commercial agreement** recognizing Liquid as Authorized/Descending |
| **LRL-PR v1.0** | 4 (vm, dex-Go, sampler, staking) | evm, dex, cli, validators | **Commercial + patent** license |
| **NO LICENSE FILE** | ~20 (Appendix B) | various | Add LICENSE upstream or written grant |

---

## 6. Top Three Risks

1. **LEL coverage of Liquid chains is ambiguous.** LEL §1 defines
   "Authorized Network" as Lux Primary Network + any "Descending Chain"
   deriving security from it. Liquid chains are independent L1s with
   their own validator set + LQDTY token, no consensus-security
   derivation from Lux mainnet. Without written confirmation, LEL §3
   (no-commercial-outside-ecosystem), §4 (no-fork), §8 (terminate on
   breach) apply. Termination invalidates Liquidity's use of MPC,
   threshold, consensus, FHE, precompile, broker, treasury, transfer,
   captable, compliance, and ~12 other core modules.

2. **LGPL-3.0 obligations on the Liquid EVM binary are not visible in
   release artifacts.** `luxfi/evm` (LGPL-3.0) is statically linked into
   every `lqd` node image. Without LGPL notice, corresponding-source
   URL, and re-link provisions, Liquidity is in technical breach of §6.
   Practically easy to fix; unfixed it is a compliance gap.

3. **GPL-3.0 propagation through every SecurityToken on three live
   chains.** `luxfi/erc-3643` + `onchain-id` are GPL-3.0. Every deployed
   SecurityToken (12,796 on devnet) and OnchainID inherits GPL on
   bytecode. Bytecode is freely re-usable under GPL, inconsistent with
   LEL's proprietary stance on the rest of the stack and limits
   exclusivity. Confirm intent with Lux; if GPL is intended (consistent
   with Tokeny T-REX upstream lineage), document; if not, relicense
   upstream.

## 7. Top Three Clean Wins

1. **The `luxfi/node` + `sdk` + `geth` + `database` + `p2p` + `api`
   foundation is BSD-3-Clause.** Largest dependency surface; attribution
   only. Confirms "Liquidity as Lux ecosystem participant" at the
   infrastructure layer.

2. **Hanzo stack is essentially MIT/Apache** (`base`, `dbx`, `orm`,
   `commerce`, `iam`, `kms`, `gateway`, `ingress`, `tasks`, `pubsub-go`,
   `authz`, `age`, `datastore`). The one LEL exception (`hanzoai/mpc`)
   is mirrored by `luxfi/mpc` and covered by the same Lux agreement.

3. **OpenZeppelin (MIT) underpins every deployed token.** Liquidity's
   `src/` Solidity (USDL, WLQDTY, LiquidToken, TokenSwap,
   OracleMirroredAMM, LiquidityPool, BatchTransfer) inherits MIT — no
   copyleft from this layer.

## 8. Recommended Next Step

Draft a **Lux ↔ Satschel/Liquidity License & Patent Agreement** with three
sections:

A. **Authorized Network designation** — written confirmation that Liquid
EVM mainnet/testnet/devnet are "Authorized Networks" / "Descending
Chains" under LEL v1.2 §1, eliminating §3 commercial-use restriction and
§4 fork prohibition.

B. **Patent license grant** — explicit commercial patent license under
current and future Lux patents covering LRL-PR modules (`vm`, `dex` Go,
`sampler`, `staking`) and patents applicable to Liquid EVM precompiles,
Quasar consensus, FHE modules, MPC/threshold, and PQ schemes (Ringtail,
ML-DSA, ML-KEM, SLH-DSA).

C. **License-clarity remediation** — (i) add LICENSE files to the ~20
modules currently without one (Appendix B); (ii) resolve the
`@luxfi/wallet` LICENSE-vs-package.json conflict; (iii) decide whether
`luxfi/erc-3643` and `luxfi/onchain-id` remain GPL-3.0 or migrate to LEL.

No contract language suggested — drafting is for counsel.

---

## Appendix A — Direct Liquidity → Lux/Hanzo dependency map

- `ats/go.mod`: hanzoai/{base, dbx, replicate}; luxfi/{broker, cex, compliance, hsm, log, treasury, zap}
- `bd/go.mod`: hanzoai/{base, commerce, replicate}; luxfi/{broker, compliance, crypto, hsm, log, zap, mpc}
- `ta/go.mod`: hanzoai/{base, dbx}; luxfi/{captable, crypto, hsm, log, transfer, treasury, zap}
- `mpc/go.mod`: declares `module github.com/luxfi/mpc` (Liquidity MPC IS Lux MPC); hanzoai/{base, dbx, kv-go, orm}; luxfi/{crypto, database, fhe, hsm, log, metric, threshold}
- `evm/go.mod`: luxfi/{evm, geth, log, precompile, sys, version, vm}
- `cli/go.mod` + `node/go.mod`: luxfi/{sdk, api, constants, crypto, formatting, genesis, go-bip32, go-bip39, ids, math, node, protocol, utxo} (+ cli: pq, staking)
- `dex/go.mod`: luxfi/{broker, cex, log, node, sys, vm}
- `fhe/go.mod`: luxfi/{log, node, sys, vm} (+ lattice/v7 transitively)
- `contracts/go.mod`: luxfi/{crypto, go-bip32, go-bip39, ids, math, proto, sdk, utxo}
- `contracts/foundry.toml`: `@luxfi/standard/` → `contracts/lib/standard/contracts/` (BSD-3 wrapper) over erc-3643 (GPL-3.0) + onchain-id (GPL-3.0) + DeFi BUSL/GPL/MIT mix
- `operator/Cargo.toml`: `license = "BSD-3-Clause"`; hanzoai/rollout (no LICENSE), luxfi/crypto, luxfi/go-bip39
- `exchange/apps/web/package.json:40-41`: @luxfi/{dex, exchange, wallet}
- `swap/apps/web/package.json:18`: @luxfi/exchange
- `wallet/apps/extension/package.json:30`: @luxfi/{utilities, wallet}

## Appendix B — Modules with NO LICENSE FILE

Highest-priority Lux/Hanzo legal items — add LICENSE upstream OR issue
written grant to Liquidity.

- **Lux**: `edwards25519`, `logger`, `protocol` (root), `cex`, `p3q`,
  `pulsar-mptc`, `prism`, `pulsarm`, `mlkem`, `mldsa`, `slhdsa`,
  `lattice/v7` (sub), `blake3`, `futures`, `financial-docs`, `gpu`,
  `homebrew-tap`, `amm`, `market`, `pool`, `manifoldxyz`, `chainlink`,
  `pyth`.
- **Hanzo**: `rollout`, `sqlite`, `s3`, `ltx`, `lz4`, `futures`.

End of memo.
