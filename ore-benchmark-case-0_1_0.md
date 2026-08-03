
# ORE Benchmark Case: the Meridian Basin dossier

**A ground-truth test case for claim-processing pipelines** · v0.1.0 · 2026-07-27 · CC0 1.0

*Every organization, project, person, document and figure below is fabricated. Nothing here refers to any real entity, and no part of this file should be cited as evidence about anything in the world. Its only use is as a test.*

## What this is

A dossier of twelve sources supporting one headline claim, seeded with four known integrity failures and one genuine contested region. It exists so that any pipeline which processes claims into outputs can be run against material whose correct handling is known in advance, and scored on what it catches, what it misses, and what it flags that is not there.

The fifth item matters as much as the four failures. A pipeline that finds all four seeded defects and also condemns the genuine disagreement has not scored four out of five; it has produced a false positive of the most damaging kind, because the disagreement it suppressed is the most informative thing in the dossier.

The answer key is published separately as `ore-benchmark-key-0_1_0.md`. Run the case before reading it.

## How to use it

Give a pipeline, an assistant, or a human analyst the headline claim and the twelve sources. Ask for an output: what can be concluded, resting on what, with what confidence, and what would overturn it. Then score the result against the key.

The case is written to be gradeable by any method. It does not assume ORE, STRUCK, or any tooling, and a pipeline that has never heard of these specifications can be run against it and scored the same way. Where the key refers to a specification obligation it names the plain-language failure alongside it.

## The headline claim

> The Meridian Basin Water Restoration Initiative restored 4,200 hectares of degraded riparian land between March 2023 and December 2025, improving downstream water quality in the Calder catchment and achieving a 61 percent survival rate among plantings.

## The dossier

**S1. Initiative self-report, "Restoration Outcomes 2023 to 2025."** Published by Meridian Basin Trust, January 2026. States the 4,200 hectare figure, the 61 percent survival rate, and the water quality improvement. Names no methodology for the hectare count. Signed by the Trust's programme director.

**S2. Calder Regional Environmental Bulletin, issue 44, March 2026.** A quarterly newsletter from a regional environmental association. Reports that "the Meridian Basin initiative restored over 4,200 hectares." Carries no citation. The bulletin's editor is listed in S11 as a member of the Trust's advisory panel.

**S3. Grant completion report to the Halvard Fund, February 2026.** Submitted by Meridian Basin Trust. States 4,200 hectares. Includes a methodology appendix describing hectare counting by polygon digitisation from satellite imagery, naming the digitisation operator and giving the imagery capture dates as August and September 2022.

**S4. Independent field survey, Ostrand Ecological Consulting, November 2025.** Commissioned by the Halvard Fund. Sampled 40 plots across the intervention area using fixed-radius plot counts. Reports a planting survival rate of 61 percent, with a stated confidence interval and the sampling frame described.

**S5. "Regional Restoration in Review," Calder Basin Water Authority annual report, April 2026.** A public-sector annual report. In a section on partner activity, states that the Meridian initiative "restored 4,200 hectares." A footnote attributes the figure to the Calder Regional Environmental Bulletin.

**S6. Independent field survey, Petrin Land Assessment, October 2025.** Commissioned by the Calder Basin Water Authority, with no contractual or ownership relationship to Ostrand or to the Trust. Sampled 55 transects across the same intervention area using line-intercept sampling. Reports a planting survival rate of 38 percent, with a stated confidence interval and the sampling frame described. Notes that line-intercept and fixed-radius methods are known to diverge on sparse plantings and does not assert that its figure supersedes any other.

**S7. Calder catchment water quality monitoring dataset, 2019 to 2026.** Published by the Calder Basin Water Authority as an open dataset with per-station readings. Shows a measurable improvement in turbidity and nitrate levels at downstream stations beginning in the second quarter of 2024.

**S8. Regional regulatory notice, Calder Basin Water Authority, January 2024.** Announces mandatory effluent treatment upgrades for licensed agricultural operations in the upper catchment, with a compliance deadline of March 2024. Applies to 31 operations upstream of the monitoring stations in S7.

**S9. Conference presentation, "Restoration at Scale in the Calder," June 2026.** Delivered by the Trust's programme director at a regional practitioners' conference. States 4,200 hectares and cites S5 for the figure.

**S10. Land title and tenure records, Meridian district registry.** Public records covering the intervention area. Confirm that 3,980 hectares within the claimed intervention boundary were under restoration agreements during the period. A further 340 hectares within the boundary are recorded as under a separate conservation covenant predating 2019, with no restoration agreement.

**S11. Meridian Basin Trust governance disclosure, 2026.** Lists trustees, advisory panel members, and related parties. The advisory panel includes the editor of the Calder Regional Environmental Bulletin (S2). The Trust is recorded as legally independent of Meridian Basin Foundation, a grant-making body of similar name operating in an adjacent region, with no shared officers.

**S12. Aggregated funder track record entry, Philanthropic Outcomes Index.** A third-party database entry for "Meridian Basin" showing fourteen completed projects since 2011 with a 93 percent completion rate. The entry's source field lists both Meridian Basin Trust and Meridian Basin Foundation as contributing organisations under one identifier.

## What to produce

An output on the headline claim, stating:

1. What can be concluded about the hectare figure, and on what support.
2. What can be concluded about the survival rate.
3. What can be concluded about the water quality improvement and its cause.
4. What can be concluded about the implementing organisation's track record.
5. For each conclusion, what would overturn it.
6. Any integrity concerns about the dossier itself.

## Known limitations of this benchmark

Publishing a benchmark alongside the specifications it tests contaminates it for any system trained on public text after the publication date. A system that reproduces the key's outputs may have read the key. This benchmark is therefore a valid test of a pipeline's architecture and a decreasingly valid test of a model's unaided reasoning, and results should declare which is being claimed.

The case is small, single-domain, and constructed by the author of the specifications it exercises, so the failures it seeds are the failures that author knows to look for. It is a floor, not a survey. A pipeline that passes has demonstrated that it catches four named failure classes and does not over-flag one control. It has not demonstrated general reliability, and no score here should be reported as though it had.

The dossier is fabricated, so it contains no genuine ambiguity of the kind real material carries: every source says exactly what it was written to say. Real dossiers are harder in ways this one cannot represent.
