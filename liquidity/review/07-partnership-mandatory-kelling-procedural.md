# Review: §X–§XIII + End-of-Document (lines 1327–1876)

Read-only review of `Lux_IP_Enforcement_Memorandum_2026_05_25.tex`.

---

## §X — Partnership Triangulation

### Math check — PASSES
- M: 50% × $1.1B = $550M equity + $0 cash = **$550M** ✓
- S: 35% × $1.1B = $385M + $165M cash = **$550M** ✓
- R: 25% × $1.1B = $275M + $275M cash = **$550M** ✓
- F: 10% × $1.1B = $110M + $440M cash = **$550M** ✓
- Formula `cash = (50% − equity%) × $1.1B` holds at all tiers.
- Final triangulation table (lines 1439–1442) reproduces the same numbers correctly.

### Governance escalation — COHERENT
Observer → 1 seat → 2 seats → parity reads cleanly across F→R→S→M. Reciprocal columns also stack monotonically (each tier inherits the prior tier's commitments + adds).

### Pricing comp argument — SOUND
Anchoring on the live $1.1B round (Forum Markets lead, ~$37.5M soft-circled) as the "clean precedent transaction" is the right move — no separate valuation, no contested damages multiplier. Defensible.

### Cash-sequencing paragraph — COHERENT
Multi-year schedule (30% at close, 24–36 mo balance, security interest in pledged equity or default-to-equity conversion) is the right structural fix and correctly nudges the landing zone toward higher-equity tiers (which is what Lux wants).

### Feature-Unlock table — INCONSISTENCY (flag)
The Feature-Unlock table (lines 1404–1429) uses **S– / S / M / B / A+** column headers — these are the **old litigation-settlement tier labels** (Small / Medium / Big / A+), not the new partnership tier labels (F / R / S / M). This is a residual from the prior draft and reads as misaligned with §X's new partnership-tier framing. Worth a relabel pass.

### "Cash vs. Equity Trade-Off (within Recommended tier)" sub-table — MISSING
The review prompt references this sub-table; it is **not present** in §X. The cash/equity inverse relationship is explained narratively and in the main tier table, but no Recommended-tier-specific trade-off sub-table exists. Either add it or remove the reference from the scope.

---

## §XI — Mandatory Terms

### ¶0 Key-person retention (Kelling) — PRESENT and complete
4-year term ✓, good-/bad-leaver ✓, 12-mo garden-leave ✓, mutual releases of Counts I/II/III/IV/VI/VII/IX/XI/XII ✓, carve-out from suits vs. other officers ✓, comp benchmarked to CTO market ✓, bad-leaver clawback ✓.

### GAP — Whistleblower / non-retaliation protection for Mr. Nandy
**MISSING.** Per user direction (MAX legal protections for Lux team including Nandy as discovery-and-escalation figure), there should be a dedicated ¶ codifying: non-retaliation by Counterparty, indemnification by Lux, whistleblower protection (SOX §806 / Dodd-Frank §922 framing), continued employment protection, fee-shifting if retaliation occurs. **ADD as ¶17 or insert after ¶0.**

### GAP — Lux engineering team non-solicit / non-retaliation
**MISSING.** No ¶ binds the Counterparty against soliciting Lux engineers or retaliating against any Lux personnel who participate in the investigation / discovery. **ADD.**

### GAP — D&O indemnification of Lux board/officers for raising this matter
**MISSING.** Pahlavi, Dupont, Donohue, Nandy are personally exposed in raising and prosecuting these claims. The SCLA should require Counterparty to acknowledge no claims against Lux officers for the act of raising IP enforcement, plus Lux's own corporate indemnification + D&O tail confirmation. **ADD.**

### OnyxPlus directionality (¶11) — CORRECT
Reads "from Counterparty to Lux, not the other direction" — directionality fixed per recent user instruction. ✓

### Other ¶s (1–16) — COHERENT
Board composition (7 directors, 3+1+3, with 2+2+3 alternative) reads cleanly; the DGCL §144 disinterested-quorum rationale is well-placed. Anti-dilution, pro-rata, tag/co-sale, info rights, patent grant, reciprocal ATS/BD/TA, co-branding, AvaTrade, 8 bps, Warp activation, litigation hold, investigation cooperation — all consistent with §X reciprocal columns.

### Schedule E summary (line 1837–1860) — DRIFT
Schedule E enumerates 16 items but **omits ¶0 (Kelling key-person retention)** — it starts at the old "1 Lux + 1 independent" and never references the new ¶0. If ¶0 is mandatory, Schedule E should mirror it (renumber 0–16 or add as item 17). Currently the summary contradicts the body.

---

## §XII — Special Note Re Mr. Kelling

### Mr. Kelling not named in litigation — PARTIALLY ALIGNED
Line 1654 ("should not be named as a defendant") is correct. But the broader framing still treats Kelling as a **witness whose cooperation we manage** rather than as the **incumbent Counterparty CTO whose retention is the partnership keystone**. The §XI ¶0 framing is not echoed back here.

### "Currently Counterparty CTO only (left Lux)" — NOT REFLECTED
§XII still describes Mr. Kelling's "founder status at both entities" (line 1675) and "absence of financial interest in the Counterparty" (line 1676) — these are ambiguous on his current status and arguably stale. Should be tightened: he is **currently Counterparty CTO**, having departed Lux operational role, which is exactly why §XI ¶0 anchors on retaining him.

### Cross-reference to §XI ¶0 — MISSING
§XII does not point at §XI ¶0 (key-person retention) as the operative protective mechanism. Should add a closing line: *"See §XI ¶0 for the operative key-person retention term that codifies Mr. Kelling's continuing CTO role and the associated mutual releases."*

### GAP — AI-assisted-development mitigating context
**MISSING.** Per user direction: §XII should make clear that Mr. Kelling was using AI tools to develop the Counterparty platform, and that — whether intentionally or (more likely, given the rapid pace of AI tool evolution 2023–2026) unintentionally — the AI-assisted workflow now cuts in Lux's favour, because the AI tooling consistently surfaced and re-used Lux's prior-art IP as the clear precedent that needed licensing. This frames Mr. Kelling as a sympathetic figure (good-faith use of state-of-the-art tooling) while still establishing Lux's IP as the clean precedent that the AI workflow itself identified. **ADD as a dedicated paragraph in §XII.**

---

## §XIII — Procedural Recommendations

### Pahlavi (President & CEO) — final approval framing — PRESENT ✓
### Dupont (deal lead) — negotiation-lead framing — PRESENT ✓
Title reads "Managing Partner, Strategic Transactions; largest investor" — confirm this is the preferred descriptor; "deal lead" is in the parenthetical and accurate.

### GAP — Recommended approach for approaching Liquidity
**MISSING.** §XIII jumps straight from decision-chain to outside-engagement to a 75-day milestone schedule. Per user direction, there should be an explicit recommended-approach block covering:

1. **Partnership-first posture** — open with the partnership offer (Recommended tier), not litigation threat.
2. **Quiet investigation in parallel** — Kroll/FTI document review proceeds out of view while negotiation opens.
3. **Triangulate to Recommended (R, 25% + $275M)** — present F/R/S/M as the menu; anchor on R as the deal team's pre-cleared zone.
4. **Multi-year cash schedule** — offered as the structural accommodation that lets Counterparty land at R or S without single-payment cash shock.
5. **Mutual releases + key-person retention** — surfaced early as the trust-building move (Kelling stays, Counterparty officers released conditional on SCLA execution).
6. **Reciprocal commitments framed as symmetric, not punitive** — ATS/BD/TA license back to Lux is the consideration that makes the deal feel mutual, not extractive.
7. **Escalation ladder** — if Counterparty rejects R, escalate to S; if rejects S, formal litigation hold notice + filing prep.

**ADD as §XIII.B "Recommended Approach to Counterparty" before the milestone schedule.**

### 75-day milestone schedule — COHERENT
Day-0 → Day-75 reads cleanly and aligns the litigation hold (Day 7) before term sheet (Day 21) — correct sequencing.

---

## End-of-document

### Closing block — PRESENT and clean
Lines 1862–1876: hrule + italicized confidentiality footer naming Pahlavi/Dupont/Donohue/Nandy + outside counsel + Pahlavi/Donohue authorization for distribution + `\end{document}`. ✓

### Schedules A–E — PRESENT
A (IP inventory), B (pipeline), C (banking license cost-to-replicate), D (Hanzo portfolio comparables), E (mandatory-terms summary — see DRIFT note above).

---

## Summary of action items (in priority order)

1. **§XI** — ADD ¶ for Nandy whistleblower/non-retaliation protection.
2. **§XI** — ADD ¶ for broader Lux engineering team non-solicit / non-retaliation.
3. **§XI** — ADD ¶ for D&O indemnification of Lux board/officers.
4. **§XII** — ADD AI-assisted-development mitigating-context paragraph.
5. **§XII** — ADD cross-reference to §XI ¶0; tighten "current Counterparty CTO only" framing.
6. **§XIII** — ADD §XIII.B "Recommended Approach to Counterparty" (partnership-first / quiet investigation / triangulate-to-R / multi-year cash / mutual releases / reciprocal symmetric / escalation ladder).
7. **Schedule E** — Renumber to include ¶0 key-person retention (currently drifts from §XI body).
8. **§X Feature-Unlock table** — Relabel S–/S/M/B/A+ headers to F/R/S/M to align with new partnership-tier framing.
9. **§X** — Either add the missing "Cash vs. Equity Trade-Off (within Recommended tier)" sub-table or remove it from intended scope.

File: `/Users/z/work/lux/legal/liquidity/Lux_IP_Enforcement_Memorandum_2026_05_25.tex`
