# ORE: Origin, Reliability, Exposure

A companion specification to [CRAFT](https://github.com/CrossWalkri/craft-meta-standard): what an evaluation chain is allowed to assume about what enters it. ORE is the chain's first legible commitment about its sources.

Every system that turns records into decisions has sources it did not create. ORE specifies what an honest account of a source must contain, and what a system is obligated to do differently when that account is thin. It grades uncertainty, never worth: a grade calibrates weight, monitoring, and eligible downstream use, and the judgment of whether the support suffices stays with the output's consumer, human or automated, never with the grade.

<p align="center">
<img alt="CRAFT is the meta-standard for an evaluation chain, drawn as a room whose six conditions (decision context, ontology, instruments, criteria set, decision logic, feedback) run its length from world to decision. ORE is the door in and STRUCK the door out, the two boundary standards CRAFT requires; WALKRI stands at the intake fields." src="images/standards-family-0_1_0.svg" width="880">
</p>

<p align="center">
<img alt="ORE and STRUCK on their own: the two ends of any chain, independently adoptable, bracketing any process with or without CRAFT in the middle." src="images/ore-struck-pair-0_1_0.svg" width="820">
</p>

What only ORE does, in one line: grade source visibility as uncertainty, refuse to let party count impersonate independence, treat opacity without verdicts, and make every output wear the grade profile of what it rests on.

**[Read the specification](ore-specification-0_1_2.md)** (v0.1.2)

## What it specifies

- **Origin:** provenance integrity, whether an input came from where it claims, unchanged, and why strength there cannot stand in for anything else.
- **Reliability:** epistemic soundness and confirmation architecture (the four-case taxonomy of what confirmed a source's output, and why party count is not independence), with track record and independence as declared extension dimensions.
- **Exposure:** every output that rests on ingested material exposes the grade profile of its support. Nothing is silently laundered into a downstream judgment.

Plus **intake postures** (Screened, Graded, Open): systems legitimately differ in when grading happens and what ungraded material may touch; ORE requires the posture be declared, enforced, and recorded, not that any one posture be used.

## What else is in this repository

- **[STRUCK](https://github.com/CrossWalkri/STRUCK)** (v0.1.2), the exit-boundary standard, now lives in its own repository. It is the output-side companion: the five obligations any evidence-grade output carries on its face. Graded evidence, refutation conditions, contested regions rather than averages, derivation chains walked to origin with labeled rungs, and the sufficiency judgment left with the consumer. A redirect stub remains at [`finding-contract-0_1_0.md`](finding-contract-0_1_0.md) so existing links keep resolving; the canonical home is the [STRUCK](https://github.com/CrossWalkri/STRUCK) repository.
- **[Prompts](ore-prompts-0_2_0.md)** (v0.2.0). Three copy-and-run prompts for any AI assistant, each self-contained: grade a source, check an evidence set for circular corroboration, declare an intake posture. No tooling required.
- **[The Claude skill](claude-skills/claude-skill-ORE-0_2_0.md)** (v0.2.0). A procedural encoding of ORE with a runtime sequence, so a partial task can be received and completed correctly.
- **[Benchmark case](ore-benchmark-case-0_1_0.md)** and **[key](ore-benchmark-key-0_1_0.md)** (v0.1.0). A fabricated twelve-source dossier with known ground truth, seeded with four integrity failures (circular corroboration, impossible provenance, a phantom entity merge, and a proxy attribution) and one genuine contested region that a pipeline must represent rather than resolve. Any system that turns claims into outputs can be run against it and scored. The case and the key publish separately so the case can be run first, and the contamination limit is stated in both.

## Relations

ORE inherits by reference from [CRAFT](https://github.com/CrossWalkri/craft-meta-standard) (the chain), [WALKRI](https://github.com/CrossWalkri) (the field: the paired instrument at the same boundary), the [Precision-First Design Standard](https://github.com/coordination-structural-integrity-suite/suite) (operational definability), and the [Information Asymmetry Classification Standard](https://github.com/coordination-structural-integrity-suite/suite) (the asymmetry taxonomy). It is independently adoptable: taking ORE requires taking nothing else. ORE does not require CRAFT; the dependency runs the other way, CRAFT depends on ORE and STRUCK to account for what enters and leaves its chain, and a CRAFT certification is not complete without them.

CRAFT holds the chain end to end as process; the others sit at loci on it. **ORE** is the accounting discipline at the source boundary (not a stage before the chain: ingestion is the chain's first stage, and ORE specifies what may be assumed about the sources feeding it). **WALKRI** holds the intake fields, and **[STRUCK](https://github.com/CrossWalkri/STRUCK)**, the exit-boundary standard for what an output must carry before anyone acts on it, binds the claim at exit.

The through line, stated once: every system that turns records into decisions has the same anatomy. Sources feed in material the system did not create, fields capture that material as data, and a chain of evaluation carries it to a claim someone acts on. Knowing begins honestly, or begins broken, in three places, and one standard stands at each: ORE at the source boundary, [WALKRI](https://github.com/CrossWalkri/WALKRI) at the field, [CRAFT](https://github.com/CrossWalkri/craft-meta-standard) over the whole path. One commitment runs through all three: no silent trust anywhere, and the worth-judgment left visible in the hands, human or automated, that make it. Each is independently adoptable; the through line is what they hold together.

As of CRAFT v0.4.4, a chain that ingests material it did not create carries an ingestion boundary declaration (CRAFT Section 6.1), satisfied by adopting ORE or by declaring equivalent obligations. Where ORE attaches to each of CRAFT's six conditions is mapped, condition by condition, in the **[ORE-to-CRAFT condition map](ore-craft-condition-map-0_1_0.md)**.

<p align="center">
<img alt="A two-column map of CRAFT's six conditions and what ORE completes at each. 1 Decision Context: declares what comes in the front door. 2 Technical Ontology: no silent gaps in what the chain is fed. 3 Measurement Instruments: completes each instrument's uncertainty budget. 4 Pre-Specified Criteria: keeps the criteria's foundations from being post-hoc. 5 Explicit Decision Logic: legible ingredients in, accountable combining. 6 Feedback with Propagation: a forwarding address for the world's faults." src="images/ore-craft-condition-map-0_1_0.svg" width="820">
</p>

## License

CC0 1.0 Universal. No permission or fee, no attribution required. See [LICENSE](LICENSE).
