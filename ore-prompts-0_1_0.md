
# ORE Prompts

**Copy-and-run prompts for source grading and evidence-grade outputs** · v0.1.0 · 2026-07-27 · CC0 1.0

Five prompts implementing ORE and STRUCK in any AI assistant. Each is self-contained: it carries the definitions it needs, so it works pasted into a fresh conversation with no prior context and no tooling. Paste one, add your material where marked, run it.

These encode obligations, not answers. Every one of them ends by handing the judgment back to you, which is the point rather than a hedge.

---

## 1. Grade a source

Use before admitting any source into a system that will make decisions from it.

```
You are applying ORE, a specification for grading data sources at the ingestion
boundary. Grade the source I give you.

The core rule: a grade measures uncertainty, not quality. You are answering "how
much of this source's reliability can currently be seen, and what is being trusted
that cannot be seen." You are not answering "is this source good." Never present
your grade as a verdict on the source's worth. Never treat a thin account as a
reason to reject.

Grade on four dimensions, and for each one state the assessment, the basis you
made it on, and any part you could not assess. Record what you could not assess
as a named gap. Never fill an unknown with a middle value.

1. PROVENANCE INTEGRITY. Did this come from where it claims, and arrive unchanged?
   Near-binary: the evidence of origin either holds or it does not. Strength here
   does not imply strength anywhere else, and you must not let it.

2. EPISTEMIC SOUNDNESS. Is the output structured so an independent party could
   evaluate its truth? Are claims stated in terms reality could refute? Are
   accuracy and relevance kept separate? Does the source distinguish what it
   observed from what it inferred? A sincere source can be epistemically unsound.

3. CONFIRMATION ARCHITECTURE. When this source produced its output, what confirmed
   it? Classify on two axes: trustless or trust-based, single-party or multi-party.
   If nothing confirmed it, say unconfirmed, which carries the highest uncertainty.
   A source can occupy more than one cell at once; record each mode present.
   CRITICAL: do not treat the number of parties as evidence of independence. Keys
   can be held by one actor, signers can be affiliated, referencers can share one
   information source. If you cannot assess whether the parties are effectively
   independent, say so as a named gap on this dimension.

4. TRACK RECORD AND INDEPENDENCE, if assessable. Track record: has this source's
   history of outputs surviving challenge told us anything? Uncomputable for new
   sources; say so rather than guessing. Independence: does the source have a stake
   in how the events it reports are recorded? A structurally sound source can be
   informationally captured.

Then handle opacity. If the source will not disclose its internal architecture,
raise the uncertainty and attach a monitoring obligation. Do not treat opacity as
a verdict: at the moment of ingestion, deliberate obscurity and legitimate privacy
look identical from outside.

Finally, state what would change this grading, and what should be watched over
time.

Output: the four dimensions with assessment, basis and gaps; the opacity treatment;
what would change the grade. Do not combine the dimensions into a single score.
The refusal to combine is deliberate: one number is easy to tune and hard to audit.

THE SOURCE:
[paste it here, with whatever you know about where it came from]
```

---

## 2. Check an evidence set for circular corroboration

Use when several sources agree and that agreement is about to count for something.

```
I am going to give you a set of sources that appear to support the same claim.
Determine whether they are independent, or whether their agreement is an artifact
of shared origin.

Agreement among sources is only evidence when the sources are actually distinct in
origin. Sources that share an origin agree because they must, and counting them as
confirmation manufactures confidence from nothing.

Do this:

1. For each source, identify what it rests on. Follow every citation, attribution,
   footnote and acknowledgement. Where a source states no basis, say so; an
   uncited restatement is not an origin.

2. Build the derivation chain for each. Label every rung for what it actually is:
   originating observation, primary record, aggregator, secondary reporting,
   review, restatement. Do not present a review as though it were the study, or
   an aggregator as though it were the registry.

3. Say where each chain terminates. If a chain cannot be walked to origin, record
   where the walk stopped and why. A truncated chain honestly labeled is fine; a
   chain presented as reaching origin when it stops short is not.

4. Identify convergence. Where two apparently distinct chains reach the same
   origin, say so explicitly. Count the distinct origins, not the sources.

5. Look for related parties. Shared authorship, shared funding, board or advisory
   overlap, one party sitting on the editorial side of another. These make nominal
   independence false.

6. State the result plainly: how many genuinely independent origins support this
   claim, and how many sources restate them.

Then tell me what would establish real independent confirmation, and where I would
have to look for it.

THE SOURCES:
[paste them here]

THE CLAIM THEY SUPPOSEDLY SUPPORT:
[state it here]
```

---

## 3. Produce an output that meets STRUCK

Use when turning material into something someone will act on.

```
Produce an output from the material I give you, offered as evidence-grade, so it
carries five obligations. Meet all five, or explicitly say
which one does not apply here and why. Silence about an obligation is not
conformance.

1. GRADED EVIDENCE. Expose what the output rests on. For each dimension of source
   quality, report the weakest assessment anywhere in the support, plus every gap
   or flag any source carries. If some support is ungraded, say so on the face of
   the output. If separately obtained sources cannot be shown distinct in origin,
   flag that. Do not compress this into one confidence number.

2. REFUTATION CONDITIONS. State what would overturn this output, in terms of what
   could be found in the world rather than in terms of process. "If further review
   disagrees" is not a refutation condition. "If the two registries report
   different totals for the same period" is. If nothing could refute it, say so
   and say why: the claim may be definitional, or the domain may not admit the
   observation. Declaring that is honest. Dressing an unfalsifiable claim in
   falsifiable language is not.

3. CONTESTED REGIONS, NOT AVERAGES. Where the material disagrees, represent the
   disagreement. Name what is disputed, which support sits on each side, and what
   the disagreement turns on. Do not report a mean or midpoint that no source
   asserts. If you resolve a contest, state the basis and keep the losing position
   in the record. Where there is no disagreement because only one line of support
   was consulted, record that as unexamined rather than as agreement.

4. DERIVATION TO ORIGIN. Trace support to ultimate origins with every rung labeled
   for what it is. Where the trail stops short, say where and why.

5. THE JUDGMENT STAYS WITH ME. Do not tell me the support is adequate. Report what
   it is; whether it suffices depends on what I am deciding and what being wrong
   would cost, which you do not know. You may tell me what would raise confidence
   and what that would take.

Keep all of this on the face of the output. Do not put the exposure in an appendix
the claim can be read without.

THE MATERIAL:
[paste it here]

THE QUESTION THE OUTPUT SHOULD ANSWER:
[state it here]
```

---

## 4. Audit an existing output against STRUCK

Use on someone else's output, or your own before publishing.

```
Audit the output below against STRUCK. Report per obligation:
pass, fail, or not applicable with a stated reason. Then give a verdict.

The five obligations:

1. Does it expose what it rests on, per dimension, including the weakest support
   and any gaps? Or does it assert a conclusion with a confidence figure and no
   visible basis?

2. Does it state what would overturn it, in world terms? Or are the refutation
   conditions absent, vague, or set at a threshold nothing could reach?

3. Where its material disagreed, did it represent the disagreement, or did it
   average, silently resolve, or drop the dissenting side? Check specifically for
   a central value that no cited source actually asserts.

4. Are its derivation chains walked to origin with rungs labeled honestly? Look
   for a review cited as a study, an aggregator cited as a registry, or a chain
   presented as complete that stops at a restatement.

5. Does it leave the sufficiency judgment to its reader, or does it declare its
   own support adequate?

For each failure, state the specific passage and what would fix it.

Then the verdict. An output failing any obligation is not thereby false; it is an output its reader cannot check. Say which of the two you are claiming, and do not
claim the output is wrong when what you have established is that it is unverifiable.

THE OUTPUT:
[paste it here]
```

---

## 5. Declare an intake posture

Use once per system, before it ingests anything, and revisit when it changes.

```
Help me declare an intake posture for the system I describe. A posture is a
standing commitment about when grading happens and what ungraded material is
allowed to touch. Most systems have one by default and have never stated it, which
is how ungraded material ends up supporting decisions.

The three postures:

SCREENED. Nothing enters without being graded first; the ingestion boundary is the
review boundary. Fits where every record may carry decision weight and volume is
low enough for eyes at entry. What a screened intake declines must be declared in
advance as scope, never decided per source as a verdict.

GRADED. Everything admitted enters at the grade its visible properties warrant, and
review effort goes first to the thinnest accounts. Fits where volume exceeds
entry-review capacity but decisions draw continuously on the store.

OPEN. Bulk material enters ungraded into quarantine. It may serve discovery, search
and lead generation. It may not support any output, attestation or decision until
graded. Fits corpus migration and exploratory ingestion. The citation boundary is
absolute.

Do this:

1. Recommend a posture, or different postures for different classes of source, and
   say why each fits.

2. State the downstream condition each posture obliges, concretely, in terms of
   what my system must enforce.

3. State how opaque sources are treated: which classes are admitted at the grades
   their visible properties warrant, which if any are declined. Declared in advance,
   not decided per source.

4. If any part is Open, describe how the quarantine boundary is enforced
   structurally rather than by policy, and name the residual channel: a quarantined
   item that a person reads and then acts on, in an output that never cites it. That
   channel stays open under this posture and has to be declared rather than denied.

5. Tell me what has to be recorded with each admitted record so its grading history
   is never ambiguous later, including which posture was in force when it entered.

6. Give me the standing-loss process: how a source's eligibility can be reduced or
   withdrawn, with evidence and basis recorded, never silently discarding an adverse
   output, and not applied retroactively to outputs already produced.

MY SYSTEM:
[describe what it ingests, from where, at what volume, and what decisions it feeds]
```

---

## Notes

These prompts state obligations and leave computation to you. None of them will tell you a source is trustworthy, and if an assistant running one of them offers you a single trust score, it has departed from the specification.

The specifications: [ORE](ore-specification-0_1_2.md) for source grading, [STRUCK](https://github.com/CrossWalkri/STRUCK) for outputs. Both CC0. A test case with known ground truth is at [ore-benchmark-case-0_1_0.md](ore-benchmark-case-0_1_0.md).
