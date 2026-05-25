# Data Processing Agreement (Template)

Template Data Processing Agreement ("DPA") for B2B counterparties of **Lux Industries Inc.** ("Lux"). This DPA is designed to satisfy GDPR Article 28 (processor obligations), UK GDPR equivalents, and the operational requirements of the CCPA / CPRA service-provider construct. It supplements a primary commercial agreement (master services agreement, commercial license, or order form) between Lux and the counterparty ("Counterparty").

The default role assignment is **Lux as Processor**, **Counterparty as Controller**. Section 1.4 addresses the inverse scenario (Counterparty as Processor) and the joint-control edge case.

This is a **template**. All bracketed placeholders must be filled in for a specific Counterparty. All `TODO[counsel-review]` markers must be resolved by counsel before signature.

---

## 1. Background and Roles

1.1 **Principal Agreement.** This DPA is incorporated into and supplements the `[PRINCIPAL AGREEMENT NAME, e.g., Lux Commercial License Agreement]` dated `[DATE]` between Lux and Counterparty (the "Principal Agreement"). In the event of conflict between this DPA and the Principal Agreement on the subject of personal data processing, this DPA controls.

1.2 **Subject Matter.** The subject matter of processing is the provision of `[SERVICES PROVIDED BY LUX]` to Counterparty under the Principal Agreement.

1.3 **Roles.** Unless otherwise specified in Annex 1, with respect to Personal Data processed under the Principal Agreement:

- **Counterparty acts as Controller** (or, where Counterparty is itself a processor for an upstream controller, as Processor on instructions from that upstream controller).
- **Lux acts as Processor** on behalf of Counterparty.

1.4 **Inverse Scenario.** Where the Principal Agreement involves Counterparty processing Personal Data on Lux's behalf (for example, Counterparty providing services to Lux), the roles in Section 1.3 are reversed and the obligations in Sections 3 through 12 apply mutatis mutandis to Counterparty as Processor.

1.5 **Joint Control.** The parties do not intend to act as joint controllers. If a regulator or court determines a processing activity gives rise to joint control, the parties shall promptly negotiate a transparency arrangement under GDPR Article 26.

TODO[counsel-review]: confirm role assignment is correct for each Principal Agreement variant; some Lux service offerings (e.g., bridged-account custody) may involve Lux acting as Controller, not Processor.

## 2. Definitions

2.1 Terms used in this DPA have the meanings given in GDPR (Regulation (EU) 2016/679) and, where applicable, UK GDPR and the CCPA / CPRA. In particular:

- **"Personal Data"** has the meaning given in GDPR Article 4(1) and includes "personal information" as defined under CCPA / CPRA.
- **"Processing"** has the meaning given in GDPR Article 4(2).
- **"Data Subject"** has the meaning given in GDPR Article 4(1).
- **"Sub-processor"** means any processor engaged by Lux to process Personal Data on Counterparty's behalf under this DPA.
- **"Personal Data Breach"** has the meaning given in GDPR Article 4(12).
- **"Standard Contractual Clauses"** or **"SCCs"** means the standard contractual clauses approved by the European Commission for the transfer of personal data to third countries (Commission Implementing Decision (EU) 2021/914) and, where applicable, the UK International Data Transfer Addendum.

## 3. Scope and Instructions

3.1 **Documented Instructions.** Lux shall process Personal Data only on Counterparty's documented instructions. The Principal Agreement, this DPA, and Annex 1 constitute the parties' initial documented instructions. Additional instructions must be provided in writing (including by email or ticket) and may be subject to additional charges if they materially expand the scope of processing.

3.2 **Subject Matter, Duration, Nature, Purpose, Categories of Data, and Categories of Data Subjects** are set out in **Annex 1**.

3.3 **Lawfulness.** Counterparty represents that it has a valid legal basis under applicable data-protection law for the processing instructed under this DPA, and that all required notices and consents have been provided to and obtained from Data Subjects.

3.4 **Conflict with Law.** Lux shall promptly notify Counterparty if, in Lux's opinion, an instruction violates applicable data-protection law, unless prohibited from doing so by law.

## 4. Confidentiality and Personnel

4.1 Lux shall ensure that personnel authorized to process Personal Data are bound by confidentiality obligations (whether by contract or statutory duty).

4.2 Lux shall limit access to Personal Data to personnel who need access to perform Lux's obligations under the Principal Agreement.

## 5. Security Measures

5.1 Lux shall implement and maintain appropriate technical and organizational measures to protect Personal Data against unauthorized or unlawful processing, accidental loss, destruction, damage, alteration, or disclosure, taking into account the state of the art, costs of implementation, and the nature, scope, context, and purposes of processing as well as the risk to Data Subjects.

5.2 The current security measures are described in **Annex 2**. Lux may update Annex 2 from time to time provided that the level of security is not materially diminished.

TODO[counsel-review]: confirm Annex 2 reflects actual implemented controls; align with SOC 2 / ISO 27001 control mapping if applicable.

## 6. Sub-processors

6.1 **Authorization.** Counterparty grants Lux general written authorization to engage Sub-processors. The current list of Sub-processors is in **Annex 3**.

6.2 **Notice of Changes.** Lux shall notify Counterparty of intended additions or replacements of Sub-processors at least **thirty (30) days** in advance, either by email to the contact listed in Annex 1 or by updating Annex 3 and notifying Counterparty of the update.

6.3 **Objection.** Counterparty may object on reasonable data-protection grounds within fifteen (15) days of notice. The parties shall negotiate in good faith. If no resolution is reached, Counterparty may terminate the affected portion of the Principal Agreement without penalty (other than payment for services rendered before termination).

6.4 **Flow-Down.** Lux shall impose on each Sub-processor data-protection obligations no less protective than those in this DPA, by written contract. Lux remains fully liable to Counterparty for any failure by a Sub-processor to fulfill its obligations.

TODO[counsel-review]: confirm 30-day notice / 15-day objection window aligns with operational reality; some standards require longer (e.g., 60/30).

## 7. Data Subject Rights

7.1 Lux shall, taking into account the nature of the processing, assist Counterparty by appropriate technical and organizational measures, insofar as possible, in fulfilling Counterparty's obligation to respond to requests by Data Subjects to exercise their rights under GDPR Chapter III (access, rectification, erasure, restriction, portability, objection) and equivalent rights under other applicable law.

7.2 If Lux receives a request directly from a Data Subject relating to Personal Data processed on behalf of Counterparty, Lux shall, without undue delay, forward the request to Counterparty and shall not respond to the Data Subject except to confirm receipt and direct the Data Subject to Counterparty (or as otherwise instructed by Counterparty).

## 8. Personal Data Breach Notification

8.1 Lux shall notify Counterparty **without undue delay and in any event within seventy-two (72) hours** after becoming aware of a Personal Data Breach affecting Personal Data processed under this DPA.

8.2 The notification shall, to the extent then known and as it becomes known:

- Describe the nature of the Personal Data Breach, including the categories and approximate number of Data Subjects and Personal Data records concerned.
- Communicate the name and contact details of the Lux point of contact for further information.
- Describe the likely consequences of the Personal Data Breach.
- Describe the measures taken or proposed to address the Personal Data Breach and mitigate its possible adverse effects.

8.3 Lux shall reasonably cooperate with Counterparty in investigating, mitigating, and remediating the Personal Data Breach, and in any notifications to regulators or Data Subjects required by applicable law. The parties acknowledge that statutory notification obligations rest with the Controller.

TODO[counsel-review]: confirm 72-hour window matches GDPR Article 33(1) (controller-to-supervisory-authority deadline); processor-to-controller is "without undue delay" — explicit 72hr is more protective for Counterparty and aligns with common practice.

## 9. Data Protection Impact Assessments

9.1 Lux shall provide reasonable assistance to Counterparty with any data-protection impact assessments and prior consultations with supervisory authorities required under GDPR Articles 35 and 36, in each case solely in relation to processing of Personal Data by Lux and taking into account the nature of the processing and information available to Lux.

## 10. International Transfers

10.1 Where Lux processes Personal Data of Data Subjects in the EEA, UK, or Switzerland in a country that has not received an adequacy decision under GDPR Article 45 (or the UK / Swiss equivalents), the parties shall rely on:

- The **Standard Contractual Clauses (Module Two: Controller-to-Processor)** for transfers from Lux as data exporter to a Sub-processor as data importer; or
- The **Standard Contractual Clauses (Module Two)** between Counterparty as data exporter and Lux as data importer, where Lux is located outside an adequacy country; or
- Another transfer mechanism recognized under applicable law (binding corporate rules, certifications, codes of conduct).

10.2 The parties agree that the SCCs are deemed incorporated into this DPA by reference and completed as set out in **Annex 4** (SCC operational annex).

10.3 Lux shall apply supplementary measures where the transfer assessment indicates they are required (for example, encryption in transit and at rest with keys held in the EEA, pseudonymization, and contractual challenges to government access requests).

TODO[counsel-review]: confirm SCC module selection is correct for each Sub-processor flow; some flows may require Module Three (processor-to-processor). UK Addendum may need to be separately signed.

## 11. Audit Rights

11.1 Lux shall make available to Counterparty all information reasonably necessary to demonstrate compliance with this DPA and with Article 28 GDPR, and shall allow for and contribute to audits, including inspections, conducted by Counterparty or another auditor mandated by Counterparty.

11.2 To minimize disruption, the parties agree that:

- Lux's then-current SOC 2 Type II report, ISO 27001 certificate, or equivalent independent attestation will be made available on request and will satisfy Counterparty's audit rights for matters covered by such report or certificate.
- Where Counterparty reasonably determines that an on-site audit is necessary (e.g., following a Personal Data Breach), Counterparty shall provide at least **thirty (30) days** written notice, conduct the audit during business hours, take reasonable steps to avoid disruption, and pay reasonable costs of Lux's cooperation (unless the audit reveals a material breach by Lux, in which case Lux bears the costs).
- The auditor must execute a confidentiality agreement with Lux and shall not be a direct competitor of Lux.

TODO[counsel-review]: confirm audit-rights construct aligns with regulator expectations for high-risk sectors (financial services, healthcare); some sectors require more direct audit rights than the certificate-substitution model.

## 12. Termination and Return / Deletion

12.1 On termination or expiration of the Principal Agreement, Lux shall, at Counterparty's option:

- Return all Personal Data processed under this DPA to Counterparty in a commonly used machine-readable format; or
- Delete all such Personal Data and certify deletion in writing.

12.2 Counterparty shall exercise the option in Section 12.1 within **thirty (30) days** of termination or expiration. Absent timely instruction, Lux may delete the Personal Data (subject to Section 12.3).

12.3 Lux may retain Personal Data to the extent required by applicable law, in which case Lux shall continue to apply the protections of this DPA to such retained Personal Data for as long as it is retained, and shall limit further processing to what is necessary for the legal-retention purpose.

## 13. Liability and Indemnity

13.1 Each party's liability under this DPA is subject to the liability provisions of the Principal Agreement, except that nothing in this DPA or the Principal Agreement limits a party's liability that cannot be limited under applicable data-protection law (including direct claims by Data Subjects).

TODO[counsel-review]: review interaction with the Principal Agreement liability cap; consider carve-outs for willful misconduct, regulator fines, and Personal Data Breach response costs.

## 14. Miscellaneous

14.1 **Governing Law.** This DPA is governed by the governing law of the Principal Agreement, except where applicable data-protection law mandates otherwise. The SCCs are governed by the law specified in their operational annex.

14.2 **Order of Precedence.** In the event of conflict between this DPA, any Annex, and the SCCs: (a) the SCCs prevail for matters within their scope; (b) this DPA prevails over the Principal Agreement on the subject of Personal Data processing; (c) the Annexes prevail over the body of this DPA for matters they specifically address.

14.3 **Severability.** If any provision is held unenforceable, the remaining provisions remain in full force.

14.4 **Counterparts.** This DPA may be executed in counterparts, including by electronic signature, each of which is an original and which together constitute one agreement.

---

## Signatures

**Counterparty**

Legal name: `[COUNTERPARTY NAME]`
Jurisdiction of formation: `[COUNTERPARTY JURISDICTION]`
Principal address: `[COUNTERPARTY ADDRESS]`
Authorized signatory: `[SIGNATORY NAME]`
Title: `[SIGNATORY TITLE]`
Email: `[SIGNATORY EMAIL]`
Date: `[DATE]`

Signature: __________________________

**Lux Industries Inc.**

Authorized signatory: `[LUX SIGNATORY NAME]`
Title: `[LUX SIGNATORY TITLE]`
Date: `[DATE]`

Signature: __________________________

---

## Annex 1 — Description of Processing

| Item | Detail |
|------|--------|
| Subject matter | `[e.g., provision of Lux validator services]` |
| Duration | Term of the Principal Agreement plus retention period in Section 12 |
| Nature and purpose of processing | `[e.g., hosting, transmission, indexing of Personal Data submitted to the Service]` |
| Types of Personal Data | `[e.g., name, email, IP address, account identifiers]` |
| Special categories of Personal Data (Art. 9 / 10 GDPR) | `[NONE unless explicitly listed]` |
| Categories of Data Subjects | `[e.g., Counterparty's end users, employees]` |
| Frequency of processing | `[continuous / batch / on-demand]` |
| Retention period | As set out in Section 12 and Counterparty's instructions |
| Counterparty data-protection contact | Name: `[NAME]`, Email: `[EMAIL]`, Role: `[ROLE]` |
| Lux data-protection contact | Email: **legal@lux.network**, cc: `[LUX DPO EMAIL IF DESIGNATED]` |

TODO[counsel-review]: confirm "special categories" line is accurate; if any Annex 1 row mentions Art. 9 / 10 data, the Principal Agreement and Annex 2 controls must be reviewed for adequacy.

---

## Annex 2 — Technical and Organizational Measures

Lux maintains, at minimum, the following measures:

1. **Access control.** Role-based access; least-privilege provisioning; multi-factor authentication for personnel access to systems processing Personal Data.
2. **Encryption.** TLS 1.2+ in transit; AES-256 (or equivalent) at rest for storage systems holding Personal Data; key management via the Lux KMS.
3. **Pseudonymization.** Where compatible with processing purposes, identifiers are replaced with opaque tokens.
4. **Resilience.** Documented backup and disaster-recovery procedures; periodic restore testing.
5. **Network security.** Segmentation between production and non-production environments; firewall and intrusion-detection controls.
6. **Personnel security.** Background checks for personnel with access to Personal Data, to the extent permitted by local law; confidentiality obligations; security training on hire and annually.
7. **Logging and monitoring.** Audit logs for access to systems processing Personal Data; centralized log retention and anomaly alerting.
8. **Vulnerability management.** Periodic scanning; patch-management program; coordinated vulnerability disclosure.
9. **Incident response.** Documented incident-response plan; designated incident-response team; tabletop exercises.
10. **Sub-processor management.** Sub-processor due diligence and contractual flow-down as described in Section 6.

TODO[counsel-review]: align Annex 2 with the actual SOC 2 / ISO 27001 control set in force at signature; remove any item not yet implemented; mark "in-progress" items explicitly rather than implying current operation.

---

## Annex 3 — Sub-processors

Current Sub-processors engaged by Lux to process Personal Data on Counterparty's behalf:

| # | Sub-processor | Service provided | Location of processing | Transfer mechanism (if applicable) |
|---|---------------|------------------|------------------------|-------------------------------------|
| 1 | `[SUB-PROCESSOR]` | `[SERVICE]` | `[COUNTRY / REGION]` | `[SCC MODULE / ADEQUACY / N/A]` |
| 2 | `[SUB-PROCESSOR]` | `[SERVICE]` | `[COUNTRY / REGION]` | `[SCC MODULE / ADEQUACY / N/A]` |

Updates to this Annex 3 are governed by Section 6.

TODO[counsel-review]: populate from the actual Lux vendor register; ensure each Sub-processor has a current DPA with Lux flowing down equivalent obligations.

---

## Annex 4 — Standard Contractual Clauses Operational Annex

Where the SCCs apply per Section 10:

- **Module:** `[Module Two: Controller-to-Processor / Module Three: Processor-to-Processor — select per flow]`
- **Docking Clause (Clause 7):** Optional, applies if selected by both parties.
- **Clause 9 — Sub-processor authorization:** Option 2 (general written authorization) — corresponds to Section 6 of this DPA; minimum notice period **thirty (30) days**.
- **Clause 11 — Redress:** Independent dispute-resolution body option **NOT** elected.
- **Clause 17 — Governing law:** Law of `[MEMBER STATE; suggest Ireland for EEA-data flows from Lux]`.
- **Clause 18 — Forum and jurisdiction:** Courts of `[MEMBER STATE matching Clause 17]`.
- **Annex I.A — Parties:** As set out in the signature block of this DPA.
- **Annex I.B — Description of transfer:** As set out in Annex 1 of this DPA.
- **Annex I.C — Competent supervisory authority:** `[per Clause 13 — typically supervisory authority of the EEA Member State where the data exporter is established]`.
- **Annex II — Technical and organizational measures:** As set out in Annex 2 of this DPA.
- **Annex III — Sub-processors:** As set out in Annex 3 of this DPA.
- **UK International Data Transfer Addendum:** Where applicable, the UK Addendum is incorporated by reference and the SCCs are amended as set out in the Addendum's Mandatory Clauses.

TODO[counsel-review]: complete SCC module selection per data flow; confirm competent supervisory authority; review need for Swiss-FADP addendum.

---

## Cross-references

- [PRIVACY-POLICY-TEMPLATE.md](PRIVACY-POLICY-TEMPLATE.md) — consumer-facing privacy policy template (different scope: Lux-as-Controller for end-user data)
- [TERMS-OF-SERVICE-TEMPLATE.md](TERMS-OF-SERVICE-TEMPLATE.md)
- [COMMERCIAL-LICENSE-TEMPLATE.md](COMMERCIAL-LICENSE-TEMPLATE.md) — typical Principal Agreement under Section 1.1

Last reviewed: TODO[counsel-review].
