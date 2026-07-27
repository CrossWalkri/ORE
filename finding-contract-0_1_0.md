
# The Finding Contract

**A companion specification to ORE and CRAFT** · v0.1.0 · 2026-07-27 · CC0 1.0

*ORE governs what a system may assume about what enters it. This specifies what a system owes on the way out: the obligations any evidence-grade finding carries on its face.*

## Preamble

A finding is the point where accumulated material becomes something a person acts on. Everything before it is process; everything after it is consequence. That makes the finding the last place an honest account can be attached and the first place its absence starts costing something.

The failure this specification addresses is not fabrication. It is the finding that is entirely accurate and structurally unusable: it states a conclusion without stating what would overturn it, averages away the disagreement its own sources contained, cites a secondary source as though it were an origin, and arrives with a confidence that the reader cannot audit because the basis of that confidence was never written down. Such a finding cannot be checked, so it cannot be corrected, so the only available responses are acceptance and rejection, both of them uninformed.

This specification states what a finding must carry so that a reader can do something other than take it or leave it. It specifies obligations, not implementations. It binds no one to any tool, format, or vocabulary, and a finding produced entirely by hand can satisfy it as fully as one produced by a pipeline.

## 1. Purpose and scope

This specification applies to any output offered as evidence-grade: a research finding, an evaluation verdict, a due-diligence conclusion, an analytic product, a recommendation to a decision-maker, or a machine-generated answer presented as resting on retrieved material.

It does not apply to outputs that do not claim evidential standing. An opinion, a summary presented as a summary, or an exploratory note is not bound by this specification, and mislabeling such an output as evidence-grade to attract the standing while avoiding the obligations is the failure the scope boundary exists to name.

A finding conforms when it carries the five obligations of Sections 2 through 6. Conformance is assessable from the finding itself, without access to the process that produced it. This is the legibility principle inherited from CRAFT: a reader with relevant knowledge can determine from the published finding alone what it claims and what would constitute evidence that the claim is wrong.

## 2. Graded evidence

A finding MUST expose the grade profile of its material support, as ORE Section 5 requires of any output resting on ingested material: for each grading dimension, the weakest assessment present anywhere in that support, together with every flag any source in it carries.

- Where the finding rests on ungraded material admitted under an Open posture, it MUST say so on its face, and MUST NOT cite quarantined material as support.
- Where separately admitted sources in the support cannot be shown distinct in effective origin, the finding MUST carry the joint-support flag. Separately admitted is not independently originated.
- A finding MUST NOT present a single combined confidence figure in place of the per-dimension profile. The refusal to combine is inherited from ORE Section 2 and for the same reason: a single number is easy to tune and hard to audit, and the environment this specification assumes contains parties with an interest in how the tuning goes.

A finding whose support is thin is not thereby a weak finding. It is a finding whose reader can see what is being trusted. That is the whole of what this obligation buys, and it is enough.

## 3. Refutation conditions

A finding MUST state what would overturn it: the observation, measurement, disclosure, or counter-evidence whose appearance would require the finding to be withdrawn or revised, specified in terms concrete enough that a reader could recognize the refuting thing on encountering it.

- The conditions MUST be stated in terms of what could be found in the world, not in terms of internal process. "If further review disagrees" is not a refutation condition; "if the two registries report different totals for the same period" is.
- A finding that cannot state any refutation condition MUST say so explicitly and name why: the claim may be definitional, the domain may not yet admit the relevant observation, or the finding may be impressionistic in CRAFT's sense. Declaring unfalsifiability is conformant. Presenting an unfalsifiable claim in falsifiable dress is not.
- Refutation conditions MUST NOT be set at a threshold the producer knows to be unreachable. A condition specified so that no available instrument could ever satisfy it is a refusal to be checked, written as an invitation.

The obligation is not that a finding be refutable in principle by someone with unlimited resources. It is that the reader be told, in advance and in the producer's own words, what the producer would accept as being wrong.

## 4. Contested regions rather than averages

Where the material supporting a finding disagrees, the finding MUST represent the disagreement rather than resolving it into a central value.

- The finding MUST name the region of contest: what is disputed, which support sits on each side, and what the disagreement turns on where that is visible.
- The finding MUST NOT report a mean, median, midpoint, or consensus figure that no source asserts and that conceals the spread it was computed from. Where a central value is genuinely informative it MAY be reported alongside the contest, never in place of it.
- Where the producer resolves a contest, the finding MUST state the basis of the resolution and MUST retain the losing position in the record. A resolution whose reasoning is not stated is a preference, and a losing position silently dropped cannot be revisited when new evidence arrives.
- Where disagreement is absent because only one line of support was consulted, the finding MUST record the absence of contest as an unexamined state rather than as agreement. Uncontested and confirmed are different, for the same reason ORE Section 2 distinguishes ungraded from low-grade.

The reason for this obligation is asymmetric cost. An average across a genuine disagreement produces a number that is precise, defensible, and about nothing, and its precision is what makes it durable: it survives into every downstream use, carrying none of the doubt that produced it.

## 5. Derivation chains to ultimate origin

A finding MUST trace its support to ultimate origins, with every intermediate rung labeled for what it actually is.

- Each rung MUST be identified by its own role: originating observation, primary record, aggregator, secondary reporting, review, restatement. A source that restates another is labeled as restating it, with the restated source named.
- Where a chain cannot be walked to origin, the finding MUST record where the walk stopped and why: the origin is unpublished, the aggregator does not disclose its inputs, the trail terminates in an unattributed claim. A truncated chain honestly labeled is conformant; a chain presented as reaching origin when it stops at an aggregator is not.
- A finding MUST NOT present a rung at a standing higher than it holds. Citing a review as though it were the study, or an aggregator as though it were the registry, is the ordinary form of this failure and it is usually inadvertent.
- Where two apparently distinct chains converge on the same origin, the finding MUST record the convergence. This is the derivation-side form of ORE Section 5's joint-support flag, and it is the specific failure that makes corroboration counts untrustworthy: chains that share an origin agree because they must.

## 6. The worth-judgment stays with the consumer

A finding MUST leave the judgment of sufficiency to the party consuming it, and MUST carry on its face what that party needs to make it.

- The finding MUST NOT assert that its support is adequate to any particular decision. It reports what the support is; whether that suffices depends on what is being decided and what the consequences of being wrong would be, neither of which the producer generally knows.
- Where the finding is addressed to a decision whose stakes the producer does know, it MAY state what it would take to raise confidence and what that would cost, which is an aid to the judgment rather than a substitute for it.
- Where the consumer is automated, the obligation is unchanged: the decision logic that composes findings into an action MUST itself be readable and challengeable, so that the judgment is made from the readings rather than in silence.
- A finding MUST NOT be structured so that the exposure required by Sections 2 through 5 is separated from the claim: material carried in an appendix that the claim can be read without is not on the face of the finding.

## 7. Conformance

A finding conforms when it carries all five obligations, or explicitly declares and justifies the absence of any that does not apply. The declaration is itself conformant behavior; silence is not.

Conformance is assessable from the finding alone. No obligation requires access to the producing process, the tools used, or any implementation. A conformance assessment answers five questions: is the support graded and exposed per dimension, are refutation conditions stated in world terms, is disagreement represented rather than averaged, is every rung labeled for what it is with stopping points declared, and is the sufficiency judgment left to the consumer with what they need to make it present on the face.

A finding that fails any of the five is not thereby false. It is a finding whose reader cannot check it, which is a different and more durable problem.

## 8. Inheritance

This specification is independently adoptable and inherits by reference:

- **ORE (Origin, Reliability, Exposure):** Section 2 of this document is ORE Section 5's exposure obligation applied at the finding boundary, and the refusal to combine grades into a single figure is ORE Section 2's, adopted for the same adversarial reason. ORE governs the ingestion boundary; this governs the output boundary; a system operating both has an account of its material at entry and an account of what rests on it at exit.
- **CRAFT (Chains Reveal Attested Falsifiable Truth):** the legibility principle and the notion of an impressionistic claim are CRAFT's. Section 3's refutation obligation is the finding-level realization of what CRAFT requires of an evaluation chain, and Section 5's labeled rungs serve CRAFT Condition 6's requirement that detected errors propagate back to every prior stage, which is only possible where the stages are named.
- **WALKRI:** where a finding reports values collected through defined fields, the reproducibility of those fields is WALKRI's obligation and is not discharged by anything here. A finding built on labels rather than instruments satisfies this specification and remains unreliable, and neither specification substitutes for the other.
- **Precision-First Design Standard:** every obligation stated here is held to operational definability. A refutation condition that two independent readers cannot assess the same way from its wording is a precision deficit in the finding, not a matter of taste.
- **Adverse-Signal Engagement Principle Core Standard:** Section 4's requirement that a losing position be retained rather than dropped is the no-silent-discard obligation, applied to the internal disagreements of a finding rather than to signals about a source.

## 9. Self-application

This specification rests on a small and interested support. Its five obligations were derived from failures observed in one author's evaluation practice across seven funding rounds, which is originating observation by a party with maximal stake in how the categories are recorded, unconfirmed by any independent party. The specifications it inherits from are published and versioned, and their conformance is presently self-attested. No independent implementation existed at publication.

The refutation conditions for this specification: a finding satisfying all five obligations that a competent reader still cannot check would show the set is incomplete; an obligation that implementers consistently satisfy in form while defeating in substance would show it is specified at the wrong level; and a domain where representing contest rather than averaging demonstrably degrades decisions would bound Section 4's scope. None of these has been tested.

## Changelog

v0.1.0 (2026-07-27): Initial publication. Five obligations, drawn from the artifact named in the Regen Web3 Toolkit contribution one-pager of 2026-07-18.
