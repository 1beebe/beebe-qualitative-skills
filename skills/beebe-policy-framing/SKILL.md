---
name: beebe-policy-framing
description: Run anthropological policy-framing analysis on a corpus of contested-policy documents (memos, press, hearings, correspondence). Use when the user asks for framing analysis, metaphor analysis, actor-attributed qualitative coding, anthropology of public policy, or Beebe policy analysis. Produces linked CSVs — actor-attributed statements, a conceptual-metaphor register, frame evolution, positionality flags, and a timeline — suitable for NVivo import.
---

# Beebe Policy-Framing Analysis

This skill operationalizes the research methodology of Dr. James Beebe (*Rapid Assessment Process*, 2001; *Rapid Qualitative Inquiry*, 2014) as designed in his study of contested policy debates: an **anthropology of public policy** (Wedel, Shore, Feldman & Lathrop 2005) combining **policy-metaphor analysis** (Schlesinger & Lau 2000), **conceptual metaphor theory** (Lakoff & Johnson 1980), and a **social constructionist** stance. Its premise: in policy struggles, *language is the weapon* — the analysis tracks who frames what, with which metaphors, to invite which policy conclusions.

## Requirements

**A study codebook is required before coding.** It defines the actors, activities, venues, frame seeds, and timeline anchors (see `codebook-template.md` in this skill's folder). If the user has no codebook, draft one from their research design and corpus, then get their explicit approval before coding. Never code against an unapproved codebook.

## Core principles

1. **The field is multi-sited** (Wedel et al.): treat internal documents, press, hearings, investigation reports, and interviews as distinct venues; code the venue of every item. Actors have varying institutional leverage across sites.
2. **Metaphors are conceptual, not decorative** (Lakoff): beneath each surface phrase, code the underlying mapping in CAPS (e.g., DEBATE IS WAR, PROGRAM IS FACADE, EXCLUSION IS FREEZING).
3. **Metaphors are analyzed in stages** (Schlesinger & Lau): stage 1 — what does the metaphor assert about its target? stage 2 — what policy conclusion does it invite the audience to accept?
4. **Every statement is attributed**: named speaker, role, date, venue. The unit of analysis is the framing act, not the aggregate theme.
5. **Positionality is data**: if the researcher (or their close associates) authored corpus documents, those passages are flagged, collected for reflexive review, and — per the researcher's decision — either analyzed like any actor's or bracketed. Watch for the researcher's own analytic vocabulary; reflexivity extends to it.
6. **Social construction means both sides**: code opposing frames of the same events symmetrically. The analysis succeeds only if each side would recognize itself as fairly rendered.
7. **Frame contestation is a first-class finding**: note when actors fight *about* a metaphor (quoting, negating, or qualifying an opponent's term — "so-called X," scare quotes) rather than *with* one.

## Outputs

Produce five linked CSVs plus a report, in an output folder next to the corpus:

1. **statements.csv** — `statement_id | speaker (actor code) | role | date | venue code | verbatim statement | activity code | stance | positionality flag | source_doc`
2. **metaphors.csv** — `metaphor_verbatim | conceptual_metaphor | speaker | date | venue | activity | stage1_meaning | stage2_policy_inference | stance | positionality`
3. **frames.csv** — `frame code | frame | supporting actors | opposing actors | representative quotes | first/last observed | change over time`
4. **positionality.csv** — every researcher-authored/attributed passage, verbatim, with a reflexive note
5. **timeline.csv** — `date | event/document | actors | frames active | anchor` aligned to the codebook's anchor events
6. **run report (.md)** — principal findings, frame contests, corrections to prior runs, and a **gap report**: what the corpus cannot show and which acquisitions would fill it

## Rules

- Quotes verbatim, including errors (mark `[sic]` only in the report, never inside the quote).
- New frames, actors, or activities not in the codebook are emitted flagged `[PROPOSED]` — never silently extend the codebook; the researcher (or study steward) approves.
- Stance is coded relative to the contested policy; statements about adjacent conflicts are AMBIG unless the speaker links them to the policy fight (and whether they do so is itself a datum).
- On repeat runs over a growing corpus, reconcile: dedupe documents, correct earlier coding, and note corrections explicitly in the run report.
- All outputs are first-pass coding for the researcher to verify against sources; researcher judgment carries the analysis.

## Citations

If this skill contributes to published research, cite: Beebe (2001, 2014); Wedel, Shore, Feldman & Lathrop (2005); Schlesinger & Lau (2000); Lakoff & Johnson (1980). See the repository README for full references.
