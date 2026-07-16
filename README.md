# ORE: Origin, Reliability, Exposure

A companion specification to [CRAFT](https://github.com/CrossWalkri/craft-meta-standard): what an evaluation chain is allowed to assume about what enters it. Ore is what gets graded before anything is built from it.

Every system that turns records into decisions has sources it did not create. ORE specifies what an honest account of a source must contain, and what a system is obligated to do differently when that account is thin. It grades uncertainty, never worth: a grade calibrates weight, monitoring, and eligible downstream use, and the judgment of whether the support suffices stays with the person reading the output.

<p align="center">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="images/evidence-path-0_1_0-dark.svg">
  <img alt="The evidence path: ORE grades the source, WALKRI grades the field, CRAFT holds the chain, the finding contract binds the claim." src="images/evidence-path-0_1_0-light.svg" width="880">
</picture>
</p>

**[Read the specification](ore-specification-0_1_0.md)** (v0.1.0)

## What it specifies

- **Origin:** provenance integrity, whether an input came from where it claims, unchanged, and why strength there cannot stand in for anything else.
- **Reliability:** epistemic soundness and confirmation architecture (the four-case taxonomy of what confirmed a source's output, and why party count is not independence), with track record and independence as declared extension dimensions.
- **Exposure:** every output that rests on ingested material exposes the grade profile of its support. Nothing is silently laundered into a downstream judgment.

Plus **intake postures** (Screened, Graded, Open): systems legitimately differ in when grading happens and what ungraded material may touch; ORE requires the posture be declared, enforced, and recorded, not that any one posture be used.

## Relations

ORE inherits by reference from [CRAFT](https://github.com/CrossWalkri/craft-meta-standard) (the chain), [WALKRI](https://github.com/CrossWalkri) (the field: the paired instrument at the same boundary), the [Precision-First Design Standard](https://github.com/coordination-structural-integrity-suite/suite) (operational definability), and the [Information Asymmetry Classification Standard](https://github.com/coordination-structural-integrity-suite/suite) (the asymmetry taxonomy). It is independently adoptable: taking ORE requires taking nothing else.

Together the family covers the evidence path end to end: **source (ORE), field (WALKRI), chain (CRAFT), claim** (the finding output contract).

## License

CC0 1.0 Universal. No permission or fee, no attribution required. See [LICENSE](LICENSE).
