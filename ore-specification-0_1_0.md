
# ORE: Origin, Reliability, Exposure

**A companion specification to CRAFT** · v0.1.0 · 2026-07-16 · CC0 1.0

*The input-stage companion to CRAFT: what an evaluation chain is allowed to assume about what enters it. Ore is what gets graded before anything is built from it.*

## Preamble

Every system that turns records into decisions has sources it did not create: the databases it imported, the attestations it accepted, the feeds it subscribed to, the documents a contributor uploaded. When something later goes wrong, the failure is usually described as bad data. But the failure almost never began as bad data. It began as unexamined confidence: the system treated a source as if its reliability were known when in fact almost nothing about it was visible. The database had no history. The attestation had five signers who were one actor. The feed was structurally sound and informationally captured. Nobody decided to trust these things; the absence of a grading discipline decided silently, and by the time the failure surfaced, every downstream judgment had inherited it.

This specification exists so that the confidence a system places in its sources is a recorded, inspectable decision instead of a silent default. It does not tell you which sources are good. It tells you what an honest account of a source must contain, and what your system is obligated to do differently when that account is thin.

## 1. Purpose and scope

This specification specifies the structural conditions for grading data sources at the ingestion boundary of any system that evaluates, attests, or decides on the basis of ingested records: evaluation chains, evidence engines, knowledge commons, attribution systems, grant programs, and ledgers.

It specifies what a conformant grading must account for, record, and expose. It does not specify how any dimension is computed. Instruments that compute effective independence, read behavioral residue, or resolve identity are implementations; a system may keep their mechanics private without impairing conformance, because conformance is judged from what the system declares, exposes, and records: the exposure and posture obligations are assessable from public declarations and outputs alone, and the recording obligations are assessable in audit, where the records this specification requires are produced. This is the legibility principle inherited from CRAFT: any party with relevant knowledge can determine, from the published declarations alone, what the system claims about its sources and what would constitute evidence that a claim is wrong.

## 2. The core reframe: grades measure uncertainty, not quality

A source grade is an uncertainty measurement, not a quality verdict. The dimensions in this specification do not answer "how good is this source." They answer "how much of this source's reliability can currently be seen, and what is being trusted that cannot be seen."

This distinction is normative, not rhetorical. A conformant system:

- MUST use grades to calibrate weight, monitoring intensity, and eligible downstream use;
- MUST NOT present a grade as a judgment of the source's worth, and MUST NOT use a low grade as grounds for rejection where the posture declared under Section 6 admits the source;
- MUST distinguish "ungraded" from "low-grade" as different states with different obligations. A source about which little is verifiable is not a bad source; it is a source carrying more uncertainty, and the system's response is calibrated weight and monitoring, not verdict.

A quality verdict issued without pre-specified criteria is an impressionistic claim in CRAFT's sense: possibly accurate, structurally unfalsifiable. This specification exists to replace that verdict with a measurement. The operational difference is what keeps the distinction from being rhetorical: a grade is revisable by accumulated evidence and carries a monitoring obligation; a verdict is terminal. A system whose grades never update and never trigger monitoring is issuing verdicts under another name.

## 3. The grading dimensions

A conformant grading accounts for each source on the dimensions below. For each dimension the grading MUST record the assessment, the basis on which it was made, and any sub-assessment that could not be computed (recorded as a named flag, never as a silent default or an assumed middle value).

### 3.1 Provenance integrity

Did this input come from where it claims, and did it arrive unchanged? This dimension is binary-adjacent: the evidence of origin and tamper-evidence either holds or it does not. High provenance integrity guarantees origin; it does not guarantee that the originating party had accurate information. A grading MUST NOT let strength on this dimension stand in for strength on any other.

### 3.2 Epistemic soundness

Is the source's output structured so that truth-evaluation by independent parties is possible? This is a structural property of claim formation: are claims stated in terms reality can refute, are accuracy and relevance kept separate, does the source distinguish what it observed from what it inferred. A source can be perfectly sincere and epistemically unsound; its outputs then resist independent evaluation regardless of intent.

### 3.3 Confirmation architecture

When this source produced its output, what confirmed it? The internal confirmation structure of the source's own process affects the weight its outputs can carry. Four structurally distinct cases:

| | Single-party | Multi-party |
| --- | --- | --- |
| **Trustless** | Cryptographic proof from one attester: origin is guaranteed, the underlying claim confirmed by no one | Mechanism-required confirmation (multisig, validator set, passed vote): the strongest case, subject to the opacity limit below |
| **Trust-based** | One evaluator, curator, or badgeholder: social provenance, no independent check on content | Adversarial or consensus confirmation built into the mechanism (bonded curation with challengers, multi-reviewer processes) |

Two boundary states complete the taxonomy. An unconfirmed source (no cryptographic proof and no confirming party: the raw uploaded document, the bare feed) occupies none of the four cells and is recorded as unconfirmed, the state carrying the highest confirmation uncertainty. And a source may carry more than one confirmation mode at once: a cryptographically signed output authored by a single evaluator has trustless origin and trust-based content. A conformant grading records each mode present rather than forcing one cell.

**The party-count limit.** Party count is visible; independence is not. N signatures do not show whether N independent perspectives confirmed anything: keys can be held by one actor, signers can be affiliated, referencers can share one information source, a challenge can be brought by a party affiliated with the challenged. A conformant grading MUST NOT operationalize confirmation architecture by party count alone. Where effective independence cannot be assessed, the grading records that as a named flag on this dimension. How a system assesses effective independence is implementation; that it must not substitute count for independence is the requirement.

### 3.4 Declared extension dimensions

Two further dimensions are named as confirmed candidates. A conformant system MAY grade on them and, where it does, MUST declare the basis; where it does not, it MUST declare their absence.

**Track record.** Has this source's history of outputs surviving challenge accumulated evidence about its reliability? This is a temporal dimension neither structural dimension captures. It is uncomputable for new sources; see Section 7.

**Independence.** Does the source have a stake in how the attested events are recorded? A structurally sound source can be informationally captured, with all of its information flowing from parties interested in the outcome. This dimension addresses conflict of interest; epistemic soundness addresses claim structure; both are required for the full picture. Adversarial resistance (does the source's challenge mechanism function under pressure, or merely exist) is treated as a sub-case of track record until adoption evidence argues otherwise.

## 4. Opacity

Some sources will not disclose their internal architecture. The specification's commitment: opacity raises uncertainty; it does not constitute a verdict. Under adversarial conditions, intentional obscurity and legitimate privacy are externally identical at the moment of ingestion, so a conformant system:

- MUST admit or decline opaque sources according to its declared posture, never according to an unrecorded judgment about why the source is opaque;
- MUST enter an admitted opaque source at the grade its visible properties warrant, with a monitoring obligation attached;
- MUST NOT treat a disclosure requirement as resolving opacity, since an actor who knows the requirements can engineer conformance while obscuring what matters. Monitoring a source's behavior over time is the stronger response; its mechanics are implementation.

## 5. Grade exposure on outputs

Grading that stops at the ingestion boundary is bookkeeping. The obligation that gives grading force:

- Every output that rests on ingested material (a finding, an attestation, a published entry, a funding decision) MUST expose the grade profile of the sources it rests on, at minimum the lowest-graded and any flagged sources in its support;
- No output may silently launder ungraded or flagged material into a downstream judgment. Where an output rests partly on ungraded material admitted under an open posture (Section 6), the output says so on its face.

The worth-judgment about whether that support suffices belongs to the person reading the output, and the exposure exists so that judgment is possible.

## 6. Intake postures

Systems legitimately differ in when grading happens and in what ungraded material may touch. This specification names three postures. A conformant system MUST declare its posture, MAY declare different postures per source class, and MUST enforce the declared posture's downstream condition. A posture declaration MUST state its treatment of opaque sources: which classes are admitted at the grades their visible properties warrant, and which, if any, are declined, declared in advance rather than decided per source.

**Screened.** Nothing enters without being graded first. The ingestion boundary is the review boundary. Appropriate where every record may carry decision weight and volume is low enough for eyes at entry. What a Screened intake declines is declared in advance as scope and posture (source classes, opacity treatment), never as a grade verdict. Downstream condition: all held material is graded; outputs expose grades per Section 5.

**Graded.** Everything admitted enters immediately at the grade its visible properties warrant, and review effort is prioritized by uncertainty: the thinnest accounts get eyes first. Appropriate where volume exceeds entry-review capacity but decisions draw continuously on the store. Downstream condition: outputs may rest on any graded material and expose the profile; flagged dimensions travel with the record.

**Open.** Bulk material enters ungraded into a quarantined state. Ungraded material MAY serve discovery, search, and lead generation; it MUST NOT support findings, attestations, or decisions until graded. Appropriate for corpus migration and exploratory ingestion, where the value of having the material inside the system precedes the capacity to grade it. Downstream condition: the quarantine boundary is structural, not procedural; an output cannot cite quarantined material as support.

Movement between postures is expected and legitimate: a system may open for a migration and screen for a case. What conformance requires is that the posture in force for any admitted record is recorded with it, so that no record's grading history is ambiguous later.

## 7. Genesis limitations

Some dimensions are uncomputable at a system's or a source's beginning: a new source has no track record; effective independence may be unassessable before interaction history exists. A conformant grading:

- MUST record an uncomputable dimension as a named limitation on the affected source, never defaulting it to a middle grade;
- MUST NOT penalize a source for limitations that are properties of the system's own youth;
- SHOULD state which limitations are expected to resolve with accumulated history and which are permanent for the source class.

## 8. Conformance

A system conforms to this specification when: (1) it declares its intake posture(s) and enforces the corresponding downstream conditions; (2) every admitted source carries a grading on the Section 3 dimensions, with uncomputable sub-assessments recorded as named flags; (3) every output exposes the grade profile of its support per Section 5; and (4) no grade is presented or used as a worth-verdict on a source. The posture and exposure obligations are assessable from declarations and outputs alone; the grading and recording obligations are assessable in audit against the records this specification requires. No obligation requires access to implementation mechanics.

## 9. Inheritance

This specification is independently adoptable and inherits by reference:

- **CRAFT (Chains Reveal Attested Falsifiable Truth):** This document is the input-stage companion. CRAFT addresses the problem class it names chain of evaluation legibility, specifying the chain from world to decision, and names the input stage as one failure class among several; this specification elaborates that class. ORE is not a CRAFT domain application and carries no CRAFT inheritance receipt or attestation. A chain builder addresses the input-stage failure class CRAFT names by adopting this specification or by meeting equivalent declared obligations.
- **WALKRI:** the paired instrument at the same boundary. WALKRI grades the field (would two independent readers collect the same thing from the definition?); this specification grades the source (how much of what feeds the field can be seen?). A record can fail at either, and neither grading substitutes for the other.
- **Precision-First Design Standard:** every grading criterion and posture rule in a conformant system is held to operational definability; a dimension whose assessment two independent graders cannot reproduce from the declared basis is a precision deficit.
- **Information Asymmetry Classification Standard:** the independence dimension and the Section 4 opacity treatment draw on its six-class taxonomy of structural informational advantage, in particular the positional, relational, and omission classes.

## 10. Related realization: bonded-challenge curation

One existing mechanism family deserves naming because it realizes, in public and by construction, the dimensions this specification can otherwise only require declarations about: the decentralized curation framework of Ferit Tunçer ("Decentralized Curation: Trustless Transformation of Information into Knowledge," v1.0.4, CC BY 4.0, [doi:10.5281/zenodo.20546399](https://doi.org/10.5281/zenodo.20546399)), with the Truth Post protocol as its worked instantiation.

In that design, claims are published under bond, challenged under counter-stake, and adjudicated by external decentralized dispute resolution. Its outputs sit in this specification's strongest social quadrant: trust-based multi-party confirmation with adversarial confirmation built into the mechanism. (The framework describes itself as trustless; this specification's axis classifies the confirmation of content, not the framework, and the divergence is terminological.) More specifically, it functions as a native instrument for the track-record extension dimension of Section 3.4, with adversarial resistance, that dimension's sub-case, exercised rather than claimed, since the challenge mechanism is the mechanism. Track record is manufactured continuously: every item carries an operational state and an adjudication outcome, and the framework's "confidence as bond-time" measure (accumulated capital risk exposure over time, explicitly not a truth label) is a quantified uncertainty-reduction instrument in exactly this specification's sense.

Three of the framework's commitments converge independently with this specification's own. Its quality-dimension separation (accuracy as global and binary, relevance as local and scalar, with distinct mechanisms per dimension and an explicit refusal to compress quality into one signal) parallels the Section 3 requirement that no dimension stand in for another. Its adjudication vocabulary distinguishes an unchallenged claim from one that survived a challenge, which parallels the Section 2 distinction between ungraded and graded: an analogy rather than an identity, since a source can be graded without having survived any challenge. And its own equilibrium analysis names challenger entry as its most fragile condition, which this specification's terms make legible as a flag: an "unchallenged" state in a pool where few challengers are entering is closer to ungraded than to surviving, and a conformant grading drawing on such a mechanism records that.

The boundary is equally clean: bonded public challenge operates where falsifying evidence is feasible, cheap, and publicly disclosable without harm beyond the verdict it delivers. Where any of those fail, Section 4's opacity and monitoring path continues coverage. The two are complements: the open-posture specialist and the posture-general discipline.
