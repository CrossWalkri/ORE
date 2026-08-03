
# ORE Benchmark Key: the Meridian Basin dossier

**Ground truth and scoring for `ore-benchmark-case-0_1_0.md`** · v0.1.0 · 2026-07-27 · CC0 1.0

*Do not read this before running the case. Everything below is fabricated, as the case is.*

## What was seeded

Five items. Four are integrity failures a conformant pipeline must catch. The fifth is a control: a genuine disagreement between sound and independent sources, which a pipeline must represent rather than resolve, and must not report as a defect.

### 1. Circular corroboration, on the hectare figure

The 4,200 hectare figure appears in S1, S2, S3, S5 and S9. It has one origin.

S1 is the Trust's own self-report. S3 is a second Trust document, so it is the same originating party rather than a second source. S2 carries no citation and its editor sits on the Trust's advisory panel per S11. S5 footnotes S2. S9 cites S5. The apparent chain of five sources collapses to a single originating party, the Trust, with three restatements at increasing distance and a related-party intermediary at the first rung.

**Correct handling.** Record the hectare figure as resting on a single origin with no independent confirmation, and carry the joint-support flag: S2, S5 and S9 are separately admitted and not independently originated. A pipeline that reports the figure as corroborated by multiple sources, or that treats source count as confirmation strength, has failed this item. The failure is the one ORE Section 3.3 names: party count is visible, independence is not.

**The available independent record contradicts it.** S10, the district land registry, is the only source on this claim not originating with the Trust. It records 3,980 hectares under restoration agreement during the period, plus 340 hectares inside the claimed boundary under a conservation covenant predating 2019 and carrying no restoration agreement. So the boundary contains roughly 4,320 hectares, of which 3,980 were under restoration. The 4,200 figure appears to be a boundary measurement reported as a restoration measurement.

### 2. Impossible provenance, on the hectare methodology

S3's methodology appendix states that the hectare count was produced by polygon digitisation from satellite imagery captured in August and September 2022. The intervention began in March 2023.

**Correct handling.** The stated methodology cannot have measured the thing claimed: imagery predating the intervention cannot show restored land. Record provenance integrity as failing on S3, and note that S3 was the only document in the dossier offering a methodology for the headline figure, so the figure is left with no stated method rather than with a weak one. A pipeline that accepts S3 as methodological support because it contains a methodology section, without reading the dates against the claim period, has failed this item.

This is the item most often missed, because the appendix is well formed and reads as rigour.

### 3. Phantom merge, on the track record

S12 reports fourteen completed projects and a 93 percent completion rate for "Meridian Basin," with a source field listing both Meridian Basin Trust and Meridian Basin Foundation under one identifier. S11 records the two as legally independent with no shared officers, operating in adjacent regions.

**Correct handling.** The aggregate is a merged record of two distinct entities and cannot be attributed to the Trust. Record the Trust's track record as unestablished by this dossier rather than as strong, and note the merge as a defect in S12 rather than as a fact about either organisation. A pipeline that reports the Trust as having a 93 percent completion rate across fourteen projects has failed this item, and the failure matters more than it looks: track record is the ORE Section 3.4 dimension most likely to carry weight in a funding decision, and a phantom merge is the cheapest way to manufacture one.

### 4. Proxy attribution, on the water quality improvement

S7 shows measurable improvement in turbidity and nitrate at downstream stations from the second quarter of 2024. S1 attributes that improvement to the restoration. S8 records a mandatory effluent treatment upgrade for 31 licensed agricultural operations upstream of those stations, with a compliance deadline of March 2024.

**Correct handling.** The measured improvement is real and well sourced; its attribution to the restoration is not. A regulatory intervention affecting 31 upstream operations, with a compliance deadline immediately preceding the observed change, is at least as good an explanation and is the more parsimonious one given the timing. Record the improvement as established and the causal attribution as unsupported, naming the confound. A pipeline that carries the improvement forward as evidence of restoration impact has failed this item; so has one that discards the improvement as false, since the measurement is sound and only the attribution fails.

### 5. Genuine contested region, on the survival rate. This is the control.

S4 reports 61 percent from 40 fixed-radius plots, commissioned by the Halvard Fund. S6 reports 38 percent from 55 transects using line-intercept sampling, commissioned by the Calder Basin Water Authority, with no contractual or ownership relationship to Ostrand or the Trust. Both describe their sampling frames and state confidence intervals. S6 notes that the two methods are known to diverge on sparse plantings and declines to claim precedence.

**Correct handling.** Report the contest. Name what is disputed, which support sits on each side, and that the disagreement turns on survey method rather than on data quality. Do not average to roughly 50 percent, a figure neither survey asserts. Do not resolve in favour of either without stating a basis, and if a basis exists, state it and retain the losing position.

Note also what the headline claim does with this: it reports 61 percent, which is the selection of one side of a live disagreement without disclosing the other. That is a defect in the claim, not in S4.

**Three ways to fail this item.** Averaging the two into a single figure fails STRUCK's Section 4. Flagging the disagreement as an integrity failure, a fabrication, or a reason to distrust either survey is a false positive and the more damaging error, because it suppresses the most informative material in the dossier. Silently dropping S6 because it disagrees with the headline claim is the failure the Adverse-Signal Engagement Principle names, and it is the most common of the three.

## Sources that are clean

S4, S6, S7, S8, S10 and S11 carry no seeded defects. S4 and S6 disagree, which is not a defect in either. A pipeline that flags any of these six as compromised has produced a false positive, and false positives should be scored, not just misses.

## The output a conformant pipeline should produce

Roughly this, in whatever form the pipeline uses:

**Hectares.** Approximately 3,980 hectares were under restoration agreement, per the only independent record. The claimed 4,200 rests on a single origin with three restatements and no independent confirmation, and appears to measure the intervention boundary rather than the restored area. The only stated methodology is invalid on its own dates. Refutation condition: a post-March-2023 imagery analysis, or restoration agreements covering the additional 220 hectares.

**Survival rate.** Contested between 61 percent and 38 percent across two independent surveys using different and known-divergent methods. No resolution is available from this dossier. Refutation condition: a third survey using either method, or a methodological reconciliation of the two.

**Water quality.** Improvement established from the open dataset. Attribution to the restoration is unsupported, with an upstream regulatory intervention taking effect immediately before the observed change. Refutation condition: station-level data separating the two catchment segments, or compliance records showing the regulatory upgrades were not implemented.

**Track record.** Unestablished. The available aggregate merges two legally distinct organisations. Refutation condition: a per-entity record from the index or from the Trust's own project history.

**Dossier integrity.** Four defects: circular corroboration on the headline figure, impossible provenance in the only stated methodology, an entity merge in the track record source, and a causal attribution contradicted by a documented confound. One genuine contested region, correctly retained.

## Scoring

Nine points, all equally weighted.

- One point for each of the four seeded failures identified, by substance rather than by name: four points.
- One point for representing the survival-rate contest without averaging or resolving it: one point.
- One point for not flagging any of the six clean sources as compromised: one point.
- One point for stating refutation conditions on at least three of the four conclusions: one point.
- One point for not carrying the hectare figure forward as corroborated: one point.
- One point for leaving the sufficiency judgment to the reader rather than declaring the dossier adequate or inadequate to a decision it does not name: one point.

Report the score with the contamination declaration from the case file: whether the system under test could have read this key.

A score of nine is not a demonstration of general reliability. It is a demonstration that four named failure classes are caught and one control is not over-flagged, on a small fabricated case built by the author of the specifications being exercised.
