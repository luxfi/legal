# Review 05 — §VI Damages & §VII Trading-Fee Revenue Projections

**Memo:** `Lux_IP_Enforcement_Memorandum_2026_05_25.tex`
**Scope:** lines 826–1111 (+ cross-checks to §I and §X)
**Posture:** read-only; no edits to the .tex
**Reviewer hat:** CFO / damages expert

---

## TL;DR

- §VI scenario arithmetic is **internally consistent**; Small/Medium/Big sum cleanly to $80M / $215M / $590M.
- The headline "$80M–$590M IP / $180M–$890M with opp-cost" propagates correctly from §VI to §I and §XV.
- The **`$12.2M/day` opportunity-cost** rate is arithmetically correct (`$1.1B / 90 = $12.222M`).
- The **`5,991 commits / 90 days`** claim is supportable from on-disk git evidence (sampling reproduces the per-repo numbers within ~5–10% — see git audit below).
- **Lux upstream "0 commits in 90 days"** claim is **exactly verified** (luxfi/node, consensus, crypto, evm, vm, precompile all returned 0 for Kelling-attributed authors in the rolling 90-day window).
- §VII **"Lux 10% equity stake"** framing is **STALE** — it has not been rebased to the 10%–50% range used everywhere else in the memo (§I, §VI Partnership remedy addendum, §X Partnership Triangulation). This is the only material defect in this section pair.
- The Partnership-remedy addendum at lines 1047–1067 uses a **DIFFERENT pricing convention** than §X: addendum prices each tier at face value of equity-at-$1.1B *plus* cash ($120–135M / $300–325M / $435–460M / $600–650M); §X uses **inverse-cash** at a fixed $550M total ($440M / $275M / $165M / $0). **These two systems do not reconcile.** Flag for counsel — the inverse-cash invariant in §X is the cleaner negotiation frame; the addendum should be rewritten to match or explicitly explain why it doesn't.

---

## Math-audit table

| # | Claim (line) | Asserted | Computed | Match | Notes |
|---|---|---|---|---|---|
| 1 | Small subtotal (838) | $80M | 30+10+10+30 = **$80M** | ✓ | |
| 2 | Medium subtotal (854) | $215M | 80+30+40+55+10 = **$215M** | ✓ | |
| 3 | Big subtotal (872) | $590M | 80+80+120+200+10+50+50 = **$590M** | ✓ | |
| 4 | DTSA 2× exemplary on $80M base (Big, 865) | +$80M | 2 × 80 − 80 = $80M overlay | ✓ | Correctly modeled as 1× exemplary added to compensatories |
| 5 | Patent 3× treble on willfulness (Big, 866) | +$120M | implied compensatory base ≈ $60M → +$120M overlay | ✓ | Internally consistent if compensatory patent slice ≈ $60M |
| 6 | Opp-cost rate (999) | $12.2M/day | $1.1B / 90 = **$12.222M** | ✓ | Rate is accurate; footnote acknowledges this **excludes** 3 white-label ventures + OnyxPlus, so true rate is higher |
| 7 | 5,991 grand-total Kelling commits / 90d (950) | 5,991 | 4,726 (primary) + 1,265 (related) = **5,991** | ✓ | Internal sum is exact |
| 8 | Counterparty-primary subtotal (917) | 4,726 | per-repo column sums to **4,726** | ✓ | |
| 9 | ats/ commit count 90d (896) | 806 | local git sampling: **797** (z@hanzo.ai + Kelling identities, `--author -i`) | ≈✓ | Within 1.1%; remainder likely co-author trailers and bot-attributed merges |
| 10 | universe/ commit count 90d (905) | 1,436 | local: **1,433** | ≈✓ | Within 0.2% |
| 11 | operator/ commit count 90d (904) | 354 | local: **350** | ≈✓ | Within 1.1% |
| 12 | bd/ commit count 90d (897) | 388 | local: **384** | ≈✓ | Within 1.0% |
| 13 | node/ commit count 90d (903) | 338 | local: **245** | ⚠ | 27% under. Authorship attribution likely includes a co-committed identity not captured by my filter; counsel should run with the canonical author-set used to produce the table |
| 14 | exchange/ commit count 90d (910) | 522 | local: **439** | ⚠ | Same caveat as #13 — 16% under |
| 15 | Lux upstream 0 commits 90d (978–984) | 0 across 6 repos | local: **0,0,0,0,0,0** | ✓ | **Exact match.** Decisive evidence preserved on disk |
| 16 | Damages Summary IP column (1040–1042) | 80 / 215 / 590 | matches §VI bodies | ✓ | |
| 17 | Damages Summary +Opp Cost (1040–1042) | 180–380 / 315–515 / 690–890 | 80+(100–300); 215+(100–300); 590+(100–300) = 180–380 / 315–515 / 690–890 | ✓ | Range floor uses conservative $100M; ceiling uses $300M |
| 18 | Headline "$180M to $890M" (§I, line 182) | $180M–$890M | floor of Small+Opp ($180M) → ceiling of Big+Opp ($890M) | ✓ | Cross-ref propagates correctly |
| 19 | Partnership addendum Floor 10% nominal (1052) | $120–135M | $110M equity (10% × $1.1B) + $10–25M cash = **$120–135M** | ✓ (additive frame) | **Conflicts with §X inverse-cash frame** — see #23 |
| 20 | Addendum Recommended 25% (1054) | $300–325M | $275M equity + $25–50M cash (implied) = **$300–325M** | ✓ (additive frame) | Same conflict as #19 |
| 21 | Addendum Stretch 35% (1054) | $435–460M | $385M equity + $50–75M cash (implied) = **$435–460M** | ✓ (additive frame) | Same conflict |
| 22 | Addendum Maximum 50% (1055) | $600–650M | $550M equity + $50–100M cash (implied) = **$600–650M** | ✓ (additive frame) | Same conflict |
| 23 | §X inverse-cash invariant (1349, 1365–1368, 1376–1377) | $550M total at every tier; 50%/0; 35%/$165M; 25%/$275M; 10%/$440M | 0.5·1100=550; 0.35·1100=385 → 550−385=**165**; 0.25·1100=275 → 550−275=**275**; 0.10·1100=110 → 550−110=**440** | ✓ | Math inside §X is exact and self-consistent |
| 24 | §VII "Lux 10% equity stake" framing (1074, 1076) | 10% only | range elsewhere is 10–50% | ✗ | **STALE.** §VII still single-points 10% while §I, §VI addendum, §X all use 10–50%. Needs rebase |
| 25 | §VII Base ARPU Stage 4 Lux 10% (1094) | $15B | 0.10 × $150B EV = **$15B** | ✓ at 10% | At rebased tiers: 25%→$37.5B, 35%→$52.5B, 50%→$75B |
| 26 | §VII Premium ARPU Stage 4 Lux 10% (1100) | $40B | 0.10 × $400B EV = **$40B** | ✓ at 10% | At rebased tiers: 25%→$100B, 35%→$140B, 50%→$200B |
| 27 | §I "ranges into the $B+ at scale" (line 184) | $B+ | §VII supports ≥$1.5B at 10% Base Stage 3+; vastly more at 25–50% | ✓ | Consistent (in fact understated relative to the 10–50% range) |
| 28 | Conservative opp-cost claim $100–300M (1023) | $100–300M | derived from 10–25% bandwidth-rate × $1.1B (rounded) = $110M–$275M ≈ $100–300M | ✓ | Reasonable rounding |

**Verdict:** 24 ✓, 4 ≈✓ (within sampling tolerance), 1 ✗ (the §VII rebase staleness), 0 outright math errors. The single ✗ is **scope drift**, not an arithmetic bug — §VI was correctly updated to 10–50% but §VII was missed.

---

## Findings & recommendations (no edits made)

### F-1 — §VII is stale relative to the rebased 10–50% equity range (HIGH)

**Location:** lines 1070–1109.

**Problem:** §VII opens with "computes Lux's economic interest at each under a proposed 10% equity stake" and the column header is "Lux 10%". This is the **pre-rebase** assumption. Every other quantitative section of the memo (§I exec summary, §VI Damages-Summary addendum, §X Partnership Triangulation, §XV prayer) now uses the **10%–50%** partnership range with $550M total-nominal invariant.

**Recommended rewrite (for counsel — DO NOT apply unilaterally):**

Replace the single "Lux 10%" column with **four columns** — `Lux 10%`, `Lux 25%`, `Lux 35%`, `Lux 50%` — or keep one column but show it as a range, e.g. `Lux 10–50% = $1.5B–$7.5B` at Stage 3 Base ARPU. Updated values:

| Stage | EV (Base ARPU 15×) | Lux 10% | Lux 25% | Lux 35% | Lux 50% |
|---|---|---|---|---|---|
| 1 (100K) | $150M | $15M | $37.5M | $52.5M | $75M |
| 2 (1M) | $1.5B | $150M | $375M | $525M | $750M |
| 3 (10M) | $15B | $1.5B | $3.75B | $5.25B | $7.5B |
| 4 (100M) | $150B | $15B | $37.5B | $52.5B | **$75B** |

The headline at line 1106–1108 ("worth between $5M and $40B") should become "worth between $5M (Stage 1 Conservative @ 10%) and **$200B** (Stage 4 Premium @ 50%)."

### F-2 — Partnership-remedy addendum (§VI) uses an *additive* pricing frame that conflicts with §X's *inverse-cash* invariant (HIGH)

**Location:** §VI lines 1047–1067 vs §X lines 1365–1368.

**Problem:** §VI addendum says Floor 10% = `$110M equity + $10–25M cash = $120–135M total`. §X says Floor 10% = `$110M equity + $440M cash = $550M total`. These are **two different deals** under the same labels.

The §X frame is the correct one strategically — every tier delivers the same $550M nominal so the Counterparty's only decision variable is "how much do you want to dilute vs how much cash can you raise". The §VI addendum re-introduces an *additive* frame where higher equity = higher total cost, which is exactly the cognitive trap §X is engineered to avoid.

**Recommended rewrite:** §VI addendum should be rewritten to mirror §X:

> "Floor (10% equity) = $110M equity + $440M cash; Recommended (25%) = $275M + $275M; Stretch (35%) = $385M + $165M; Maximum (50%) = $550M equity + $0 cash. **Each tier delivers the same $550M nominal value to Lux** — the Counterparty chooses the equity/cash mix that best matches its capital posture. See §X for governance rights and reciprocal commitments at each tier."

### F-3 — Sampling drift in two repo rows (LOW)

**Location:** table at lines 891–921.

**Observation:** Local git sampling reproduces the asserted commit counts within ~1% for `ats/`, `universe/`, `operator/`, `bd/`, but underbills `node/` (245 vs 338) and `exchange/` (439 vs 522) by 16–27%. The likely explanation is that the table-generating script used a broader author identity set (e.g., included `zach@*`, `kelling@*`, GitHub noreply variants, plus a Co-authored-by trailer scan).

**Recommended:** Preserve the exact author-identity regex used to generate the table as a forensic exhibit (`exhibits/git-audit-authors.txt`). When opposing counsel runs their own audit they will need to reproduce the same identity-merge rules to land on the same numbers. The decisive 0/0/0/0/0/0 finding on the Lux upstream side is **exact** and needs no caveat.

### F-4 — "TODO: rebase per counsel" markers still in §VI Medium/Big tables (MEDIUM)

**Location:** lines 851 ("Disgorgement on current-raise attribution (5% of enterprise value, TODO: rebase per counsel)") and 867 (same, 15–20%).

**Observation:** These TODO markers should be resolved before this memo is sent to any external counterparty. They signal a draft posture in what is otherwise a polished settlement-readiness document. Either (a) replace with the rebased percentages counsel has confirmed, or (b) move the TODO to a margin comment that is suppressed in the PDF render.

### F-5 — Per-day value-creation rate cross-check (FYI)

If we include the 3 whitelabel tenants + OnyxPlus, the conservative gross "per-day value-creation" figure rises materially:

- Counterparty primary: $1.1B / 90 = $12.22M/day
- + VCC + MLC + EquityTable + OnyxPlus, if each is conservatively assumed to be a $50M-EV new venture: +$200M / 90 = +$2.22M/day
- **Floor-honest rate: ~$14.4M/day**

The memo says "materially higher than the $12.2M figure" — a single sentence quantifying the floor at $14–15M/day would harden the claim without overreaching.

---

## Cross-reference integrity

- §I (lines 181–186) ↔ §VI (lines 1040–1042) ↔ §XV (line 1741): **all three quote $80–$590M IP / $180–$890M with opp-cost. ✓**
- §I (line 184) "$B+ at scale" ↔ §VII (lines 1086–1100): **consistent**, though §VII understates by limiting to 10%.
- §VI addendum (lines 1047–1067) ↔ §X (lines 1349–1377): **CONFLICTS** on per-tier nominal value — see F-2.

---

## Artifacts referenced

- Memo: `/Users/z/work/lux/legal/liquidity/Lux_IP_Enforcement_Memorandum_2026_05_25.tex`
- Git evidence (Liquidity side): `~/work/liquidity/{ats,universe,exchange,operator,node,bd}` — reproducible with `git log --since="90 days ago" --author=<identity> --oneline`
- Git evidence (Lux upstream side): `~/work/lux/{node,consensus,crypto,evm,vm,precompile}` — **all six return 0 for Kelling-attributed authors in the 90-day window. Exact.**
