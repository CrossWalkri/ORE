---
title: ORE-to-CRAFT Condition Map
version: 0.1.0
date: 2026-07-18
status: Companion mapping document. Shows where ORE attaches to each of the six CRAFT conditions, against CRAFT specification v0.4.4 and ORE specification v0.1.2. Descriptive of both documents; normative content lives in the specifications themselves.
license-intent: CC0
---

# ORE-to-CRAFT Condition Map

CRAFT's six conditions discipline the evaluation chain an operator builds. ORE extends each condition's discipline across the ingestion boundary, into the part of the chain the operator did not build. This document maps the attachment points, condition by condition, so that an adopter of either specification can see exactly where the other one connects. As of CRAFT v0.4.4, a chain that ingests material it did not create carries an ingestion boundary declaration (CRAFT Section 6.1), satisfied by adopting ORE or by declaring equivalent obligations; this map is the worked account of what that adoption does at each condition.

The map is descriptive. Nothing here adds obligations beyond what the two specifications state; where a mapping suggests a future obligation, it is marked as a direction, not a requirement.

## Condition 1: Decision Context Specification

CRAFT's frame element requires naming the mechanism by which entities enter the evaluation. For ingested material, ORE's intake postures are that declaration at the source level: Screened, Graded, and Open are three answers to when grading happens and what ungraded material may touch, and CRAFT v0.4.4 states that the frame declaration is completed by the ingestion boundary declaration.

CRAFT's risk reduction statement requires identifying the three inputs that combine to produce risk (hazard, uncertainty, exposure) and stating which the chain addresses, for whom. ORE is the declared instrument for the uncertainty input as it concerns sources: a grade measures how much of a source's reliability can currently be seen, and what is being trusted that cannot be seen. ORE's Section 5 exposure obligation is the mechanism by which the risk-bearer named in Condition 1 can see what any output rests on; the exposure exists for the reader of the output, not for the operator.

CRAFT's adversarial threat model requires naming actors who can satisfy the conditions while defeating the chain's purpose. The boundary-shaped members of that class are what ORE names structurally: manufactured corroboration (many channels tracing to one origin), party count impersonating independence, and engineered conformance behind opacity. A chain's threat model that omits its source boundary has omitted the entry route that requires no knowledge of the chain's internals.

Role in one line: ORE supplies Condition 1's declarations for the front door.

## Condition 2: Technical Ontology Adequate to the Decision Context

CRAFT requires known gaps in the ontology to be stated, because unstated gaps become invisible failure modes indistinguishable from valid output. ORE's named-flag discipline is the same rule applied to sources: a dimension that cannot be assessed is recorded as a named limitation, never defaulted to a middle value and never silently omitted. The two requirements are one discipline at two stages: no silent gaps in what the chain measures, no silent gaps in what the chain was fed.

ORE's own grading bases are held to this condition's standard: two independent graders applying a declared basis to the same source must reach the same account. A dimension whose assessment cannot be reproduced from the declared basis is a precision deficit in both specifications' terms.

Role in one line: ORE is the stated-gaps discipline for everything the ontology's constructs will be fed with.

## Condition 3: Valid Measurement Instruments within the Ontology

The tightest coupling of the six. CRAFT makes uncertainty quantification a carried requirement on every instrument and requires systematic error sources to be named, because systematic error is directional and compounds downstream. For any instrument that reads an external feed, the source is part of the instrument, and ORE's grade profile is the source-level term of the instrument's uncertainty statement. The mapping is close to mechanical: a source with compromised independence contributes systematic, directional error; a source with thin confirmation architecture contributes a wider uncertainty band; a flagged or unassessable dimension marks a region where the instrument's error is uncharacterized. An instrument uncertainty statement that stops at the instrument's own mechanics, without the grades of the sources it reads, is incomplete on CRAFT's own terms.

CRAFT's adversarial robustness requirement for financial instruments asks what manipulation would cause a false reading. For oracle-consuming instruments this is ORE's confirmation-architecture dimension read as an instrument property: what confirmed the reading, and what would it cost an adversary to have been that confirmation.

CRAFT's multi-hop inferential validation requires declaring every intermediate construct between instrument and decision. ORE's transitive definition of support (everything an output rests on, traced all the way back) is the same tracing requirement applied to material rather than inference: both refuse validation that stops one hop short.

Role in one line: ORE completes every instrument's uncertainty budget at the point where the instrument touches the world.

## Condition 4: Pre-Specified Evaluation Criteria

CRAFT requires criteria specified before data is observed, because criteria adjusted to the data optimize for coherent appearance. ORE's grading bases obey the same discipline at the boundary: the basis for each dimension's assessment is declared before material is graded, not fitted to the material afterward.

CRAFT's gaming clause observes that stated criteria are optimized against under incentive. ORE's opacity doctrine is the same insight at the boundary: an actor who knows the disclosure requirements can engineer conformance while obscuring what matters, which is why ORE weights monitored behavior over declared compliance. The two clauses are one adversary described at two stages, and a chain that hardens Condition 4 while admitting sources on unmonitored declarations has hardened the wrong door.

Role in one line: ORE keeps the criteria's foundations from being quietly post-hoc.

## Condition 5: Explicit Decision Logic

CRAFT requires the logic by which outputs produce decisions to exist as a written specification before outputs exist, independently of the code that implements it. This is where the composition of graded material becomes accountable. ORE deliberately refuses to combine its dimensions into one score; the combining step belongs to the consumer of the readings, and Condition 5 is where that consumer's combining is written down. The decision logic states what a weakest-support reading does to the decision, what a flag does, and what an Open-posture citation boundary forbids, before any decision is produced. The rule this enforces is symmetric for human and machine consumers: silent composition is forbidden everywhere; legible composition is permitted anywhere, by anyone, of any kind. A pipeline that consumes grade profiles satisfies this exactly as a person does, by its combining logic existing as a readable, challengeable specification.

CRAFT's consequence level declaration gives the natural coupling: the harm magnitude of acting on a false claim calibrates the evidence bar, and grade-aware decision logic is the boundary expression of that calibration. Higher-consequence decisions demand stronger support profiles; a direction for both specifications, not yet an obligation in either.

Role in one line: ORE delivers the decision logic legible ingredients; Condition 5 is where combining them becomes accountable.

## Condition 6: Feedback Mechanism with Propagation

CRAFT requires detected errors to propagate to every prior stage. The ingestion boundary is a prior stage, and ORE makes it a concrete propagation target: an error traced to a source updates that source's grade, and the accumulating record of such updates is the track-record dimension being manufactured by the feedback mechanism itself. A chain without ORE propagates source-originated errors to a stage with no ledger; a chain with ORE gives Condition 6 a forwarding address for every error that was the world's fault.

The loop depths map directly. Single-loop corrects the affected record. Double-loop re-grades the source or revises a dimension's declared basis. Triple-loop revisits the posture: whether this source class should be admitted on these terms at all.

CRAFT's calibration drift requirement gains a localization instrument: systematic directional drift in chain outputs may originate in source degradation, and ORE's monitoring obligation is the reading that says which sources moved. Conversely, the lifecycle obligations that stringent ingestion regimes carry (recurring re-assessment, escalation, exit) are Condition 6 discipline applied to sources; ORE inherits them through this attachment rather than restating them.

Role in one line: ORE is Condition 6's propagation target for source-originated error, and Condition 6 is where ORE's grades learn.

## Summary table

| CRAFT condition | ORE attachment | Role in one line |
|---|---|---|
| 1. Decision Context | Intake postures complete the frame declaration; grade as the declared uncertainty input; Section 5 exposure serves the named risk-bearer; boundary threat classes for the adversarial model | Supplies Condition 1's declarations for the front door |
| 2. Technical Ontology | Named-flag discipline as the stated-gaps rule for ingested material; grading bases held to the two-grader test | Stated-gaps discipline for what the constructs are fed |
| 3. Measurement Instruments | Grade profile as the source-level term of every instrument's uncertainty budget; confirmation architecture as adversarial robustness; transitive support as multi-hop tracing | Completes the uncertainty budget where the instrument touches the world |
| 4. Pre-Specified Criteria | Grading bases declared before material is seen; opacity doctrine as the boundary form of the gaming clause | Keeps the criteria's foundations from being post-hoc |
| 5. Explicit Decision Logic | Composition of grade profiles written into the decision logic; no silent composition, human or machine; consequence level as the coupling point | Legible ingredients in; accountable combining here |
| 6. Feedback with Propagation | Source grades as propagation target; loop depths as record, re-grade, re-posture; monitoring localizes calibration drift; lifecycle obligations inherited | The forwarding address for the world's faults; where grades learn |

## What this map is not

It is not an inheritance receipt: ORE is a companion specification, not a CRAFT domain application, and carries no receipt. It is not normative: each obligation described here binds through its home specification, and a conflict between this map and either specification is resolved in the specification's favor. And it is not complete for the future: the directions marked above (consequence-calibrated support profiles, the lifecycle stream) belong to the specifications' own next versions, where they will be obligations or will not exist.
