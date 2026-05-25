# SF Private Bank ↔ Lux Industries — Integration Brief

**Audience:** SF Private Bank technical + commercial leadership.
**Purpose:** what we (Lux Industries) need from SFPB to leverage the SFPB
banking stack — SF Private Pay (PSP), multi-currency accounts and IBANs,
card issuance, and merchant acquiring — under the Lux × Local Partner
Strategic Partnership Agreement (50/50 above documented costs).
**Confidentiality:** confidential between Lux Industries Inc. and
SF Private Bank. Not for distribution. Drafted as an internal working
document, not a contract.

---

## 0. Context

Lux Industries operates a native, regulator-neutral financial backend
(`bankd` ledger, `forexd` FX engine, `brokerd` smart order router,
`treasuryd` double-entry ledger + 14 leaf adapters, `amld` AML/sanctions,
`@luxfi/bridge` cross-chain MPC, `lux/kms` HSM-backed key custody,
`lux/mpc` threshold signing). The customer surfaces sit on top:
`lux.financial` (marketing + product), `app.lux.financial` (operational
console), per-tenant white-label deploys for downstream partners.

SF Private Bank holds the US chartered-bank + BD + ATS + TA + FinCEN MSB
+ state money-transmitter + CIRO + CSA + FINTRAC license stack and
operates SF Private Pay (Zeekash agent rails, MyATMen ATM network, card
issuance, ACH/wire/FedNow, stablecoin on/off-ramp).

The partnership is **50/50 net partnership revenue above documented
costs**, per the Lux × Local Partner Strategic Partnership Agreement
template already shared. This brief enumerates exactly what we need from
SFPB at the technical, commercial, and compliance layers so we can wire
the integration and start producing partnership revenue.

---

## 1. SF Private Pay (PSP)

### What SFPB gives us
A regulated US-side payment service provider product covering card
acceptance, alternative payment methods, agent cash rails (Zeekash),
ATM rails (MyATMen), card issuance, ACH/wire/FedNow, and stablecoin
on/off-ramp.

### What we need from SFPB

#### Technical
- **API base URLs** — production + sandbox.
- **API documentation** — full OpenAPI/Swagger or equivalent spec
  covering every endpoint (auth, accounts, customers, payments,
  payouts, refunds, disputes, reports).
- **Auth model** — OAuth client_credentials, API key + HMAC, mTLS, or
  signed JWT. Token rotation policy and rate limits.
- **Webhook spec** — per event type (`payment.authorized`,
  `payment.captured`, `payment.failed`, `payout.completed`,
  `dispute.opened`, `chargeback.received`, etc.) with payload schema,
  HMAC signature header + algorithm, retry policy, idempotency-key
  header convention. We will subscribe at `https://api.lux.financial/
  webhooks/sfpay/<event_type>` with HMAC verification before our
  callback handler accepts.
- **Idempotency-key convention** — header name and how SFPB dedupes.
- **Test credit card numbers** + test bank routing/account numbers +
  sandbox failure scenarios (insufficient funds, sanctions hit, KYC
  mismatch, fraud reject, dispute).
- **Rate limits** — per-key request/minute, burst, and tier.

#### Capability matrix (one row per rail we plan to surface)

| Rail | Direction | Sandbox? | Production? | Settlement T+? | Per-tx limit | Fee schedule |
|---|---|---|---|---|---|---|
| Card acceptance (Visa/MC/AMEX/Discover) | in | ? | ? | ? | ? | ? |
| Card-not-present (e-com) | in | ? | ? | ? | ? | ? |
| Card-present (POS) | in | ? | ? | ? | ? | ? |
| ACH debit | in | ? | ? | ? | ? | ? |
| ACH credit | out | ? | ? | ? | ? | ? |
| FedNow | in/out | ? | ? | ? | ? | ? |
| RTP (TCH) | in/out | ? | ? | ? | ? | ? |
| Wire (Fedwire) | in/out | ? | ? | ? | ? | ? |
| Wire (CHIPS) | out | ? | ? | ? | ? | ? |
| SWIFT MT103 | in/out | ? | ? | ? | ? | ? |
| Interac (Canada) | in/out | ? | ? | ? | ? | ? |
| Zeekash agent cash-in | in | ? | ? | ? | ? | ? |
| Zeekash agent cash-out | out | ? | ? | ? | ? | ? |
| MyATMen deposit | in | ? | ? | ? | ? | ? |
| MyATMen withdrawal | out | ? | ? | ? | ? | ? |
| Stablecoin (USDC/USDT) on-ramp | in | ? | ? | ? | ? | ? |
| Stablecoin off-ramp | out | ? | ? | ? | ? | ? |

#### Commercial
- **Fee schedule** for each rail (per-transaction, percentage, monthly
  minimum).
- **Settlement mechanics** — when funds clear; holdback / reserve
  requirements; FBO vs direct deposit.
- **Revenue-share** mechanics confirming compatibility with the 50/50
  above documented costs structure in the partnership agreement.
- **Reporting feeds** — daily reconciliation (CSV/JSON SFTP or webhook
  push), per-merchant breakdown, fee detail, dispute aging.
- **Chargeback / dispute liability** — who carries the reserve, what's
  the partner-side process.

#### Compliance
- **Shared responsibility matrix** explicitly stating who performs:
  KYC, KYB, OFAC sanctions screening, PEP screening, AML transaction
  monitoring, BSA SAR filing, CTR filing, FBAR, FATCA, Reg E disputes,
  Reg Z disclosures, PCI-DSS scope ownership.
- **PCI-DSS scope** — does SFPay tokenise on the iframe / hosted
  fields so we stay out of scope, or do we need full SAQ D?
- **Card-network rules attestation** — Visa CISP, Mastercard SDP, AMEX
  DSOP compliance evidence for SFPay's acquiring stack.

### Lux integration target
`treasury/pkg/provider/sfpay/` — new adapter implementing the standard
`Provider` interface (CreateAccount, CreatePayment, GetPayment,
ListPayments, GetBalance, GetFXQuote/CreateFXConversion if multi-
currency, CreateCounterparty, Capabilities). Env-gated on
`SFPAY_API_KEY`. Webhook ingest at `forexd` or `bankd` with HMAC verify.

---

## 2. Multi-currency accounts + IBAN issuance

### What SFPB gives us
Account issuance across the SFPB regulated perimeter — USD accounts with
ABA routing + account number (US); CAD accounts with transit + account
(Canada); GBP, EUR, and other currencies via partner EMI relationships
or correspondent banks; named or virtual IBANs where the partner offers
SEPA / Faster Payments access.

### What we need from SFPB

#### Technical
- **Account types** SFPB can issue: checking, savings, custodial (FBO),
  virtual sub-account, escrow.
- **Account-issuance API** — create per-customer account, list,
  freeze, close. Per-customer KYC payload requirements.
- **Multi-currency support** — which currencies natively, which via
  partner EMI, settlement mechanics for cross-currency transfers.
- **IBAN issuance** — does SFPB issue named GBP / EUR IBANs directly
  or via a UK/EU EMI partner? If partner: who, what passport,
  shared-responsibility mapping. Or: do we provide our own EU EMI
  partner and use SFPB only for US/CA?
- **Sweep / cash-management** — overnight sweep, balance interest if
  any, target-balance rules.
- **Statement + reporting** API — daily balance feed, transaction
  detail, year-end 1099 / equivalent.

#### Commercial
- **Per-account monthly fee** schedule.
- **Per-transaction fees** for each outbound rail at the account
  level (separate from PSP merchant acquiring).
- **Interest-bearing accounts** — interest split if any.
- **Minimum balance / reserve** required to maintain account.

#### Compliance
- **CDD requirements** per customer type (US natural person, US legal
  entity, US trust, foreign natural person, foreign legal entity).
  Document checklist + acceptable ID types.
- **OFAC screening cadence** — onboarding + per-transaction +
  ongoing.
- **CIP/BSA reliance** — can SFPB rely on Simplici.io's KYC/CIP
  results under a Reliance Agreement (WRA), or does SFPB require
  independent CDD? Reliance Agreement template?
- **Reg E** dispute handling responsibility.
- **State money-transmitter** licensing footprint — does SFPB cover
  all 50 states or do we route around unlicensed states?

### Lux integration target
`treasury/pkg/provider/sfpb-accounts/` — implements `CreateAccount`,
`GetAccount`, `ListAccounts`, `GetBalance`, `CreateCounterparty` end-to-
end; routes outbound payment rails through SFPay (above) or directly
where SFPB's account API exposes them.

---

## 3. Card issuance

### What SFPB gives us
BIN sponsorship via SFPB's Visa and/or Mastercard principal membership;
issuance of debit, prepaid, and (where applicable) credit cards under
our brand or partner-tenant brand, physical and virtual.

### What we need from SFPB

#### Technical
- **Card-issuing platform** — is SFPB on Marqeta, Lithic, Galileo, FIS,
  i2c, in-house? Whatever it is, we need API access (read-only at
  minimum; ideally full create/freeze/replace/cancel).
- **Card product configurations** — debit, prepaid (open-loop, closed-
  loop), credit, virtual-only, single-use, expense-controlled.
- **Funding model** — direct from cardholder account, FBO pooled,
  ledger-backed-on-our-side with daily settlement to SFPB.
- **Auth stream** — real-time authorization webhook (sub-200ms
  decision) with our risk engine (`amld` + custom rules) participating
  in the auth decision. Spec for the auth-request payload + decision
  response.
- **3DS** — 3DS2 challenge integration, ACS provider, fall-back path.
- **Card-network tokenisation** — Visa Token Service / Mastercard MDES
  support for Apple Pay / Google Pay / Samsung Pay.
- **Physical card production** — vendor (Perfect Plastic / CPI / G+D
  Mühlbauer / Tag Systems / Idemia), turnaround, custom artwork
  approval flow, EMV chip personalisation, contactless.
- **PIN management** — PIN issuance, change, unblock; PIN-Verify
  service.
- **Dispute / chargeback** — flow into the network dispute API; SFPB-
  side process for representment + arbitration.

#### Commercial
- **Setup fees** — per BIN, per card product, artwork approval.
- **Per-card fees** — issuance, monthly active, transaction (network
  + processing), 3DS, tokenisation, physical-card production.
- **Interchange revenue share** — the headline economic. Visa/MC
  posted interchange, less network assessments, less processing fees,
  less SFPB take; net interchange flows into the 50/50 partnership
  pool.
- **Cardholder funding** — is there a customer-deposit reserve
  requirement?

#### Compliance
- **KYC for cardholders** — CIP requirements; SFPB-required or our
  WRA-reliance.
- **CARD Act / Reg Z** disclosure ownership for credit / prepaid.
- **Reg E** dispute ownership.
- **OFAC** screening on cardholder onboarding + ongoing.
- **Network rules** — Visa Operating Regulations, Mastercard Rules
  attestation; PCI-DSS compliance scope for cardholder data on our
  side.

### Lux integration target
`treasury/pkg/provider/sfpb-cards/` implements the card-issuance side
of the `Provider` interface (CreateCard, GetCard, FreezeCard,
ReplaceCard, ListTransactionsForCard). Auth-stream webhook handled by
`bankd` with `amld` risk-gate participation. Card-decline reasons
emitted to Lux Network as content-addressed audit events.

---

## 4. Merchant acquiring (PSP card acceptance for our partners)

### What SFPB gives us
Acquiring services for our downstream merchant partners — onboarding,
MID provisioning, settlement, dispute management — across the
jurisdictions where SFPB or its acquiring partner holds the requisite
acquirer licences.

### What we need from SFPB
- **Acquirer jurisdictions** — which Visa / Mastercard regions, plus
  domestic schemes (AMEX, Discover, Diners, JCB, UnionPay, Interac).
- **Onboarding API** — KYB submission, beneficial-ownership
  attestation, MCC assignment, monthly volume cap.
- **Underwriting timeline** — SLA from KYB submitted → MID issued.
- **MID provisioning** — per merchant, per MCC; descriptor rules,
  soft-descriptor support, dynamic-descriptor by transaction.
- **Settlement schedule** — T+N per merchant tier, daily ACH or wire,
  holdback / reserve mechanics.
- **Dispute API** — chargeback receive, representment submit, evidence
  upload, arbitration escalation.
- **Reporting** — per-merchant daily + monthly fee detail, gross +
  net + interchange + assessments + processing.

(Compliance posture inherits from §1 SFPay.)

### Lux integration target
The same `treasury/pkg/provider/sfpay/` adapter handles the
merchant-acquiring surface — same auth, same webhooks, separate
endpoint family.

---

## 5. Operational + commercial requirements (cross-cutting)

#### Operational
- **Sandbox vs production parity** — every endpoint above must work
  in sandbox with realistic data, before production credentials issue.
- **API status page** + status webhook.
- **Maintenance windows** — schedule, advance notice, runbook for
  failover or graceful-degradation.
- **On-call escalation path** — named technical liaison, on-call
  rotation contact, SLA on critical incidents (P0 / P1 / P2 / P3 with
  response + resolution targets).
- **Production cutover plan** — phased rollout (shadow → 1% → 10% →
  100%), per-product enablement, named go/no-go gates.

#### Commercial
- **Documented Costs definition** alignment with the partnership
  agreement (which SFPB-incurred costs count as Documented; e.g.
  network interchange, processing, sponsor fees yes; SFPB overhead /
  marketing / cost of capital no).
- **Net Partnership Revenue reconciliation cadence** — monthly
  statements within 15 business days of month-end, joint reconciliation
  meeting within 5 business days of statement delivery, net wire
  within 30 days.
- **Audit rights** — biannual, on 30 days' notice, at audited party's
  expense if >5% underpayment.
- **Customer markup retention** — SFPB confirms 100% retention of any
  customer-facing markups by either party stays with the marking-up
  party (the standard from the partnership agreement).

#### Compliance shared-responsibility matrix
Annex A to the partnership agreement should formalise the SFPB-side vs
Lux-side regulated-function allocation across:
- BSA / AML programme ownership
- OFAC sanctions screening
- CIP / CDD / EDD
- Suspicious Activity Reports (FinCEN)
- Currency Transaction Reports (FinCEN)
- FBAR / FATCA / CRS / GoAML
- Reg E (electronic fund transfers) dispute resolution
- Reg Z (truth in lending) disclosures
- Reg D (regulation D, account-class restrictions if any)
- Network operating-rules compliance (Visa CISP, MC SDP)
- PCI-DSS scope ownership per integration surface
- Card Act disclosures (where applicable)
- State money-transmitter licensing footprint
- CIRO / CSA Canadian rules
- FCA / FINTRAC / EBA cross-border rules where SFPB extends to those

---

## 6. What we will give SFPB in return (recap from the partnership agreement)

For reference, the symmetric obligations from the partnership agreement
that satisfy SFPB's side of the deal:

- **Simplici.io** white-labelled onboarding, KYC, AML, sanctions, PEP
  with the per-check pass-through pricing in the agreement; SFPB can
  rely on Simplici under a WRA.
- **Lux Network** content-addressed audit substrate covering every
  state transition relevant to SFPB-supervised activity, with
  cryptographic commitments retainable for the durations required by
  CBS, FinCEN, OFAC, FATCA.
- **Identity** — every customer onboarded once, used across every
  product surface (account, card, FX, crypto) with consistent
  reference IDs.
- **Distribution** — our customer base served through SFPB-issued
  accounts, SFPB-issued cards, SFPB-acquired merchants. Concrete
  volume forecast in the partnership-agreement schedule.
- **Net Partnership Revenue** monthly statements and 50/50 settlement
  on the agreed cadence.
- **Operational integration** of our risk and AML rules into the
  SFPB auth stream so SFPB sees consistent risk-gate decisions.

---

## 7. Decision checklist for the joint kickoff call

To convert this into a green-lit project we propose the following items
as agenda for the kickoff:

1. SFPB confirms API documentation will be shared under NDA within 5
   business days.
2. SFPB confirms a sandbox tenant will be provisioned for Lux engineering
   within 10 business days.
3. SFPB confirms the named technical liaison + on-call escalation path.
4. SFPB confirms the shared-responsibility matrix (Annex A above) is
   acceptable in principle and identifies any function it would prefer
   to retain or delegate.
5. SFPB confirms its UK/EU IBAN partner (if any) and the operational
   model for cross-currency settlement.
6. SFPB confirms the card BIN sponsor / issuing platform and any prior
   commercial dependencies (e.g. existing Marqeta or Lithic relationship)
   that we should integrate to vs around.
7. Joint sign-off on the partnership-agreement Annex A
   (shared-responsibility) and Annex B (Documented Costs definition)
   within 15 business days.

---

## 8. What we will deliver after the joint kickoff

| Phase | Deliverable | Owner | ETA from kickoff |
|---|---|---|---|
| 0 | Mutual confidentiality executed | Both | 5 BD |
| 0 | Sandbox creds for SFPay + accounts + cards | SFPB | 10 BD |
| 0 | Annex A + Annex B sign-off | Both | 15 BD |
| 1 | `treasury/pkg/provider/sfpay/` PR open | Lux | 4 wks |
| 1 | `treasury/pkg/provider/sfpb-accounts/` PR open | Lux | 4 wks |
| 1 | `treasury/pkg/provider/sfpb-cards/` PR open | Lux | 6 wks |
| 1 | Shadow-mode pilot (read-only, no funds) | Joint | 8 wks |
| 2 | 1% live traffic gate | Joint | 12 wks |
| 2 | 10% live traffic gate | Joint | 16 wks |
| 3 | 100% live; first Net Partnership Revenue settlement | Joint | 24 wks |
| 3 | Audit rights exercised once for baseline | Joint | 28 wks |

---

*Document prepared by Lux Industries Inc. for SF Private Bank.
Confidential and pre-decisional.
Reference: OG-SP-2026-SFPB (partnership-agreement reference).*
