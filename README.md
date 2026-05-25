# Lux Industries Inc. — Legal

Canonical home for Lux Industries Inc.'s general-purpose legal templates and policy documents.

## Scope

This directory holds **general-purpose, reusable** legal artifacts:

- Licensing policy and commercial license templates.
- Contributor and employee IP agreements.
- Trademark, patent, brand, and open-source policies.
- Privacy policy and terms of service templates for any Lux-operated service.

It does **not** hold:

- Customer-specific commercial license drafts (those live in customer-specific private trees, scoped to the relationship).
- Per-service SLA contracts (those live with the service operator, not here).
- Executed agreements (those live in the corporate records system, not in source control).

## Important

Every document in this tree carries `TODO[counsel-review]` markers on sections that require legal judgment. These are **starting drafts**, not legally vetted final agreements. Nothing here may be executed, signed, or distributed externally without review by qualified counsel admitted in the relevant jurisdiction.

Lux Industries Inc. employees and contractors using these templates: route every instance through counsel before signature.

## Contents

| File | Purpose |
|------|---------|
| [LICENSING-POLICY.md](LICENSING-POLICY.md) | Internal three-tier IP/licensing strategy and per-repo classification |
| [COMMERCIAL-LICENSE-TEMPLATE.md](COMMERCIAL-LICENSE-TEMPLATE.md) | Generic commercial license template (no specific licensee) |
| [COMMERCIAL-LICENSE-PRIVATE-MOAT-ADDENDUM.md](COMMERCIAL-LICENSE-PRIVATE-MOAT-ADDENDUM.md) | Optional addendum granting access to the private moat |
| [CONTRIBUTOR-AGREEMENT.md](CONTRIBUTOR-AGREEMENT.md) | CLA template for individual outside contributors |
| [CONTRIBUTOR-AGREEMENT-CORPORATE.md](CONTRIBUTOR-AGREEMENT-CORPORATE.md) | Corporate CLA companion binding a company and its designated employees / contractors |
| [EMPLOYEE-IP-ASSIGNMENT.md](EMPLOYEE-IP-ASSIGNMENT.md) | Employee invention and IP assignment template |
| [TRADEMARK-POLICY.md](TRADEMARK-POLICY.md) | Lux trademark usage rules |
| [PATENT-POLICY.md](PATENT-POLICY.md) | Defensive-primary, offensive-secondary patent posture |
| [BRAND-USAGE-GUIDELINES.md](BRAND-USAGE-GUIDELINES.md) | Logo, name, and brand asset usage |
| [OPEN-SOURCE-POLICY.md](OPEN-SOURCE-POLICY.md) | Lux's open-source contribution and acceptance policy |
| [PRIVACY-POLICY-TEMPLATE.md](PRIVACY-POLICY-TEMPLATE.md) | Privacy policy template for Lux-operated services |
| [TERMS-OF-SERVICE-TEMPLATE.md](TERMS-OF-SERVICE-TEMPLATE.md) | Terms of service template for Lux-operated services |
| [DPA-TEMPLATE.md](DPA-TEMPLATE.md) | Data Processing Agreement template (GDPR Art. 28 / CCPA-aware) for B2B counterparties |

## Cross-references

- Public-facing strategy summary: [`luxfi/.github` profile/README.md](https://github.com/luxfi/.github/blob/main/profile/README.md)
- Open-core EE explanation: [`luxfi/.github` profile/OPEN-CORE-EE.md](https://github.com/luxfi/.github/blob/main/profile/OPEN-CORE-EE.md)
- Public docs mirror: [docs.lux.network/licensing](https://docs.lux.network/licensing) and [docs.lux.network/open-core](https://docs.lux.network/open-core)

## Runtime gate vs license tier

Every Lux artifact is licensed. Tiers 1 (BSD-3-Clause) and 2 (Lux Ecosystem License v1.2 / Research-with-Patent-Reservation / Genesis) carry **no runtime token check**; tier 3 (commercial-only, `lux-private/*`) does. The canonical table lives in [LICENSING-POLICY.md → Runtime Gate vs License Tier](LICENSING-POLICY.md#runtime-gate-vs-license-tier) and is mirrored at [docs.lux.network/licensing](https://docs.lux.network/licensing#runtime-gate-vs-license-tier) and [`luxfi/.github` profile/README.md](https://github.com/luxfi/.github/blob/main/profile/README.md#runtime-gate-vs-license-tier).

## Contacts

- Commercial license inquiries: **licensing@lux.network**
- Governance, IP, and corporate questions: **legal@lux.network**

## Maintenance

These templates are revised by Lux Industries Inc. legal and engineering leadership. Material changes require counsel sign-off. Edits that change legal substance must update the `Last reviewed` line at the bottom of each affected file.
