# Alpaca Clearing-BD Diligence Materials (Preserved on Disk)

The Counterparty's Alpaca-side clearing-broker-dealer diligence materials
are **preserved on the operator's local disk** at:

```
~/work/lux/legal/liquidity/exhibits/alpaca-liquidity-bd/
```

They are **deliberately excluded from git history** (per `.gitignore`) because:
- Several files contain PII (Eric Choi government-ID images front + back).
- Several files are signed personal beneficial-ownership certifications.
- The subtree contains Counterparty employees' signed diligence documents.
- Counsel will produce specific exhibits on subpoena / discovery from the
  preserved on-disk copy, rather than via git distribution.

## Inventory (high-level)

- **Alpaca general partner docs** (4 PDFs): Broker API integration guide
  v2025, "Understanding the CIP API" v8.2025, US Tech Partner Guidelines,
  Statement & Trade Confirmation Requirements v.2025.05.
- **`LIVE/` subdir** — production-tier diligence pack:
  - LIVE Due Diligence Checklist v052025.
  - Live Broker API Partner Form V10025 (signed by Liquidity).
  - `LIVE/Beneficial Owner Information - additional DD requirements/`:
    Eric Choi ID front + back; Corporate Entities Org Chart;
    Beneficial Ownership Certification v.5.25 (template + Liquidity-signed
    copy).
  - `LIVE/Submitted/` — final signed submissions.
- **`Limited Live/` subdir** — limited-tier intermediate-state diligence.
- **Root** — `LiveBrokerAPIPartnerForm-V100251_Liquidity_SIGNED.pdf`.

## Evidentiary use

Referenced from §IV.A(3) ("October–December 2025 critical Counterparty-
enabling work") of `Lux_IP_Enforcement_Memorandum_2026_05_25.tex`. The
materials corroborate Mr. Kelling's personal introduction of Alpaca as
the Counterparty's clearing BD and his / the Lux engineering team's
Alpaca-integration exchange-tech work over Q4 2025 that enabled the
Counterparty's ATS to launch in its current commercial form.

## Production protocol

Counsel may request specific files by path; the operator will produce
under attorney-client privilege / work-product designation as applicable.
The full subtree may be sealed-filed if litigation proceeds.
