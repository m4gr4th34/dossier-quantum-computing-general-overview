---
title: "Prior-Art Reconnaissance — The Quantum Computing Landscape"
subtitle: "Dossier QC-Landscape · Phase 0 working map (pre-release draft)"
author: "Irfan Ali-Khan — Independent Researcher"
date: "16 June 2026"
---

> **STATUS: Phase 0 prior-art reconnaissance — a working map, not laddered claims.**
> Nothing here is asserted as a verified result of this dossier. Every entry is
> tagged by evidence tier (ESTABLISHED / ADJACENT / OPEN). Demonstrated,
> peer-reviewed results are stated plainly with sources; vendor roadmaps,
> announcements, and contested claims are flagged as such; comparative and
> predictive judgements are held in the OPEN bucket as forecasts. These rows
> still need a per-claim human reality-check before any of them enters the
> formal claim ledger, `verify_numbers.py`, or the manuscript. *The one rule:
> every label is true.*

## How to read this map

One distinction governs everything below, because it is the single most common
way this topic gets misreported:

- **Physical vs logical qubits.** A raw qubit count is not an error-corrected
  (logical) qubit count. We state which is which everywhere.
- **Demonstrated vs roadmap.** A measured, published result is a different kind
  of object from a company's projection of where it will be in 2029. Both
  appear here; only the first is ESTABLISHED.
- **Peer-reviewed vs interested-party.** A Nature paper and a press release are
  not the same evidence tier. Vendor and aggregator claims are flagged.

Evidence tiers used here:

- **ESTABLISHED** — demonstrated on hardware, with a peer-reviewed or otherwise
  primary source. Asserted plainly.
- **ADJACENT** — announced, roadmapped, or contested; an interested party's
  claim not yet independently reproduced, or a result the community disputes.
- **OPEN** — a comparative or predictive judgement (probability of success,
  "who wins," timelines). Held as a forecast with a falsifiable signpost; never
  asserted as settled.

---

## The landscape, avenue by avenue

### Superconducting (Google, IBM, Rigetti, IQM)

- **Best demonstrated:** Google's Willow processor (105 physical qubits) showed
  *below-threshold* error correction — the logical error rate falls as the code
  distance grows (d=3 to d=5 to d=7), reaching roughly 0.14% logical error per
  cycle at d=7 with real-time decoding (peer-reviewed, late 2024). IBM's Condor
  reached 1,121 physical qubits in 2023 before IBM pivoted to smaller,
  higher-quality, modular chips (Heron, Nighthawk).
- **Strength:** most mature at scale; fast gates; the clearest public access
  ladder and roadmap (IBM).
- **Weakness:** surface-code overhead (hundreds-to-thousands of physical qubits
  per logical qubit); cryogenic; chip-to-chip interconnect is the scaling
  frontier.
- **Maturity:** highest. The reference platform the others are measured against.

### Trapped ion (Quantinuum, IonQ — IonQ now includes Oxford Ionics)

- **Best demonstrated:** Quantinuum's Helios — 98 physical barium ions at
  ~99.92% two-qubit fidelity across all pairs, yielding 48 error-corrected
  logical qubits at roughly a 2:1 physical-to-logical ratio (Nov 2025). Oxford
  Ionics / IonQ have reported the highest gate fidelities of any platform
  (two-qubit ~99.99%, single-qubit error around the 10^-7 level).
- **Strength:** highest fidelities and longest coherence of any modality; the
  best (lowest) encoding ratio on the logical-qubit leaderboard.
- **Weakness:** slower gate speeds; laser/optics complexity has been the
  historic scaling bottleneck (the problem the microwave-gate and ions-on-chip
  approaches are trying to solve).
- **Maturity:** high on quality; scaling to large qubit numbers is the open
  question.

### Neutral atom (QuEra, Pasqal, Atom Computing)

- **Best demonstrated:** QuEra reported 96 logical qubits from 448 physical
  atoms with below-threshold error suppression (peer-reviewed, Jan 2026) — the
  current logical-qubit count leader. Atom Computing crossed 1,000 physical
  atoms in 2023; Pasqal has operated ~1,000-atom systems.
- **Strength:** traps are cheap; atoms are identical by physics (no
  device-to-device variability); connectivity is reconfigurable in software
  rather than fixed by lithography.
- **Weakness:** a younger control/gate stack; gate speed and fidelity still
  maturing relative to ions.
- **Maturity:** rising fast; strongest recent logical-qubit results.

### Silicon spin (Intel, Diraq, Silicon Quantum Computing, Quantum Motion, Equal1)

- **Best demonstrated:** Diraq + imec showed >99% two-qubit fidelity for
  silicon spin qubits built on a standard 300mm CMOS foundry line — and,
  notably, across multiple randomly selected dies, not one hero device
  (peer-reviewed, Sept 2025). Silicon Quantum Computing reported ~99.99%
  two-qubit fidelity (peer-reviewed, Dec 2025).
- **Strength:** smallest physical footprint; rides the existing semiconductor
  manufacturing base, giving (in principle) the cheapest path to millions of
  qubits.
- **Weakness:** lowest qubit counts today; no logical-qubit demonstration yet
  on this modality.
- **Maturity:** earliest on integration, but the manufacturing-scale argument
  is the strongest of any avenue if the counts come.

### Photonic (PsiQuantum, Xanadu, Quandela)

- **Best demonstrated:** Xanadu's Aurora — a 12-qubit modular, networked,
  room-temperature photonic machine built from 35 chips and ~13 km of fiber
  (peer-reviewed, Jan 2025) — plus on-chip generation of error-resistant GKP
  states (peer-reviewed, June 2025).
- **Strength:** room-temperature operation; networking and modularity are
  native; rides silicon-photonics fabrication.
- **Weakness:** **optical loss** is the make-or-break bottleneck; many gates are
  inherently probabilistic, demanding heavy redundancy.
- **Maturity:** key building blocks shown; the loss problem stands between the
  blocks and a useful machine.

### Topological (Microsoft) — CONTESTED

- **Claim:** Majorana 1 (Feb 2025), presented as 8 topological qubits and a
  hardware path toward a million-qubit chip.
- **Status — ADJACENT / contested:** the accompanying Nature paper's reviewers
  explicitly noted the results do not constitute evidence for Majorana zero
  modes, and independent physicists at the 2025 APS meeting were largely
  unconvinced the device demonstrates a topological qubit. A follow-up
  (Majorana 2) reports longer lifetimes but leaves the central physics question
  open.
- **If real:** intrinsic, hardware-level error protection — a potentially
  decisive scaling advantage. That payoff is exactly why it is worth pursuing,
  and exactly why the bar for "demonstrated" must stay high.
- **Maturity:** a genuine materials-science bet whose foundational claim is not
  yet accepted.

### Annealing (D-Wave) — a distinct, non-gate avenue

- **Status:** D-Wave's Advantage2 annealers are in commercial optimization use
  today; annealing is not universal/gate-based computing. D-Wave has now
  announced a separate gate-model roadmap (initial small system in 2026; a
  target of 100 logical qubits by 2032) — that gate-model line is early and
  roadmap-stage.
- **Note:** keep annealing clearly separated from the gate-based
  fault-tolerance race; it answers a different question.

### Sub-threads worth a flag (not top-level rows here)

- **Cat / bosonic qubits (Alice & Bob):** hardware-level bit-flip protection,
  with reported bit-flip lifetimes exceeding one hour — a distinct
  error-correction strategy that can sit under superconducting hardware.
- **NV-center / diamond, and Rydberg-specific variants:** real but treated as
  sub-threads pending your call on whether any deserves its own row.

---

## The three buckets (summary)

### ESTABLISHED (demonstrated; mostly peer-reviewed)

1. Below-threshold error correction now exists on real hardware in at least
   three modalities — superconducting (Google Willow), neutral-atom (QuEra),
   and trapped-ion (Quantinuum Helios). It is no longer only theory.
2. Trapped ions hold the fidelity lead; silicon spin has now matched ~99.99%
   two-qubit fidelity *and* shown it on an industrial foundry line across
   non-cherry-picked dies.
3. High-rate codes (color codes, qLDPC) have driven the physical-to-logical
   ratio down to ~2:1 on ion and atom hardware, versus hundreds-to-one for the
   surface code — a demonstrated overhead reduction.
4. Neutral-atom and superconducting platforms operate at 1,000+ physical qubits
   in real systems; photonics has shown a room-temperature modular networked
   prototype.

### ADJACENT (announced / roadmap / contested — interested-party until reproduced)

1. Every "fault tolerance by year X" roadmap: IBM (large-scale FT ~2029), IonQ
   (an accelerated roadmap citing thousands of logical qubits by the late
   2020s), Pasqal / QuEra / Atom logical-qubit ladders, D-Wave's gate-model
   100-logical-by-2032. All are vendor projections.
2. Microsoft's topological qubit (Majorana 1 / 2): a real materials bet whose
   foundational claim the community disputes.
3. Single-vendor "quantum advantage" / utility benchmarks not yet independently
   reproduced.

### OPEN (the dossier's core forecasts — to be posted as challenges)

1. Which modality reaches fault-tolerant, useful-scale QC first.
2. The probability of success per avenue/material.
3. The "most promising candidate" call.
4. The timeline to a cryptographically-relevant or industrially-useful machine.

Each OPEN item, when entered in the ledger, carries a forecast label, the
explicit reasoning and a base rate or comparable where possible, and a
falsifiable signpost — for example: a logical qubit sustained below a stated
error rate over a stated number of cycles; a below-threshold surface-code patch
at a stated scale; or a photonic system demonstrating loss below the
fault-tolerance threshold.

---

## Candidate OPEN forecasts to seed the ledger (draft — needs sign-off)

These are *not yet* ledger rows. They are the predictive claims this dossier
will make, each to be labeled OPEN-UNVERIFIED with a signpost:

- **QC-F1** — "No single modality has yet secured the path to fault-tolerant,
  useful-scale QC; the leaders by distinct metric are trapped-ion (fidelity,
  encoding ratio), neutral-atom (logical-qubit count), and superconducting
  (scale, maturity)." (Forecast; signpost: first sustained, reproduced
  logical-qubit advantage on a useful problem.)
- **QC-F2** — Per-avenue probability-of-success estimates (to be built with
  stated assumptions). (Forecast; signposts per avenue.)
- **QC-F3** — "Silicon spin has the strongest manufacturing-scale argument but
  the furthest to go on logical qubits." (Forecast; signpost: first
  logical-qubit demonstration on silicon spin at a stated fidelity.)
- **QC-F4** — "Microsoft's topological route remains unproven at the level of
  the qubit itself." (Currently ADJACENT/contested; signpost: independent
  reproduction of a topological qubit with accepted Majorana evidence.)

---

## Reality-check questions for the author

1. **Aggregator-sourced numbers.** Several figures (some fidelity records,
   logical-qubit counts, roadmap dates) trace to industry-news aggregators that
   often restate vendor PR. The Nature-anchored ones (Willow, QuEra 96,
   Diraq/imec, Xanadu, SQC) are firmer. Any you know to be misreported?
2. **The probability call.** The safe framing is "no clear winner yet," but this
   dossier deliberately wants a probability-of-success call per avenue. Do you
   have a prior on which avenue you lean toward, so the strongest forecast is
   built there?
3. **Missing avenues.** Should cat/bosonic, NV-center/diamond, or any Rydberg
   variant be promoted to a top-level row?
4. **Materials axis.** You flagged materials specifically (silicon-28
   enrichment; barium vs ytterbium ions; InAs/Al for topological;
   lithium-niobate vs silicon-nitride photonics). Develop "materials" as its own
   axis, or fold it into each modality?

---

## Sources consulted (Phase 0; to be re-verified at citation-audit stage)

Peer-reviewed / primary:

- Silicon spin, 300mm foundry, >99% fidelity — *Nature* (2025):
  <https://www.nature.com/articles/s41586-025-09531-9>
- Diraq/imec milestone announcement — Diraq newsroom (Sept 2025):
  <https://diraq.com/newsdesk/imec-technology-lights-the-path-to-utility-scale-for-diraq-s-quantum-chips>
- Xanadu Aurora (modular networked photonic) — Xanadu / *Nature* (Jan 2025):
  <https://www.xanadu.ai/press/xanadu-introduces-aurora-worlds-first-scalable-networked-and-modular-quantum-computer>
- Xanadu on-chip GKP states — The Quantum Insider (June 2025):
  <https://thequantuminsider.com/2025/06/05/xanadu-demonstrates-scalable-building-block-for-photonic-quantum-computers/>
- Microsoft topological-qubit skepticism — APS *Physics* (2025):
  <https://link.aps.org/doi/10.1103/Physics.18.68> ; *Science* (2025):
  <https://www.science.org/content/article/debate-erupts-around-microsoft-s-blockbuster-quantum-computing-claims>

Industry news / vendor (flagged — restate vendor or aggregator claims):

- Superconducting / Willow below-threshold, roadmaps — Network World (2025):
  <https://www.networkworld.com/article/4088709/top-quantum-breakthroughs-of-2025.html>
- Trapped-ion state of play (2026) — The Quantum Insider:
  <https://thequantuminsider.com/2026/06/12/trapped-ion-quantum-computing-companies-technology-and-where-it-stands-in-2026/>
- Trapped-ion fidelity / Helios detail — PostQuantum:
  <https://postquantum.com/quantum-modalities/trapped-ion-qubits/>
- Neutral-atom companies / QuEra 96 logical — Quantum Zeitgeist:
  <https://quantumzeitgeist.com/top-neutral-atom-quantum-computing-companies/>
- Pasqal roadmap — Pasqal newsroom (2026):
  <https://www.pasqal.com/newsroom/pasqal-releases-2025-roadmap/>
- IBM roadmap detail — PostQuantum:
  <https://postquantum.com/quantum-computing-companies/ibm/>
- Silicon-spin companies (2026) — Quantum Zeitgeist:
  <https://quantumzeitgeist.com/top-silicon-spin-quantum-computing-companies/>
- D-Wave gate-model roadmap (June 2026) — Business Wire:
  <https://www.businesswire.com/news/home/20260601444734/en/>
- Quantum error correction / logical-qubit leaderboard overview — Quantum
  Zeitgeist: <https://quantumzeitgeist.com/what-is-quantum-error-correction/>
- "What quantum computer to buy?" buyer-guide preprint (roadmap synthesis):
  <https://arxiv.org/pdf/2604.04761>

---

*Open Dossier format · Phase 0 working draft · committed as a plain commit (no
release, no DOI, no timestamp) · CC BY 4.0 (prose). This document supersedes
nothing and asserts nothing as verified; it is the input to the claim ledger.*
