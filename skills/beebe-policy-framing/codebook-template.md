# Study Codebook — [Study Title]
**Version: draft — requires researcher/steward approval before coding begins.**

Deductive seed codes for the beebe-policy-framing skill. The pipeline may propose additions inductively, flagged `[PROPOSED]`, for your approval.

*All italic rows in this template are **fictional worked examples** from an invented case — a contested city streetcar project — included to show grain-size and form. Replace them with codes surfaced from your own corpus.*

## A. Activities (units of contention)
The specific programs, decisions, or grants the policy fight is about.

| Code | Activity | Notes |
|---|---|---|
| ACT-POL | The overall policy | Keep one code for the policy itself, distinct from individual activities |
| *ACT-LINE* | *The downtown streetcar line ($48M)* | *Small, visible activities often carry the whole symbolic fight* |
| *ACT-EIR* | *The environmental review process* | *Procedural steps can become units of contention in their own right* |
| ACT-01 | | |

## B. Actors (key players)
Aim for the named individuals who made statements — typically 10–20. Include one code for the researcher if they were a participant.

| Code | Actor | Role / site |
|---|---|---|
| P-[NAME] | | |
| *P-DIR* | *Transit authority director* | *Agency* |
| *P-CM3* | *Council member, District 3 (leading opponent)* | *Legislature* |
| P-SELF | [Researcher, if participant] | All coded material flagged POS-SELF |
| P-PRESS | Unnamed/other journalists | |
| P-OTHER | Other named speakers | |

## C. Venues / sites
`V-INT` internal document · `V-PRESS` press · `V-CONG` legislative hearing/testimony · `V-INV` official investigation report · `V-INTVW` study interview · `V-OBS` participant observation
*(Split V-PRESS by country/outlet if the debate crosses borders.)*

## D. Frame families (seed set)
**Seed these from an inductive `qualigpt` run on your corpus**, not from intuition: run the thematic analysis first, then convert its themes into frames here. 5–10 seeds is typical. Give each an example surface form (a verbatim quote from the run's theme table is ideal).

### D.1 Theme → frame mapping worksheet
*(Italic rows show the mapping logic, using the fictional streetcar case.)*

| qualigpt theme (from inductive run) | Becomes frame? | Frame code | Notes (or: actor/activity/context instead) |
|---|---|---|---|
| *"Characterizations of the project as wasteful spending"* | *Yes* | *F-BOONDOGGLE* | *A characterization of events → frame. Its defender counterpart became a paired counter-frame, F-INVEST* |
| *"Conflict between the transit director and District 3 council member"* | *No* | — | *About who/where → actor codes (B) + possibly an activity code* |
| *"Disputes over ridership projections"* | *Yes* | *F-COOKED* | *The evaluative language ("cooked numbers," "fantasy forecasts") is the frame; the forecast documents are sources, not codes* |
| *"Regional growth and the light-rail referendum backstory"* | *No* | — | *Historical context → timeline anchors (G)* |
| | | | |

*Not every theme is a frame. Themes about **who** map to actor codes (B); themes about **which program** map to activity codes (A); themes about **how events are characterized** become frame families below. Themes that are pure context (historical background) map to timeline anchors (G).*

### D.2 Frame families
*(Fictional examples — replace with frames your own corpus produces.)*

| Code | Frame | Example surface forms |
|---|---|---|
| *F-BOONDOGGLE* | *Project as waste/absurdity* | *"boondoggle," "a train to nowhere," cost-per-rider arithmetic ("$12,000 per daily rider")* |
| *F-INVEST* | *Project as investment in the future* | *"world-class city," "you don't judge a sapling by its shade" — the paired counter-frame: the same cost overruns coded as growing pains* |
| *F-COOKED* | *Official numbers as fabrication* | *"cooked numbers," "fantasy forecasts," scare quotes around "projections"* |
| *F-CAPTURE* | *Project as insider patronage* | *"the developer's pet project," "gravy train," benefits flowing to connected firms* |
| *F-PROCESS* | *Proceduralism as legitimacy* | *"the review followed every required step," "public comment was taken" — de-personalizes contested decisions* |
| *F-STEAMROLL* | *Decision-making as force majeure* | *"rammed through," "steamrolled the neighborhood," "done deal before the first hearing"* |
| F-01 | | |

*Also code **frame contests**: actors fighting about a term rather than with one — scare quotes, "so-called X," redefining an opponent's word ("that's not a subsidy, it's an investment"), or outright negation of an opponent's metaphor. These are often the most analytically valuable instances.*

## E. Metaphor register fields
Worked example of one register entry (fictional):

> `metaphor_verbatim`: "a train to nowhere" · `conceptual_metaphor`: PROJECT IS JOURNEY WITHOUT DESTINATION · `speaker`: P-CM3 · `venue`: V-PRESS · `stage1_meaning`: the project moves and consumes fuel (money) but arrives at no benefit · `stage2_policy_inference`: continued funding is motion without purpose; cancel it · `stance`: OPPOSE

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

*Either way, reflexivity extends to the researcher's own analytic vocabulary — if you find yourself describing the debate as a "battle" or a "circus," that choice belongs in the register too.*

## G. Timeline anchors
The 3–5 historical events that structure the study window. *(Fictional example: T1 = referendum approves the line · T2 = election flips the council majority · T3 = auditor's report released · T4 = first front-page exposé.)*

| Anchor | Date | Event |
|---|---|---|
| T1 | | |

**Study window:** [start] – [end]

---
**Approval:** ______________________ (researcher/steward) — date: __________
