# CLAUDE.md — Working doctrine for this repository

This repo is an Open Dossier: a living research publication. These rules
are non-negotiable and apply to every session.

## Before any commit
- Run `python verification/verify_numbers.py`. If any check fails,
  fix the manuscript or the model — NEVER widen a tolerance to pass.
- If a change alters any number in the paper, the corresponding check
  in verify_numbers.py AND the JS port in index.html must be updated
  to match. All three must agree.

## Verification labels are sacred
- Every claim's status in claim_ledger.csv must be true. Claims nobody
  verified are labeled OPEN-UNVERIFIED, never asserted.
- Manuscript language must match ledger status: unverified claims say
  "is expected to" or "we conjecture", never "yields" or "is".
- **OPEN-CAVEATED** — a claim that is established, but only under an explicitly
  stated restriction. The gap is one of verification WORK, not truth: the
  result holds within its stated scope, and closing the caveat (extending the
  derivation, computing the general case) is bounded work that could be done.
  NOT for claims whose truth hinges on a contingent external fact that may or
  may not hold — those are OPEN-UNVERIFIED. The test: can the gap be closed by
  doing more verification work? → OPEN-CAVEATED; does the claim instead depend
  on a fact that must be true but isn't established? → OPEN-UNVERIFIED. Unlike
  OPEN-UNVERIFIED, an OPEN-CAVEATED claim IS verified within its scope (true,
  with a caveat), not merely unverified; unlike EXPLORATORY-CONJECTURE, it
  asserts a truth value (within scope) rather than none. Worked example: a
  result proven only for the Gaussian case is OPEN-CAVEATED (the general case
  is more verification work); a result that holds only assuming the measured
  range is accurate is OPEN-UNVERIFIED (it hinges on a contingent fact — the
  measurement — that has not been verified).
- **EXPLORATORY-CONJECTURE** — deliberately speculative material for gedanken
  experiments and idea exploration. Asserts NO truth value. Admissible only if
  it (a) states its premise — the explicit "if"; (b) predicts a distinct,
  measurable signature that would distinguish it from the alternatives; and
  (c) names its cost — the conservation law or principle it strains, the energy
  density or exotic ingredient it implies, and what it cannot explain. A
  conjecture that predicts nothing and costs nothing is cut. Quarantine rule:
  exploratory-conjecture material lives ONLY in a clearly-labeled exploratory
  section — never in the abstract, the main results, or the claim ledger except
  as a row explicitly tagged EXPLORATORY-CONJECTURE, and it may never be used as
  a premise for a claim of any higher verification status. It is a sandbox with
  walls, not a loophole.
- **REPORTED — NON-SCIENTIFIC SOURCE, UNCORROBORATED** (provenance label — rarely
  used; included for completeness. Applies mainly to dossiers investigating
  phenomena where non-scientific reports are part of the landscape; most dossiers
  will never need it.) A reported observation or claim recorded in the dossier for
  completeness or to flag a question worth investigating, originating from a source
  that does not meet evidentiary standards — no published methodology, no raw or
  instrumented data, no independent corroboration, no peer review (e.g.
  entertainment media, anecdote, social media). It asserts no truth value and is
  explicitly NOT the author's claim. This label sits on a different axis from the
  others. The verification ladder (verified → OPEN-CAVEATED → OPEN-UNVERIFIED →
  EXPLORATORY-CONJECTURE) measures how well-backed a claim the author is making or
  exploring. This label measures provenance — where a reported item came from — for
  material the author records but does not adopt. It is a tag on origin, not a rung
  on the ladder.
  Admissibility requirements (all mandatory): (1) The source is named explicitly
  and its non-scientific nature stated plainly. (2) Mundane-explanation wall: where
  an ordinary candidate explanation exists, it must be stated with at least equal
  prominence to the reported anomaly. Where no ordinary explanation is known, that
  absence must itself be stated ("no ordinary explanation has been identified") —
  never left as an implied void, because an unexplained-by-omission report reads as
  significance it has not earned. Recording an anomaly while suppressing its
  plausible ordinary explanation is inadmissible one-sided framing. (3) Premise wall
  (inherited from EXPLORATORY-CONJECTURE, in full): it may never serve as a premise
  for any higher-status claim, never enters the abstract or main results, and lives
  only in a clearly-walled "reported anomalies" register, visibly separated from the
  physics. Its function is to inform which questions to ask; it gets no vote on any
  claim's verification status.
  Boundaries: vs. CITE — CITE means a real, evidentiary source supports the claim.
  This means the source explicitly does not meet that bar; the non-evidentiary
  provenance is the whole point. vs. OPEN-UNVERIFIED — OPEN-UNVERIFIED is the
  author's own asserted claim, merely unchecked. This is someone else's reported
  claim from a non-evidentiary source — a provenance problem, not an
  unfinished-verification one. vs. EXPLORATORY-CONJECTURE — conjecture is a
  structured physics hypothesis (premise / predicted signature / named cost). This
  is a raw reported observation with no such structure; it makes no hypothesis at
  all.
  Worked example: A recurring EM signal reported only on a television program →
  REPORTED — NON-SCIENTIFIC SOURCE, UNCORROBORATED, with the source named, its
  non-scientific nature stated, and the mundane candidate (e.g. uncharacterized RF
  interference, or that no instrumented measurement exists to assess it) stated
  alongside with equal prominence.

## Releases vs commits
- Plain commits: site edits, typo fixes, doc improvements. Push freely.
- Releases (git tags): substantive milestones only. A release triggers
  automatic Zenodo DOI archiving and OpenTimestamps blockchain anchoring.
  Do not create releases without the author's explicit instruction.
- NEVER modify anything in timestamps/ — those are cryptographic proofs.

## File map
- index.html        — interactive edition (sliders + verification console)
- paper.html        — self-explaining edition (term/citation expansions)
- dossier.html      — audit trail (red team, citation audit)
- paper/            — LaTeX manuscript + PDF
- verification/     — verify script, audits, red-team report, format spec
- claim_ledger.csv  — every claim, typed, with honest status

## Standing context
- **Open claims:** None formally entered yet — to be built during prior-art
  recon. Anticipated structure: the ESTABLISHED bucket (demonstrated qubit
  counts, coherence times, gate/readout fidelities, error-correction
  milestones, peer-reviewed results from named groups, with their exact
  measurement conditions) will be asserted with citations; the comparative and
  predictive claims — which modality reaches fault tolerance first, the
  probability of success per avenue/material, and the most promising candidate
  — will be the central OPEN-UNVERIFIED claims, posted as forecasts with
  explicit reasoning and the evidence that would settle them.
- **Open red-team findings:** None yet — adversarial pass comes after the first
  draft.
- **Anything a fresh session must know:**
  - **Framing discipline (critical):** This topic is routinely over-hyped, so
    the format's credibility depends on labeling with total precision. State
    demonstrated lab results plainly as ESTABLISHED with sources and their
    exact conditions — qubit count, fidelity, and crucially whether the result
    is a logical or physical qubit — that is bedrock, not speculation, and
    soft-pedaling a real milestone into "alleged" is a mistake. But every
    probability estimate, timeline, and "winner" call stays in the OPEN bucket,
    hedged, framed as a forecast — that is what makes the dossier undismissable
    rather than mockable. Truth in labeling cuts BOTH ways: never downgrade a
    genuinely demonstrated result, and never assert a forecast as settled. That
    symmetry IS the credibility.
  - **Vendor material:** roadmaps, press releases, and "quantum advantage"
    announcements are claims by interested parties, not established results
    until independently reproduced or peer-reviewed. Label them as such and
    flag them.
  - **Forecast labeling:** every "probability of success" or "most promising"
    judgment is an OPEN forecast — give the reasoning, a base rate or
    comparable where possible, and the falsifiable signpost that would raise or
    lower it (e.g. a logical qubit sustained below error rate X over Y cycles,
    or a demonstrated below-threshold surface-code patch at scale Z).
  - **Model to emulate:** bullish in analysis, conservative in labeling —
    believe boldly about where the field is heading, but publish each claim
    with a label a hostile referee cannot attack. Restraint as a weapon, not as
    timidity.
  - **Key prior work to map in recon:** peer-reviewed milestones and roadmaps
    across modalities — superconducting (IBM, Google), trapped-ion (Quantinuum,
    IonQ), neutral-atom (QuEra, Pasqal, Atom Computing), photonic (PsiQuantum,
    Xanadu), topological (Microsoft), silicon spin (Intel and academic groups);
    error-correction results (surface code, recent logical-qubit
    demonstrations); and benchmarking standards (quantum volume, randomized
    benchmarking, the threshold theorem). Distinguish physical vs logical qubits
    everywhere — conflating them is the most common way this topic gets
    misreported. Treat marketing-driven or unsourced claims as adjacent-at-best
    and flag them.
  - **The boldest claims and their labels:** "modality X has the highest
    probability of reaching fault-tolerant, useful-scale QC" and any specific
    timeline → OPEN-UNVERIFIED, posted as a forecast with stated assumptions and
    falsifiable signposts. The publishable, defensible spine is the honest
    separation of what has been demonstrated from what is being predicted.
