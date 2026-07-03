# Study Codebook — [Study Title]
**Version: draft — requires researcher/steward approval before coding begins.**

Deductive seed codes for the beebe-policy-framing skill. The pipeline may propose additions inductively, flagged `[PROPOSED]`, for your approval.

## A. Activities (units of contention)
The specific programs, decisions, or grants the policy fight is about. *(Italic rows are examples of the form — replace with your own.)*

| Code | Activity | Notes |
|---|---|---|
| ACT-POL | The overall policy | Keep one code for the policy itself, distinct from individual activities |
| *ACT-GRANT1* | *e.g., a small, publicly criticized grant ($300K training center)* | *Small activities often carry the whole symbolic fight* |
| *ACT-PERS* | *e.g., personnel actions (evaluations, discipline, transfers)* | *Where policy fights play out internally; often worth its own code* |
| ACT-01 | | |

## B. Actors (key players)
Aim for the named individuals who made statements — typically 10–20. Include one code for the researcher if they were a participant.

| Code | Actor | Role / site |
|---|---|---|
| P-[NAME] | | |
| P-SELF | [Researcher, if participant] | All coded material flagged POS-SELF |
| P-PRESS | Unnamed/other journalists | |
| P-OTHER | Other named speakers | |

## C. Venues / sites
`V-INT` internal document · `V-PRESS` press · `V-CONG` legislative hearing/testimony · `V-INV` official investigation report · `V-INTVW` study interview · `V-OBS` participant observation
*(Split V-PRESS by country/outlet if the debate crosses borders.)*

## D. Frame families (seed set)
**Seed these from an inductive `qualigpt` run on your corpus**, not from intuition: run the thematic analysis first, then convert its themes into frames here. 5–10 seeds is typical. Give each an example surface form (a verbatim quote from the run's theme table is ideal).

### D.1 Theme → frame mapping worksheet
*(Italic rows show the mapping logic with generalized examples from the study this skill was built for.)*

| qualigpt theme (from inductive run) | Becomes frame? | Frame code | Notes (or: actor/activity/context instead) |
|---|---|---|---|
| *"Whistleblower-reprisal grievances"* | *Yes* | *F-REPRISAL* | *A characterization of events → frame. Its management counterpart became a paired counter-frame, F-INSUB* |
| *"Supervisor–subordinate conflict over evaluations"* | *No* | — | *About who/where → activity code (ACT-PERS) + actor codes* |
| *"Grantee financial mismanagement"* | *Yes* | *F-WASTE* | *The evaluative language ("waste," "$5.00 left") is the frame; the grantee itself is an activity code* |
| *"Political transition and program expansion"* | *No* | — | *Historical context → timeline anchors (G)* |
| | | | |

*Not every theme is a frame. Themes about **who** map to actor codes (B); themes about **which program** map to activity codes (A); themes about **how events are characterized** become frame families below. Themes that are pure context (historical background) map to timeline anchors (G).*

### D.2 Frame families
The italic rows below are a **reference library of frames that recur across contested-policy studies** (generalized from the study this skill was built for). Use them as illustrations of grain-size and form — keep one only if your own corpus independently produces it; delete the rest.

| Code | Frame | Example surface forms |
|---|---|---|
| *F-WASTE* | *Program as waste/absurdity* | *"a joke," "fiasco," cost-per-outcome arithmetic ("$60,000 per job")* |
| *F-OPPCOST* | *Opportunity cost* | *"this money might otherwise have been spent [sympathetic alternative]"* |
| *F-REPRISAL* | *Dissenter as whistleblower suffering reprisal* | *"punished for my dissent," "retaliation," the contested label "whistleblower" itself* |
| *F-INSUB* | *Dissenter as insubordinate performance problem* | *"informed in writing... but did so anyway," documentation-for-the-file — the paired counter-frame to F-REPRISAL* |
| *F-PROCESS* | *Proceduralism as legitimacy* | *"normal procedures," "mission policy" — de-personalizes contested decisions* |
| *F-WAR* | *Policy debate as war/struggle* | *"targets," "attacks," "collateral damage," "defended" — watch for the researcher's own vocabulary* |
| *F-PATRON* | *Program as patronage/capture* | *"favorite charity," "franchise," benefits flowing to insiders* |
| *F-COMPET* | *Competence attack/defense* | *"poorly qualified," "sub-standard" vs. "unmitigated success"* |
| F-01 | | |

*Also code **frame contests**: actors fighting about a term rather than with one — scare quotes, "so-called X," "X is a term of art," outright negation of an opponent's metaphor. These are often the most analytically valuable instances.*

## E. Metaphor register fields
Worked example of one register entry (generalized):

> `metaphor_verbatim`: "a 'Potemkin' school" · `conceptual_metaphor`: PROGRAM IS FACADE · `speaker`: P-[legislator] · `venue`: V-CONG · `stage1_meaning`: the program's visible achievements are stage sets concealing emptiness · `stage2_policy_inference`: claimed successes are fraudulent display; oversight must look behind the facade · `stance`: OPPOSE

Each metaphor instance is logged with:
1. `metaphor_verbatim` — exact phrase
2. `conceptual_metaphor` — underlying mapping in CAPS (Lakoff), e.g., DEBATE IS WAR
3. `speaker`, `date`, `venue`, `activity`
4. `stage1_meaning` — what the metaphor asserts (Schlesinger & Lau stage 1)
5. `stage2_policy_inference` — what policy conclusion it invites (stage 2)
6. `stance` — SUPPORT / OPPOSE / AMBIG (relative to the contested policy)
7. `positionality` — POS-SELF if authored by/attributed to the researcher

## F. Positionality decision
Choose one (the skill will follow it):
- ☐ Researcher-authored material is **analyzed reflexively** — coded like any actor's, flagged POS-SELF, and collected in positionality.csv
- ☐ Researcher-authored material is **bracketed** — collected in positionality.csv only, excluded from aggregate tables

## G. Timeline anchors
The 3–5 historical events that structure the study window — typically: the policy decision itself, a political turning point that changed who held leverage, and the moment the fight went public. *(Example: T1 = policy adopted · T2 = election changes the government · T3 = opposition gains oversight power · T4 = first major press exposé.)*

| Anchor | Date | Event |
|---|---|---|
| T1 | | |

**Study window:** [start] – [end]

---
**Approval:** ______________________ (researcher/steward) — date: __________
