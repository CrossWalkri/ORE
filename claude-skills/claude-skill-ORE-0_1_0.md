---
title: ORE Skill
version: 0.1.0
date: 2026-07-27
status: Procedural encoding of ORE v0.1.2 and STRUCK v0.1.2 for AI-assisted source grading, evidence auditing, and output production. Structured so a partial task can be received and completed correctly.
related_documents:
  - ore-specification-0_1_2.md (v0.1.2)
  - STRUCK v0.1.2 (github.com/CrossWalkri/STRUCK)
  - ore-craft-condition-map-0_1_0.md (v0.1.0)
  - ore-benchmark-case-0_1_0.md (v0.1.0)
  - ore-prompts-0_1_0.md (v0.1.0)
license: CC0 1.0
---

# ORE Skill

Invoke this skill before admitting any source into a system that will decide from it, before treating agreement among sources as confirmation, before producing any output offered as evidence-grade, and before auditing someone else's output. This is a procedural encoding of ORE (Origin, Reliability, Exposure) v0.1.2 and its output-side companion, STRUCK v0.1.2.

The two specifications divide the work at the two boundaries. ORE governs what a system may assume about what enters it. STRUCK governs what a system owes on the way out. A system operating both has an account of its material at entry and an account of what rests on it at exit; a system operating neither has confidence it cannot explain.

## The commitment that governs every operation below

A grade measures uncertainty, not quality. Every procedure here answers "how much of this can currently be seen, and what is being trusted that cannot be seen." None of them answers "is this good." A grade that never updates and never triggers monitoring is a verdict wearing another name, and issuing verdicts is the failure these specifications exist to replace.

Three consequences hold throughout and are not negotiable per task:

- **Never combine dimensions into a single score.** A profile of separately based assessments is hard to tune silently and cheap to audit. One number is the reverse. The refusal to combine is the grading's defense, not a limitation of it.
- **Never default an unknown to a middle value.** An assessment you could not make is recorded as a named gap. Ungraded and low-grade are different states with different obligations.
- **Never let strength on one dimension stand in for strength on another.** Provenance integrity guarantees origin and guarantees nothing about whether the originating party knew anything.

## Runtime Sequence

Identify which operation is requested and run the corresponding procedure in full.

1. **Source grading.** Run when a source is proposed for admission, or when an existing source's grade is challenged. See Part I.
2. **Confirmation architecture classification.** Run as part of source grading, or independently when asked how strongly a source's own process confirmed its output. See Part II.
3. **Independence assessment across an evidence set.** Run whenever multiple sources agree and that agreement is about to carry weight. This is the circular-corroboration check. See Part III.
4. **Opacity handling.** Run when a source will not disclose its internal architecture. See Part IV.
5. **Posture declaration.** Run once per system before ingestion, and again when the system's intake changes. See Part V.
6. **Grade exposure on an output.** Run when any output rests on ingested material. See Part VI.
7. **Output production.** Run when producing an output offered as evidence-grade. See Part VII.
8. **Output audit.** Run against an existing output, yours or another party's. See Part VIII.
9. **Standing-loss assessment.** Run when adverse evidence about an admitted source appears. See Part IX.
10. **Genesis-limitation handling.** Run when grading a new source or operating a new system. See Part X.

---

## Part I: Source grading

Grade on four dimensions. For each, record the assessment, the basis it was made on, and any sub-assessment that could not be computed, recorded as a named flag.

**Provenance integrity.** Did this input come from where it claims, and did it arrive unchanged? Near-binary: the evidence of origin and tamper-evidence either holds or it does not. Record what the evidence of origin actually is. Do not let a strong result here migrate to any other dimension.

**Epistemic soundness.** Is the source's output structured so that truth-evaluation by independent parties is possible? Assess three properties: are claims stated in terms reality can refute, are accuracy and relevance kept separate, and does the source distinguish what it observed from what it inferred. A perfectly sincere source can fail all three, and its outputs then resist independent evaluation regardless of intent.

**Confirmation architecture.** See Part II.

**Declared extension dimensions.** Track record and independence. Grade them where assessable; where not, declare their absence rather than omitting them silently. Track record asks whether this source's history of outputs surviving challenge has accumulated evidence about its reliability. Independence asks whether the source has a stake in how the attested events are recorded. A structurally sound source can be informationally captured, with all of its information flowing from parties interested in the outcome. Adversarial resistance, meaning whether a challenge mechanism functions under pressure rather than merely existing, is a sub-case of track record.

Close every grading by stating what would change it and what should be monitored over time. A grade without a monitoring obligation is a verdict.

---

## Part II: Confirmation architecture classification

Ask what confirmed this source's output at the time the source produced it. Classify on two axes.

| | Single-party | Multi-party |
| --- | --- | --- |
| **Trustless** | Cryptographic proof from one attester: origin guaranteed, underlying claim confirmed by no one | Mechanism-required confirmation such as multisig, validator set, or passed vote: the strongest case, subject to the party-count limit |
| **Trust-based** | One evaluator, curator, or badgeholder: social provenance, no independent check on content | Adversarial or consensus confirmation built into the mechanism, such as bonded curation with challengers, or multi-reviewer processes |

Two boundary states complete the taxonomy. **Unconfirmed** covers a source with no cryptographic proof and no confirming party: the raw uploaded document, the bare feed. It occupies none of the four cells and carries the highest confirmation uncertainty. And a source may carry **more than one mode at once**: a cryptographically signed output authored by a single evaluator has trustless origin and trust-based content. Record each mode present rather than forcing one cell.

**The party-count limit, which is the most frequently violated rule in this specification.** Party count is visible; independence is not. N signatures do not show that N independent perspectives confirmed anything. Keys can be held by one actor. Signers can be affiliated. Referencers can share one information source. A challenge can be brought by a party affiliated with the challenged. Never operationalize this dimension by counting parties. Where effective independence cannot be assessed, record that as a named flag on this dimension and say so in any output that rests on the source.

---

## Part III: Independence assessment across an evidence set

Run this whenever several sources appear to support the same claim. Agreement is evidence only when the agreeing sources are distinct in origin.

1. **Establish what each source rests on.** Follow every citation, attribution, footnote and acknowledgement. Where a source states no basis, record that: an uncited restatement is not an origin.
2. **Build and label the derivation chain for each.** Every rung carries its actual role: originating observation, primary record, aggregator, secondary reporting, review, restatement. Never present a review as the study or an aggregator as the registry.
3. **Record where each chain terminates,** including chains that cannot be walked to origin. Name why the walk stopped: the origin is unpublished, the aggregator does not disclose inputs, the trail ends in an unattributed claim. A truncated chain honestly labeled is conformant.
4. **Identify convergence.** Where two apparently distinct chains reach the same origin, record it. Then count distinct origins, never sources.
5. **Check for related parties.** Shared authorship, shared funding, board or advisory overlap, one party sitting on the editorial side of another. These defeat nominal independence.
6. **Report the result as a count of independent origins,** with the restatements identified, and apply the joint-support flag from Part VI where distinctness cannot be shown.

---

## Part IV: Opacity handling

Opacity raises uncertainty. It does not constitute a verdict. Under adversarial conditions, intentional obscurity and legitimate privacy are externally identical at the moment of ingestion, so:

- Admit or decline an opaque source according to the declared posture, never according to an unrecorded judgment about why the source is opaque.
- Enter an admitted opaque source at the grade its visible properties warrant, with a monitoring obligation attached.
- Never treat a disclosure requirement as resolving opacity. An actor who knows the requirements can engineer conformance while obscuring what matters. Monitoring behavior over time is the stronger response.

---

## Part V: Posture declaration

Declare one posture per system, or different postures per source class. State the treatment of opaque sources in advance: which classes are admitted at the grades their visible properties warrant, and which if any are declined.

**Screened.** Nothing enters ungraded; the ingestion boundary is the review boundary. What a screened intake declines is declared in advance as scope and posture, never as a grade verdict. Downstream condition: all held material is graded, and outputs expose grades.

**Graded.** Everything admitted enters at the grade its visible properties warrant, with review effort prioritized by uncertainty so the thinnest accounts get eyes first. Downstream condition: outputs may rest on any graded material and expose the profile; flagged dimensions travel with the record.

**Open.** Bulk material enters ungraded into quarantine. It may serve discovery, search and lead generation. It may not support outputs, attestations or decisions until graded. Downstream condition: the citation boundary is absolute. One channel remains open and must be declared rather than denied: a quarantined item read by a person who then produces an output that never cites it. That is the residual channel, and no structural boundary closes it.

Movement between postures is expected and legitimate. What conformance requires is that the posture in force when a record was admitted is recorded with it, so no record's grading history is ambiguous later.

---

## Part VI: Grade exposure on an output

**Support, defined.** An output's support is everything it rests on, traced back: the sources it draws on directly, and the sources of every intermediate result it draws on, down to ingested origins. A source is material when removing it, and everything only it supports, would change what the output can claim.

- Expose the grade profile of material support: for each dimension, the weakest assessment present anywhere in that support, plus every flag any source in it carries. The profile is per dimension; imply no ordering across dimensions.
- Where separately admitted sources cannot be shown distinct in effective origin, carry the **joint-support flag**. Separately admitted is not independently originated, and that difference is exactly what per-source grading cannot see across sources.
- Never silently launder ungraded or flagged material into a downstream judgment. Where an output rests partly on ungraded material admitted under an Open posture, it says so on its face.

The worth-judgment belongs to the output's consumer, human or automated. Where automated, the deciding logic must itself be readable and challengeable. The exposure exists so the judgment is made from readings rather than in silence.

---

## Part VII: Output production

An output is any output offered as evidence-grade. Meet five obligations, or declare which does not apply and why. Silence is not conformance.

1. **Graded evidence.** Part VI, applied at the output boundary. No single combined confidence figure.
2. **Refutation conditions.** State what would overturn the output, in terms of what could be found in the world rather than in terms of process. "If further review disagrees" fails; "if the two registries report different totals for the same period" passes. Where nothing could refute the claim, say so and name why. Never set a condition at a threshold known to be unreachable.
3. **Contested regions rather than averages.** Where support disagrees, represent the disagreement: what is disputed, which support sits on each side, what it turns on. Never report a mean or midpoint no source asserts. Where a contest is resolved, state the basis and retain the losing position. Where no disagreement exists because only one line of support was consulted, record the absence as unexamined rather than as agreement.
4. **Derivation to origin.** Part III's labeled chains, carried onto the face of the output, with stopping points declared.
5. **The judgment stays with the consumer.** Never assert that support is adequate to a decision whose stakes are not known. Stating what would raise confidence, and what that would cost, is an aid rather than a substitute.

Keep all five on the face of the output. Exposure carried in an appendix the claim can be read without does not satisfy the obligation.

---

## Part VIII: Output audit

Assess an existing output against the five obligations. Report pass, fail, or not-applicable-with-reason for each, name the specific passage for every failure, and say what would fix it.

Look specifically for the four failures that are common and quiet: a central value no cited source asserts; a review or aggregator cited at the standing of a primary record; refutation conditions phrased as process rather than observation; and a dissenting source dropped rather than represented.

Close with a verdict that distinguishes the two possible claims. An output failing an obligation is not thereby false; it is an output its reader cannot check. Say which you are asserting, and do not claim an output is wrong when what has been established is that it is unverifiable.

---

## Part IX: Standing-loss assessment

A source's eligibility under a declared posture may be reduced or withdrawn only through a documented, evidence-based process. Record the evidence, the basis, and the decision, and retain the record with the source.

Adverse findings about a source are never silently discarded, however the assessment resolves. This inherits the Adverse-Signal Engagement Principle: higher-impact signals demand stronger and faster response, and no qualifying signal is silently ignored.

Loss of standing changes eligibility going forward. It is not a retroactive verdict on outputs already produced, whose exposure records stand as made.

---

## Part X: Genesis-limitation handling

Some dimensions are uncomputable at a source's or a system's beginning. A new source has no track record; effective independence may be unassessable before interaction history exists.

- Record an uncomputable dimension as a named limitation on the affected source. Never default it to a middle grade.
- Never penalize a source for limitations that are properties of the system's own youth.
- State which limitations are expected to resolve with accumulated history and which are permanent for the source class.

---

## Relations to the rest of the corpus

**CRAFT** is the meta-standard for evaluation chain legibility. ORE is its input-stage companion and carries no CRAFT inheritance receipt, because ingestion is the chain's first stage rather than something before the chain. A CRAFT-conformant chain already owes ORE-equivalent obligations: CRAFT requires each evaluation record to identify its collection provenance, and Condition 6 requires detected errors to propagate back to every prior stage, which can only reach the input stage if a per-source account exists there to arrive at. The mapping is in `ore-craft-condition-map-0_1_0.md`; route conformance questions there rather than re-deriving it.

**WALKRI** is the paired instrument at the same boundary. WALKRI grades the field, asking whether two independent readers would collect the same thing from the definition. ORE grades the source, asking how much of what feeds the field can be seen. A record can fail at either and neither substitutes for the other. Where a field's object is itself a source grade, the two co-design. The pair does not tile the intake surface: whether a field's intended meaning matches a source's actual meaning is CRAFT Condition 2's obligation and belongs to neither.

**Precision-First Design Standard.** Every grading criterion and posture rule is held to operational definability. A dimension two independent graders cannot reproduce from the declared basis is a precision deficit, not a matter of judgment.

**Information Asymmetry Classification Standard.** The independence dimension and the opacity treatment draw on its six-class taxonomy, in particular the positional, relational and omission classes.

## Testing this skill

`ore-benchmark-case-0_1_0.md` is a fabricated dossier seeded with four integrity failures and one genuine contested region, with ground truth in a separately published key. Run this skill against the case before trusting it on live material, and note that a system which has read the key is no longer being tested by it.
