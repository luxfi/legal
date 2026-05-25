# Commercial License Agreement (Template)

This is a **generic template**. All bracketed placeholders must be filled in for a specific transaction. All `TODO[counsel-review]` markers must be resolved by counsel before execution.

---

**THIS COMMERCIAL LICENSE AGREEMENT** (the "Agreement") is entered into as of `[EFFECTIVE DATE]` (the "Effective Date") by and between:

- **Lux Industries Inc.**, a corporation organized under the laws of `[LUX JURISDICTION OF INCORPORATION]`, with its principal place of business at `[LUX ADDRESS]` ("Licensor"); and
- **[LICENSEE NAME]**, a `[LICENSEE ENTITY TYPE]` organized under the laws of `[LICENSEE JURISDICTION]`, with its principal place of business at `[LICENSEE ADDRESS]` ("Licensee").

Licensor and Licensee may each be referred to as a "Party" and collectively as the "Parties".

## 1. Definitions

1.1 **"Licensed Software"** means the source code, object code, and documentation of the software repositories listed in **Schedule A**, in each case as published by Licensor under the Lux Eco License or made available to Licensee under this Agreement.

1.2 **"Permitted Use"** means use of the Licensed Software by Licensee and its Affiliates for the purposes set out in **Schedule B**, subject to the limits and exclusions in this Agreement.

1.3 **"Affiliate"** means, with respect to a Party, any entity that controls, is controlled by, or is under common control with that Party, where "control" means ownership of more than 50% of the voting equity or the power to direct the management of the entity.

1.4 **"Production Use"** means use of the Licensed Software to provide services to third parties for revenue, or as part of a commercial product offering.

1.5 **"Patent Rights"** means all patents and patent applications owned or controlled by Licensor as of the Effective Date and during the Term that read on the Licensed Software as published by Licensor.

1.6 **"Confidential Information"** means non-public information disclosed by one Party to the other that is marked confidential or that a reasonable person would understand to be confidential under the circumstances. Source code in public Licensor repositories is not Confidential Information; source code in private Licensor repositories is.

1.7 **"Term"** has the meaning given in Section 9.

## 2. Grant of License

2.1 Subject to Licensee's compliance with this Agreement and timely payment of all fees, Licensor grants Licensee a non-exclusive, non-transferable, non-sublicensable, worldwide license, during the Term, to:

  (a) use, reproduce, and modify the Licensed Software for the Permitted Use;
  (b) deploy and operate the Licensed Software (including modifications) for the Permitted Use, including Production Use; and
  (c) distribute the Licensed Software internally within Licensee and its Affiliates for the Permitted Use.

2.2 The license in Section 2.1 does **not** include any right to:

  (a) sublicense the Licensed Software to any third party;
  (b) distribute the Licensed Software (including modifications) to any third party outside Licensee and its Affiliates;
  (c) use any Licensor trademark, service mark, or trade name except as expressly permitted by [TRADEMARK-POLICY.md](TRADEMARK-POLICY.md);
  (d) remove, alter, or obscure any proprietary notices in the Licensed Software; or
  (e) use the Licensed Software in violation of applicable law.

2.3 **Private Moat Exclusion.** This Agreement does **not** grant Licensee any rights to Licensor's private repositories. Access to private repositories is granted only under a separate written addendum executed by both Parties (see [COMMERCIAL-LICENSE-PRIVATE-MOAT-ADDENDUM.md](COMMERCIAL-LICENSE-PRIVATE-MOAT-ADDENDUM.md)).

## 3. Patent Grant

3.1 Subject to the Term and Licensee's compliance with this Agreement, Licensor grants Licensee a non-exclusive, non-transferable, non-sublicensable, worldwide license under the Patent Rights to make, use, sell, offer for sale, and import the Licensed Software solely as necessary for the Permitted Use.

3.2 **Patent Retraction.** If Licensee or any Affiliate initiates or voluntarily participates in a patent infringement action or counterclaim against Licensor or any other licensee of the Licensed Software alleging that the Licensed Software infringes a patent owned or controlled by Licensee or its Affiliates, the patent license granted in Section 3.1 terminates automatically as of the date of filing.

TODO[counsel-review]: confirm patent retraction scope (initiator-only vs. all participating parties; defensive carve-outs; cross-claim treatment).

## 4. Fees

4.1 Licensee shall pay Licensor the fees set out in **Schedule C**.

4.2 All fees are exclusive of taxes. Licensee is responsible for all sales, use, value-added, withholding, and similar taxes, excluding taxes on Licensor's net income.

4.3 Fees are non-refundable except as expressly provided in Section 9.

4.4 Late payments accrue interest at the lesser of `[INTEREST RATE TBD]` per annum or the maximum rate permitted by law.

TODO[counsel-review]: confirm interest rate consistent with usury law in governing jurisdiction; consider step-up termination right for prolonged non-payment.

## 5. Intellectual Property

5.1 As between the Parties, Licensor retains all right, title, and interest in and to the Licensed Software, including all modifications, enhancements, and derivative works created by Licensor.

5.2 Modifications created by Licensee solely for its internal Permitted Use are owned by Licensee, subject to Licensor's underlying ownership of the Licensed Software. Licensee grants Licensor a non-exclusive, royalty-free, perpetual, irrevocable, worldwide license to use, reproduce, modify, and distribute any modifications that Licensee voluntarily contributes to a public Licensor repository.

5.3 Feedback (suggestions, ideas, improvements) provided by Licensee to Licensor regarding the Licensed Software may be used by Licensor without restriction or compensation.

TODO[counsel-review]: confirm modification-ownership treatment; consider whether grant-back should be broader (e.g., all modifications, not just contributed ones).

## 6. Warranties and Disclaimers

6.1 **Mutual Warranties.** Each Party represents and warrants that it has the corporate authority to enter into this Agreement and that doing so does not violate any other agreement to which it is a party.

6.2 **Licensor Warranty.** Licensor represents and warrants that, to its knowledge as of the Effective Date, the Licensed Software does not infringe any third-party intellectual property right. This warranty does not apply to (a) modifications made by anyone other than Licensor, (b) combinations of the Licensed Software with other software not provided by Licensor, or (c) use of the Licensed Software outside the Permitted Use.

6.3 **DISCLAIMER.** EXCEPT FOR THE EXPRESS WARRANTIES IN THIS SECTION 6, THE LICENSED SOFTWARE IS PROVIDED "AS IS" AND LICENSOR DISCLAIMS ALL OTHER WARRANTIES, EXPRESS OR IMPLIED, INCLUDING WITHOUT LIMITATION THE IMPLIED WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE, AND NON-INFRINGEMENT. LICENSOR DOES NOT WARRANT THAT THE LICENSED SOFTWARE WILL BE ERROR-FREE OR UNINTERRUPTED.

TODO[counsel-review]: confirm disclaimer scope per governing law; some jurisdictions require additional formalities for valid disclaimer.

## 7. Indemnification

7.1 **Licensor Indemnity.** Licensor shall defend, indemnify, and hold harmless Licensee from and against any third-party claim alleging that the Licensed Software (as provided by Licensor and used within the Permitted Use) infringes a patent, copyright, or trade secret of the claimant, and shall pay any damages finally awarded by a court of competent jurisdiction or agreed in settlement, provided that Licensee (a) promptly notifies Licensor of the claim, (b) gives Licensor sole control of the defense and settlement, and (c) provides reasonable cooperation at Licensor's expense.

7.2 **Licensor Indemnity Exclusions.** Licensor has no obligation under Section 7.1 for any claim arising from (a) use of the Licensed Software outside the Permitted Use, (b) modifications not made by Licensor, (c) combination of the Licensed Software with other software not provided by Licensor, or (d) Licensee's failure to use a non-infringing update or replacement made available by Licensor.

7.3 **Licensee Indemnity.** Licensee shall defend, indemnify, and hold harmless Licensor from and against any third-party claim arising from Licensee's use of the Licensed Software outside the Permitted Use, breach of this Agreement, or violation of applicable law.

7.4 **Sole Remedy.** The remedies in this Section 7 are each Party's sole and exclusive remedy for third-party intellectual-property claims related to the Licensed Software.

TODO[counsel-review]: confirm indemnity caps and carve-outs align with Section 8 limitations; consider mutual cap on indemnity exposure.

## 8. Limitation of Liability

8.1 **Cap.** EXCEPT FOR (A) BREACHES OF SECTION 11 (CONFIDENTIALITY), (B) INDEMNITY OBLIGATIONS UNDER SECTION 7, (C) PAYMENT OBLIGATIONS UNDER SECTION 4, AND (D) GROSS NEGLIGENCE OR WILLFUL MISCONDUCT, EACH PARTY'S AGGREGATE LIABILITY UNDER THIS AGREEMENT IS LIMITED TO THE FEES PAID OR PAYABLE BY LICENSEE UNDER THIS AGREEMENT IN THE 12 MONTHS PRECEDING THE EVENT GIVING RISE TO LIABILITY.

8.2 **Excluded Damages.** EXCEPT FOR THE CARVE-OUTS IN SECTION 8.1, NEITHER PARTY IS LIABLE FOR INDIRECT, INCIDENTAL, SPECIAL, CONSEQUENTIAL, OR PUNITIVE DAMAGES, OR FOR LOST PROFITS, LOST REVENUE, OR LOST DATA, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGES.

TODO[counsel-review]: confirm cap formula; some licensees push for a multi-year or multi-fees cap, some for a flat-dollar cap. Confirm carve-outs are appropriate given total contract value.

## 9. Term and Termination

9.1 **Term.** This Agreement begins on the Effective Date and continues for `[INITIAL TERM TBD]`, then renews automatically for successive `[RENEWAL TERM TBD]` periods unless either Party provides written notice of non-renewal at least `[NOTICE PERIOD TBD]` before the end of the then-current term.

9.2 **Termination for Cause.** Either Party may terminate this Agreement on written notice if the other Party materially breaches the Agreement and fails to cure within 30 days of written notice of the breach (10 days for non-payment).

9.3 **Termination for Insolvency.** Either Party may terminate this Agreement immediately on written notice if the other Party becomes insolvent, makes a general assignment for the benefit of creditors, or has a receiver appointed.

9.4 **Effect of Termination.** On termination or expiration:

  (a) all licenses granted to Licensee terminate immediately;
  (b) Licensee shall cease all use of the Licensed Software, delete all copies in its possession, and certify deletion in writing within 30 days;
  (c) accrued payment obligations survive termination; and
  (d) Sections 5, 6.3, 7, 8, 10, 11, and 12 survive termination.

TODO[counsel-review]: confirm transition / wind-down period if Licensee operates production infrastructure that depends on the Licensed Software; consider escrow or extended wind-down for material deployments.

## 10. Audit

10.1 During the Term and for one year after termination, Licensor may, on at least 30 days' written notice and no more than once per 12-month period, audit Licensee's use of the Licensed Software to verify compliance with this Agreement.

10.2 Audits shall be conducted during normal business hours, by an independent auditor selected by Licensor and reasonably acceptable to Licensee, and shall not unreasonably interfere with Licensee's operations.

10.3 If an audit reveals underpayment of more than 5% of fees due, Licensee shall reimburse Licensor for the reasonable costs of the audit in addition to paying the underpaid amount with interest under Section 4.4.

TODO[counsel-review]: confirm audit scope and dispute mechanism; some licensees require auditor NDAs and limit access to specific systems.

## 11. Confidentiality

11.1 Each Party shall protect the other Party's Confidential Information using at least the same degree of care it uses for its own confidential information of like importance, and in no event less than a reasonable degree of care.

11.2 Confidential Information may be used solely to perform under this Agreement and disclosed only to employees, contractors, and advisors with a need to know who are bound by confidentiality obligations at least as protective as those in this Agreement.

11.3 Confidentiality obligations under this Section 11 survive termination of this Agreement for `[CONFIDENTIALITY TAIL TBD]`.

11.4 Confidentiality obligations do not apply to information that (a) was known to the receiving Party before disclosure, (b) becomes publicly available through no fault of the receiving Party, (c) is independently developed by the receiving Party without reference to the disclosing Party's Confidential Information, or (d) is rightfully received from a third party without confidentiality obligations.

11.5 Disclosure compelled by law or court order is permitted, provided the receiving Party gives prompt notice to the disclosing Party (where legally permitted) and reasonable cooperation in seeking a protective order.

## 12. General

12.1 **Governing Law.** This Agreement is governed by the laws of `[GOVERNING LAW JURISDICTION; suggest Delaware]`, without regard to conflict of laws principles. The UN Convention on Contracts for the International Sale of Goods does not apply.

TODO[counsel-review]: confirm governing law fits both Parties' jurisdictions; consider New York for finance counterparties, England & Wales for UK counterparties, Singapore for Asia-Pacific counterparties.

12.2 **Dispute Resolution.** Any dispute arising out of or relating to this Agreement shall be resolved by `[DISPUTE FORUM TBD; suggest binding arbitration under JAMS or AAA Commercial Rules in DELAWARE]`. The prevailing Party is entitled to recover reasonable attorneys' fees and costs.

TODO[counsel-review]: confirm arbitration vs. court litigation; consider class-action waiver; confirm seat / venue.

12.3 **Assignment.** Neither Party may assign this Agreement without the other Party's prior written consent, except that either Party may assign without consent to a successor in connection with a merger, acquisition, or sale of substantially all assets, provided the assignee assumes all obligations under this Agreement.

12.4 **Notices.** Notices under this Agreement shall be in writing and delivered by courier, certified mail, or email with confirmation of receipt to the addresses set out in **Schedule D**.

12.5 **Entire Agreement.** This Agreement (including its Schedules and any executed addenda) is the entire agreement between the Parties regarding its subject matter and supersedes all prior or contemporaneous agreements.

12.6 **Amendment.** This Agreement may be amended only by a written instrument signed by both Parties.

12.7 **Severability.** If any provision of this Agreement is held unenforceable, the remaining provisions remain in full force.

12.8 **No Waiver.** Failure by either Party to enforce any provision is not a waiver of future enforcement.

12.9 **Force Majeure.** Neither Party is liable for delay or failure caused by events beyond its reasonable control.

12.10 **Independent Contractors.** The Parties are independent contractors. Nothing in this Agreement creates a partnership, joint venture, agency, or employment relationship.

12.11 **Counterparts.** This Agreement may be executed in counterparts, including by electronic signature, each of which is an original and all of which together constitute one agreement.

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

## Schedule A — Licensed Software

`[LIST OF LICENSOR REPOSITORIES, e.g., github.com/luxfi/node, github.com/luxfi/consensus, github.com/luxfi/crypto]`

## Schedule B — Permitted Use

`[DESCRIPTION OF PERMITTED USE: industry, geography, deployment scale, named services or products]`

## Schedule C — Fees

`[FEE STRUCTURE: e.g., annual subscription, per-deployment, per-validator, revenue share. Use placeholder amounts ([FEE TBD]) until commercial terms are finalized.]`

## Schedule D — Notices

Licensor:
- Address: `[LUX NOTICE ADDRESS]`
- Email: `legal@lux.network`

Licensee:
- Address: `[LICENSEE NOTICE ADDRESS]`
- Email: `[LICENSEE NOTICE EMAIL]`

---

## Cross-references

- [LICENSING-POLICY.md](LICENSING-POLICY.md)
- [COMMERCIAL-LICENSE-PRIVATE-MOAT-ADDENDUM.md](COMMERCIAL-LICENSE-PRIVATE-MOAT-ADDENDUM.md)
- [PATENT-POLICY.md](PATENT-POLICY.md)
- [TRADEMARK-POLICY.md](TRADEMARK-POLICY.md)

Last reviewed: TODO[counsel-review].
