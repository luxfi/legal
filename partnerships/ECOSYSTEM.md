# Lux × Local Partner — Ecosystem Registry

Canonical list of named Lux ecosystem partnerships. Every partnership
is governed by the Lux × Local Partner Strategic Partnership Agreement
template (`template/`), customised per counterparty. All share the
**50/50 net partnership revenue above documented costs** commercial
structure, Delaware governing law, and Wilmington AAA arbitration.

Partners interoperate via the Lux backend (`bankd`, `treasuryd`,
`forexd`, `brokerd`, `amld`, `bridge`, `kms`, `mpc`) and the
`@luxfi/brand` white-label tenant override mechanism.

## Registry

| Reference | Partner | Region | Role |
|---|---|---|---|
| `OG-SP-2026-SFPB` | SF Private Bank | United States + Canada | US chartered private bank + BD + ATS + TA + FinCEN MSB + state money-transmitter + CIRO + CSA + FINTRAC stack; operat… |
| `OG-SP-2026-SOGO` | SogoTrade, Inc. | United States | US registered broker-dealer; introduction + execution + distribution of US securities to a retail customer base. |
| `OG-SP-2026-AVA` | AvaTrade Ltd. | Ireland / EU / Australia / South Africa / UK / Japan / BVI / UAE. | Multi-jurisdiction regulated retail brokerage group (Ireland Central Bank, ASIC, FSCA, FCA, JFSA, BVI FSC, ADGM FSRA). |
| `OG-SP-2026-ATM` | Atmen Ltd. | United Kingdom | Culture-led consumer banking and payments application (“Atmen --- Culture meets Currency”) serving an international d… |
| `OG-SP-2026-SSB` | Salaam Somali Bank | Somalia + Horn of Africa diaspora | Somalia’s first privately owned commercial bank (2009); ~45% market share; ISO 9001:2015 certified; SWIFT member; pri… |

## Per-partner detail

### SF Private Bank

- **Reference**: `OG-SP-2026-SFPB`
- **Region**: United States + Canada
- **Role**: US chartered private bank + BD + ATS + TA + FinCEN MSB + state money-transmitter + CIRO + CSA + FINTRAC stack; operator of SF Private Pay (PSP) including Zeekash agent rails and MyATMen ATM network; card issuance; merchant acquiring.
- **Coordination with other partners**: Provides the regulated US/CA bank, BD, PSP, and card-issuance rails that every other named Lux ecosystem partner can plug into via the Lux backend (treasury / forex / bankd / amld).
- **Status**: Brief delivered (sfpb_integration_brief.pdf); awaiting kickoff per §7 of the brief.
- **Agreement file**: `partnerships/sfpb/Lux_*_Strategic_Partnership_Agreement.{docx,pdf}`

### SogoTrade, Inc.

- **Reference**: `OG-SP-2026-SOGO`
- **Region**: United States
- **Role**: US registered broker-dealer; introduction + execution + distribution of US securities to a retail customer base.
- **Coordination with other partners**: Uses SFPB for ACH/wire settlement, card-funded buy-side deposits, and (optionally) the SF Private Bank ATS as an additional execution venue. Customer KYC via Simplici.io with WRA reliance from SFPB.
- **Status**: Agreement delivered.
- **Agreement file**: `partnerships/sogotrade/Lux_*_Strategic_Partnership_Agreement.{docx,pdf}`

### AvaTrade Ltd.

- **Reference**: `OG-SP-2026-AVA`
- **Region**: Ireland / EU / Australia / South Africa / UK / Japan / BVI / UAE.
- **Role**: Multi-jurisdiction regulated retail brokerage group (Ireland Central Bank, ASIC, FSCA, FCA, JFSA, BVI FSC, ADGM FSRA).
- **Coordination with other partners**: Uses SFPB for US-side IBAN equivalents (ACH + Fedwire), card funding via SF Private Pay, and access to the SF Private Bank ATS for US securities sleeves. Cross-currency settlement via forex/currencycloud and SFPB-coordinated FX. Customer onboarding via Simplici.io.
- **Status**: Agreement delivered.
- **Agreement file**: `partnerships/avatrade/Lux_*_Strategic_Partnership_Agreement.{docx,pdf}`

### Atmen Ltd.

- **Reference**: `OG-SP-2026-ATM`
- **Region**: United Kingdom
- **Role**: Culture-led consumer banking and payments application (“Atmen --- Culture meets Currency”) serving an international diaspora customer base.
- **Coordination with other partners**: Uses SFPB for US-dollar deposit accounts, US-issued cards, ACH/wire/FedNow settlement, and stablecoin on/off-ramp. Cross-border GBP ↔ USD via forex/currencycloud + SFPB. Customer onboarding via Simplici.io. Reliance Agreement with SFPB for CIP records.
- **Status**: Agreement delivered.
- **Agreement file**: `partnerships/atmen/Lux_*_Strategic_Partnership_Agreement.{docx,pdf}`

### Salaam Somali Bank

- **Reference**: `OG-SP-2026-SSB`
- **Region**: Somalia + Horn of Africa diaspora
- **Role**: Somalia’s first privately owned commercial bank (2009); ~45% market share; ISO 9001:2015 certified; SWIFT member; primary banker of the Somali Federal Government; full Shariah-compliant product set (Murabahah, Mudharabah, Musharakah, Ijaarah).
- **Coordination with other partners**: Uses SFPB for the US/CA diaspora corridor (SFPay cash-in, card issuance to diaspora customers, USD wire settlement, Reg D 506(c) / Reg S Mudharabah subscriptions through SF Private Bank’s BD + ATS). Customer onboarding via Simplici.io with WRA reliance from both sides. Shariah Supervisory Board approval of every on-chain Mudharabah / Murabahah representation. Drought-linked parametric Takaful settled in stablecoin on Lux Network.
- **Status**: Strategic paper delivered (papers/lux-ssb-partnership/). Agreement generated in this session.
- **Agreement file**: `partnerships/ssb/Lux_*_Strategic_Partnership_Agreement.{docx,pdf}`

## Adding a new partner

1. Copy `template/Lux_LocalPartner_Strategic_Partnership_Agreement_TEMPLATE.docx` into a new `<partner-key>/` subdirectory.
2. Fill in counterparty fields (legal name, jurisdiction, registered office, ID, business description, license-stack rows).
3. Append the Annex B — Lux Ecosystem Cross-Reference (the generator at `/tmp/agreements/append_ecosystem.py` does this automatically).
4. Assign a reference number `OG-SP-2026-<short>` and add an entry to this registry.
5. Commit + push.

## Confidentiality

All per-partner agreements are confidential between Lux Industries Inc. and the named counterparty. The SFPB integration brief (`partnerships/sfpb/sfpb_integration_brief.pdf`) is **CONFIDENTIAL — pre-decisional**. Do not distribute outside the bilateral relationship.

This file itself is internal to `luxfi/legal` (PRIVATE repo).
