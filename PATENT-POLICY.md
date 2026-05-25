# Lux Patent Policy

This document describes Lux Industries Inc.'s posture on patents: how Lux acquires them, how it asserts them, and how it grants them to others.

## Strategic Posture

Lux Industries Inc. is a **defensive-primary, offensive-secondary** patent holder.

### Defensive — Primary

The primary purpose of Lux's patent portfolio is to deter patent litigation against Lux and against downstream consumers of Lux technology. Patents are filed and maintained so that:

1. Lux has counterclaim and cross-license leverage against any party that asserts a patent against Lux or against a Lux licensee in respect of Lux technology.
2. Downstream Lux users (open-source contributors, BSD-3 consumers, Eco licensees) inherit deterrence by association: any plaintiff suing them on Lux technology faces the prospect of a Lux counter-assertion.
3. Lux reduces the strategic value of patent acquisition by adversaries who would otherwise hold up the ecosystem.

### Offensive — Secondary

Lux uses its patents offensively only in defined and limited circumstances:

1. **Commercial license enforcement.** Lux asserts its patents against parties who use patented Lux inventions in production for commercial gain without a Lux commercial license. Eco repos publish patented inventions specifically so Lux can detect and address unlicensed commercial use.
2. **Counter-assertion.** Lux asserts patents in response to a patent assertion against Lux or against a Lux licensee.
3. **Trade-secret-equivalent protection.** Lux files patents on inventions that would otherwise be reverse-engineerable, to prevent third parties from claiming them.

Lux does not pursue:

1. Speculative offensive litigation against parties who do not use Lux technology.
2. Litigation against good-faith open-source projects that use Lux technology under permitted-use terms.
3. Patent troll behavior or patent-monetization through third-party assertion entities.

TODO[counsel-review]: confirm posture statement is consistent with Lux's articles of incorporation, board policy, and any IP-related representations made to investors.

## Patent Grants by Tier

### Tier 1 — BSD-3 Repos

BSD-3-Clause's standard patent treatment applies. Lux's patent license to users of BSD-3 repos is implicit in BSD-3's grant structure as construed by courts in the relevant jurisdiction.

TODO[counsel-review]: confirm jurisdiction-specific construction of BSD-3 patent grant; some commentators read BSD-3 as silent on patents and prefer Apache 2.0 for patent clarity. Decide whether Lux should add an explicit PATENTS file alongside BSD-3 LICENSE in patent-relevant Tier 1 repos.

### Tier 2 — Eco Repos

The Lux Eco License does not grant a patent license for production / commercial use. Patent rights to Eco repos are granted only under a Commercial License Agreement (see [COMMERCIAL-LICENSE-TEMPLATE.md](COMMERCIAL-LICENSE-TEMPLATE.md), Section 3).

Permitted non-commercial uses (inspection, research, education, internal evaluation, security audit) carry an implied license sufficient to perform those uses. Lux does not assert patents against good-faith non-commercial use.

### Tier 3 — Closed Repos

Closed repos require a commercial license including the [Private Moat Addendum](COMMERCIAL-LICENSE-PRIVATE-MOAT-ADDENDUM.md). Patent rights to Closed repos are granted only under that addendum.

## Patent Retraction

All Lux commercial licenses include a patent retraction clause. If a licensee initiates a patent infringement action against Lux or against another Lux licensee in respect of the licensed software, Lux's patent license to that licensee terminates as of the filing date.

This protects Lux's licensee community: a licensee cannot use a Lux patent license as a shield while simultaneously asserting patents against other Lux licensees.

TODO[counsel-review]: confirm retraction-clause language across templates is consistent and enforceable in target jurisdictions.

## Defensive Publications

Where Lux determines that an invention should be in the public domain to deter third-party patenting (rather than retained as a Lux patent), Lux may publish a defensive publication. Defensive publications create prior art that prevents third parties from patenting the invention, without committing Lux to the cost of patent prosecution.

## Pledge

Lux pledges that:

1. Lux will not assert any of its patents against any party for use of Tier 1 BSD-3 repos consistent with the BSD-3 license.
2. Lux will not assert any of its patents against good-faith non-commercial use of Tier 2 Eco repos consistent with the Eco license's permitted-use scope.
3. Lux will not assert patents against academic researchers publishing peer-reviewed work that does not constitute production / commercial use.
4. Lux's patent grants under commercial licenses are non-revocable except under the patent retraction clause described above.

TODO[counsel-review]: pledge language carries legal weight; confirm it does not unintentionally bind Lux to non-assertion in contexts Lux wishes to retain (e.g., a competing fork commercializing the technology under a renamed brand).

## Standards Participation

Where Lux participates in industry standards bodies, Lux complies with the patent policy of that body. This typically requires Lux to grant licenses on Fair, Reasonable, and Non-Discriminatory ("FRAND") or Royalty-Free ("RF") terms for Lux patents that are essential to practicing the standard. Lux complies with such commitments in good faith.

TODO[counsel-review]: maintain a separate registry of Lux's standards-body commitments (W3C, IETF, ISO, etc.) so the policy here can reference it.

## Filing Process

Lux's invention-disclosure and filing process is internal. Employees disclose inventions to engineering leadership; engineering leadership reviews with legal; legal evaluates patentability and strategic fit; if filed, Lux retains qualified patent counsel to prepare and prosecute the application.

## Cross-references

- [LICENSING-POLICY.md](LICENSING-POLICY.md)
- [COMMERCIAL-LICENSE-TEMPLATE.md](COMMERCIAL-LICENSE-TEMPLATE.md)
- [COMMERCIAL-LICENSE-PRIVATE-MOAT-ADDENDUM.md](COMMERCIAL-LICENSE-PRIVATE-MOAT-ADDENDUM.md)
- [CONTRIBUTOR-AGREEMENT.md](CONTRIBUTOR-AGREEMENT.md)
- [EMPLOYEE-IP-ASSIGNMENT.md](EMPLOYEE-IP-ASSIGNMENT.md)

Last reviewed: TODO[counsel-review].
