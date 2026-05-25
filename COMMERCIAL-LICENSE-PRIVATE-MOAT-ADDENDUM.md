# Commercial License — Private Moat Addendum (Template)

This Addendum extends a Commercial License Agreement (the "Base Agreement") between **Lux Industries Inc.** ("Licensor") and `[LICENSEE NAME]` ("Licensee") to grant Licensee access to and entitlements in respect of certain non-public Licensor repositories (the "Private Moat").

This is a **generic template**. All bracketed placeholders must be filled in for a specific transaction. All `TODO[counsel-review]` markers must be resolved by counsel before execution.

---

## 1. Effective Date and Relationship to Base Agreement

1.1 This Addendum is effective as of `[ADDENDUM EFFECTIVE DATE]` and is incorporated into the Base Agreement.

1.2 Capitalized terms not defined here have the meanings given in the Base Agreement.

1.3 In the event of conflict between this Addendum and the Base Agreement, this Addendum controls with respect to the Private Moat.

## 2. Private Moat Definition

2.1 **"Private Moat"** means the Licensor repositories listed in **Schedule PM-A**, in each case as made available by Licensor through the Distribution Channel defined in Section 4.

2.2 The Private Moat as of the date of this Addendum includes, by way of example, repositories under `github.com/lux-private/*` such as:

- `lux-private/gpu-kernels` — GPU acceleration kernels.
- `lux-private/dex` — DEX matching engine.
- `lux-private/fpga` — FPGA designs.

The authoritative list for this Addendum is **Schedule PM-A**.

## 3. Grant

3.1 Subject to Licensee's compliance with the Base Agreement and this Addendum, and timely payment of all fees including the Private Moat fees in **Schedule PM-C**, Licensor grants Licensee a non-exclusive, non-transferable, non-sublicensable, worldwide license, during the Term, to:

  (a) access and download the Private Moat solely through the Distribution Channel;
  (b) use, reproduce, and modify the Private Moat for the Permitted Use defined in the Base Agreement;
  (c) deploy and operate the Private Moat (including modifications) for the Permitted Use, including Production Use, solely on infrastructure controlled by Licensee or its Affiliates; and
  (d) integrate the Private Moat with the Licensed Software for the Permitted Use.

3.2 The license in Section 3.1 does **not** include any right to:

  (a) sublicense, distribute, publish, or disclose the Private Moat to any third party;
  (b) make the Private Moat available as a service to any third party except as part of Licensee's own products provided to its end users;
  (c) reverse-engineer the Private Moat for the purpose of building a competing product;
  (d) use the Private Moat after expiration or revocation of the License Token defined in Section 5; or
  (e) remove, alter, or obscure any proprietary notices.

## 4. Distribution Channel

4.1 Licensor shall make the Private Moat available to Licensee through the GitHub container registry under `ghcr.io/lux-private/*` (the "Distribution Channel"), accessed using a licensee-specific pull credential issued by Licensor.

4.2 Licensor may, at its option, also make Private Moat source code available through licensee-specific access grants on `github.com/lux-private/*`, governed by the same terms.

4.3 Licensee shall (a) treat the licensee-specific pull credentials as Confidential Information under Section 11 of the Base Agreement, (b) restrict access to authorized personnel with a need to know, and (c) notify Licensor immediately on discovery of any compromise.

4.4 Licensor may rotate, revoke, or replace pull credentials at any time on reasonable notice to Licensee. Licensor shall not unreasonably interfere with Licensee's ongoing Permitted Use through such rotations.

TODO[counsel-review]: confirm credential-rotation provisions do not amount to unilateral termination right; consider explicit minimum-notice-period for credential revocation absent breach.

## 5. License Token

5.1 On execution of this Addendum and on each renewal, Licensor shall issue Licensee a **License Token** in the form of a JSON Web Token (JWT) signed by Licensor's `luxfi/license` issuing key.

5.2 The License Token's claims include, at minimum:

  - `iss`: `licensing.lux.network`.
  - `sub`: Licensee's organization identifier.
  - `aud`: a list of Private Moat repository identifiers Licensee is entitled to use.
  - `iat`, `nbf`, `exp`: standard time claims, with `exp` set to the end of the then-current paid period.
  - `lux:tier`: the support tier described in Section 6.
  - `lux:scale`: any deployment-scale limits applicable to the Permitted Use.

5.3 Private Moat artifacts may verify the License Token at runtime. Licensee shall not tamper with, forge, or attempt to extend the validity of any License Token.

5.4 On termination or expiration of this Addendum or the Base Agreement, the License Token shall be deemed revoked. Licensee shall cease all use of the Private Moat and certify deletion under Section 9.4 of the Base Agreement.

TODO[counsel-review]: confirm enforceability of token-expiry stop-use provisions in the governing jurisdiction; confirm runtime token verification does not create privacy-law exposure (e.g., no telemetry leaks PII).

## 6. Support Tier

6.1 Licensor shall provide Licensee with the support tier specified in **Schedule PM-B**.

6.2 Standard support tiers (one to be selected in **Schedule PM-B**):

  - **Bronze.** Best-effort response within five business days. No SLA on resolution.
  - **Silver.** Response within two business days. Best-effort SLA on resolution. Quarterly review.
  - **Gold.** Response within one business day. Targeted resolution SLA. Monthly review and a named technical contact.
  - **Platinum.** 24-hour critical-issue response, named technical contact, quarterly roadmap review with engineering leadership, and access to pre-release builds.

6.3 Support is provided in English. Support hours are stated in **Schedule PM-B**.

TODO[counsel-review]: confirm support-tier definitions are not inadvertently warranted as outcomes; tiers describe response targets, not result guarantees.

## 7. Audit and Telemetry

7.1 The audit rights in Section 10 of the Base Agreement extend to Licensee's use of the Private Moat.

7.2 Licensee acknowledges that Private Moat artifacts may emit signed, anonymized telemetry sufficient to verify (a) License Token validity and (b) deployment scale within the limits in **Schedule PM-A**. Telemetry shall not include personal data of Licensee's end users or any Confidential Information of Licensee, and shall be limited to what is necessary for license enforcement.

TODO[counsel-review]: confirm telemetry minimization aligns with privacy law in Licensee's jurisdiction; consider explicit data-categories list in Schedule.

## 8. Termination

8.1 In addition to the termination rights in Section 9 of the Base Agreement, Licensor may terminate this Addendum (without affecting the Base Agreement's continuation as to non-Private-Moat use) on written notice if Licensee:

  (a) discloses the Private Moat or any pull credentials in violation of this Addendum;
  (b) tampers with or forges any License Token; or
  (c) fails to pay Private Moat fees and does not cure within 10 days of written notice.

8.2 On termination of this Addendum:

  (a) Licensor may revoke pull credentials and License Tokens immediately;
  (b) Licensee shall cease use of the Private Moat, delete all copies, and certify deletion within 30 days; and
  (c) any provisions that by their nature survive termination of the Base Agreement also survive as to the Private Moat.

## 9. Fees

9.1 Licensee shall pay Licensor the Private Moat fees set out in **Schedule PM-C**, in addition to fees due under the Base Agreement.

---

## Signatures

**Lux Industries Inc.**

By: __________________________
Name: `[NAME]`
Title: `[TITLE]`
Date: `[DATE]`

**[LICENSEE NAME]**

By: __________________________
Name: `[NAME]`
Title: `[TITLE]`
Date: `[DATE]`

---

## Schedule PM-A — Private Moat Repositories and Scale Limits

| Repository | Scope of Permitted Use | Scale Limits |
|------------|------------------------|--------------|
| `lux-private/[REPO]` | `[DESCRIBE]` | `[LIMITS]` |

## Schedule PM-B — Support Tier

Tier: `[BRONZE / SILVER / GOLD / PLATINUM]`
Hours: `[SUPPORT HOURS]`
Named technical contact (Gold/Platinum): `[NAME / EMAIL]`

## Schedule PM-C — Private Moat Fees

`[FEE TBD]`

---

## Cross-references

- [COMMERCIAL-LICENSE-TEMPLATE.md](COMMERCIAL-LICENSE-TEMPLATE.md) (Base Agreement)
- [LICENSING-POLICY.md](LICENSING-POLICY.md) (three-tier strategy)
- [PATENT-POLICY.md](PATENT-POLICY.md)

Last reviewed: TODO[counsel-review].
