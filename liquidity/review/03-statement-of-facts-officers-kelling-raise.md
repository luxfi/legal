# Memo Review 03 — §IV.D / §IV.E / §IV.F / §IV.G

**File:** `/Users/z/work/lux/legal/liquidity/Lux_IP_Enforcement_Memorandum_2026_05_25.tex`
**Lines reviewed:** 542–716
**Mode:** Read-only

---

## §IV.D — Officer Knowledge (¶¶16–22)

### PASS

- **Sonsurkar (¶19–21):** Correctly framed as long-standing admin on
  `satschel/*` and `liquidityio/*` (the Counterparty's own orgs), with
  the express disclaimer that he did **not** hold admin on `luxfi/*`,
  which is correctly attributed to Lux's own engineering team (Nandy,
  Kelling) upstream. The "software-supply-chain integrity duty
  attaches to imports into the Counterparty's own tree, where his
  admin access was present" formulation is exactly right and matches
  the most-recent correction.
- **Trombley (¶17):** Correctly framed by cross-reference to §II
  (Franklin Templeton litigation history, CSO/Acting CEO posture,
  pre-Kelling ATS state). Investor-representation responsibility is
  carried by the §II framing.
- **Church (¶18):** FINRA-regulated BD CEO framing is accurate and
  scope-appropriate.
- **Nandy (¶21):** Consistently named as the whistleblower / dual-role
  identifier (VPE at Counterparty, concurrently CTO at Lux). No "Woo
  Bin" residue.

### FLAG — Choi framing (¶16)

¶16 currently reads: *"Mr. Eric Choi (CEO) holds ultimate operational
responsibility for technology licensing and IP compliance. His
signature appears (or will appear) on the subscription documents
…; representations therein sound in his name."* That is a strict
liability-of-office framing — it does **not** explicitly carry the
"apparently uninformed" / mitigating-context caveat the user has
directed elsewhere. Compare with ¶22 ("the precise scope of each
officer's knowledge will require diligence development"), which
covers Choi only by reference. **Recommend** a one-sentence add to
¶16 making the "apparently uninformed at this stage; scope of
knowledge subject to diligence" qualifier explicit on Choi
specifically, so §IV.D does not implicitly assert affirmative
knowledge by Choi.

---

## §IV.E — Position of Mr. Kelling (¶¶23–25)

### PASS

- **Departure & current role (¶23):** "**has departed Lux Industries
  Inc.** and is **currently Chief Technology Officer of the
  Counterparty (Liquidity.io)**" — exactly the framing the user
  directed. No concurrent-role implication.
- **Key-person retention as mandatory term (¶25):** Fully present.
  Multi-year retention, good-leaver/bad-leaver triggers, garden-leave,
  equity clawback, carve-outs from any litigation against other
  Counterparty officers — all listed. Cross-refs to §X and §XI are
  there.
- **Litigation-vs-partnership branching (¶24/¶25):** Correctly
  conditional — releases available **only** on full execution +
  ongoing performance of partnership; without partnership, Mr.
  Kelling stands as co-defendant.
- **Equity TODO (¶24):** "Counterparty equity position is to be
  confirmed in diligence" — flag preserved as expected.

### FLAG — CRITICAL CONTENT GAP: AI-assisted development mitigation

The user-directed mitigation context — *"lets make sure it's clear
zach was using AI to develop this and whether intentionally or
unintentionally (as likely given rapid pace of AI development)
should now side with lux team as the clear precedent of lux IP that
needed licensing etc."* — is **NOT PRESENT** anywhere in §IV.E
(¶¶23–25) or in §IV.F. There is no paragraph framing:
  1. that Mr. Kelling used AI-assisted development tooling during
     the Counterparty rebuild;
  2. that any IP-provenance error in attribution may have been
     intentional or unintentional given the pace of AI-assisted
     development;
  3. that, having now been put on notice, he should side with the
     Lux team in establishing the Lux IP precedent / licensing
     posture going forward.

This is the **single largest known pending content add** in this
review band. Recommend a new ¶ between current ¶24 and ¶25 — call
it ¶24A — covering this. It materially softens the §IV.E posture
and is load-bearing for the partnership-tier outcome.

### FLAG — ¶24 Count IX framing

¶24 names Mr. Kelling as a prospective defendant on Count IX (Rule
10b-5) "by virtue of his current CTO role during the active raise."
This is consistent with §IV.G's "current and ongoing duty of
disclosure" framing in ¶16/¶29 — internally coherent. But note: it
sharpens the case for the AI-assisted-development mitigation
paragraph above, because absent that context, Count IX exposure on
Kelling is squarely individual.

---

## §IV.F — Pre-Kelling Technical State (¶¶26–28)

### PASS

- **Time-price priority order matching:** Internally consistent with
  §II framing (per cross-reference at ¶17). The "foundational
  ordering principle … required by SEC Reg ATS" framing is correct.
- **$40K ACH exploit (¶26):** Properly hedged as "on information and
  belief" via the prefacing sentence at ¶26 ("Specifically, on
  information and belief"). Good.
- **¶27 attribution:** "the technology that supports the current
  $75M / $1.1B-valuation raise was the Lux IP that Mr. Kelling
  brought across" — load-bearing for damages (§VI) and credibility
  (Trombley as technology witness). Solid.

### FLAG — ACH exploit evidence

No commit-history corroboration available from
`~/work/liquidity/*` git history at the top-level repo (no commits
found via `git log`; appears to be a meta directory of subprojects).
The §IV.F ¶26 "$40K" figure remains on-information-and-belief only.
**Recommend:** before filing, attempt to locate the contemporaneous
incident/postmortem record (Slack, email, AWS CloudTrail, ACH
processor dispute filings, internal Jira/Linear ticket) and footnote
it. As drafted, the on-info-and-belief framing is defensible but
thin if Counterparty denies the exploit.

---

## §IV.G — Current Raise (¶¶29–30)

### PASS

- **Quantum:** Correctly stated as "**$75 million at a $1.1 billion
  valuation**" — never collapsed to "$1.1B raise." Header reads
  "$75M / $1.1B-Valuation Capital Raise" — clean.
- **Verbal commitments:** "**verbal commitments covering at least
  approximately half of the $75 million round** (i.e. approximately
  $37.5M soft-circled)" — matches user's input wording precisely.
- **"The round has not closed":** Present, bolded, on a line of its
  own. Followed by the funds-not-wired / securities-not-issued /
  duty-of-disclosure-remains-live triad. Strong.
- **Current-and-ongoing duty of disclosure / 10b-5:** ¶30 ties
  directly to Count IX. Securities-fraud framing is present and
  correctly scoped.
- **Forum Markets / formerly Ethzilla:** Correctly identified as
  publicly-traded lead investor continuing from prior round.

### FINDING — Ticker resolved

EDGAR confirms: **Forum Markets Inc — ticker `FRMM`** — CIK
**0001690080**, file number **001-38105**, principal office Palm
Beach, FL, SIC 6199 (Finance Services). Multiple 2026 8-K filings
on the docket (most recent in the search results: 2026-05-14
period; 2026-03-31 press release as EX-99.1). The memo's
`[TICKER --- to be confirmed against SEC EDGAR]` placeholder can
be replaced with **`FRMM`** with high confidence. Recommend the
final filing also drop a footnote with CIK 0001690080 for cite
discipline.

---

## Outstanding TODOs going into final pass

| § | TODO | Severity |
|---|------|----------|
| IV.D ¶16 | Add "apparently uninformed" mitigating caveat on Choi | Medium |
| IV.E ¶24A (new) | **AI-assisted-development mitigation paragraph for Kelling** | **HIGH — known pending content add** |
| IV.E ¶24 | Confirm Counterparty equity position for Kelling in diligence | Medium |
| IV.F ¶26 | Corroborate $40K ACH exploit with contemporaneous record | Low/Medium |
| IV.G ¶29 | Replace `[TICKER TBD]` with `FRMM` (CIK 0001690080) | Low — mechanical |
