# Beebe Qualitative Skills

Two [Claude Code](https://claude.com/claude-code) skills for LLM-assisted qualitative analysis:

| Skill | What it does |
|---|---|
| [`qualigpt`](skills/qualigpt/SKILL.md) | Thematic analysis of document batches (interviews, focus groups, social media, archival documents), re-implementing the **QualiGPT** methodology (Zhang et al.) as Claude instructions. Produces a structured theme table — Theme \| Description \| Verbatim Quotes \| Source Count — plus CSV export. |
| [`beebe-policy-framing`](skills/beebe-policy-framing/SKILL.md) | Anthropological policy analysis of contested-policy corpora, based on the methodology of **Dr. James Beebe**: actor-attributed framing statements, a conceptual-metaphor register with policy-inference analysis, frame-evolution tracking, researcher-positionality flagging, and timeline output — as NVivo-importable CSVs. |

Both skills treat LLM output as **first-pass coding for a researcher to verify**, not a replacement for researcher judgment. Quotes are always verbatim; counts are real tallies; codebook extensions are proposed, never silently applied.

## How the two skills work together

They are stages of one iterative loop, not alternatives:

1. **Inductive discovery** — run `qualigpt` on the corpus (or a pilot sample). Its themes, quotes, and source tallies surface what the data actually contains.
2. **Codebook curation** — the researcher converts the inductive themes into the study codebook: recurring themes become frame families, named speakers become actor codes, contested programs become activity codes. The codebook template has a worksheet for this mapping.
3. **Deductive framing analysis** — run `beebe-policy-framing` against the approved codebook to produce attributed statements, the metaphor register, and frame-evolution tables.
4. **Feedback** — the framing run emits `[PROPOSED]` frames/actors/activities it found beyond the codebook; the researcher approves or rejects them, and the next pass (or the next batch of documents) runs against the revised codebook.

This mirrors standard qualitative practice — open coding before focused coding — and Beebe's own iterative principle that analysis begins during data collection, with each pass sharpening the instrument for the next.

## Install

Copy the skill folders into your Claude Code skills directory:

```bash
git clone https://github.com/<you>/beebe-qualitative-skills
cp -r beebe-qualitative-skills/skills/* ~/.claude/skills/
```

Then in any Claude Code session: *"run qualigpt on ./transcripts, 10 themes"* or *"run a policy-framing analysis of ./corpus using ./codebook.md"*.

The `beebe-policy-framing` skill requires a study codebook (actors, activities, frame seeds). Start from [`codebook-template.md`](skills/beebe-policy-framing/codebook-template.md).

## Attribution

### QualiGPT
The `qualigpt` skill re-implements, as model instructions, the prompt design, segmentation strategy, and output format of [QualiGPT](https://github.com/KindOPSTAR/QualiGPT) (MIT License). No QualiGPT code is used. If you use it in research, please cite the original authors:

> Zhang, H., Wu, C., Xie, J., Rubino, F., Graver, S., Kim, C., Carroll, J. M., & Cai, J. (2023). *QualiGPT: GPT as an easy-to-use tool for qualitative coding.* arXiv:2310.07061.
>
> Zhang, H., Wu, C., Xie, J., Kim, C., & Carroll, J. M. (2023). *Redefining Qualitative Analysis in the AI Era: Utilizing ChatGPT for Efficient Thematic Analysis.* arXiv:2309.10771.

### James Beebe
The `beebe-policy-framing` skill operationalizes the research design of Dr. James Beebe (1943–2024) — anthropologist, USAID Foreign Service Officer, and pioneer of rapid qualitative methods — from his unfinished study *Race, Politics, and U.S. Foreign Assistance to South Africa during the Transition to Majority Rule* (Gonzaga University, unpublished, started 2011), which applied the anthropology of public policy to a contested-policy corpus he had assembled as both participant and researcher. If you use it, please cite:

> Beebe, J. (2001). *Rapid Assessment Process: An Introduction.* Walnut Creek, CA: AltaMira Press.
>
> Beebe, J. (2014). *Rapid Qualitative Inquiry: A Field Guide to Team-Based Assessment* (2nd ed.). Lanham, MD: Rowman & Littlefield.

The skill's theoretical framework follows the sources his proposal specified:

> Wedel, J. R., Shore, C., Feldman, G., & Lathrop, S. (2005). Toward an anthropology of public policy. *The Annals of the American Academy of Political and Social Science, 600*, 30–51.
>
> Schlesinger, M., & Lau, R. R. (2000). The meaning and measure of policy metaphors. *American Political Science Review, 94*(3), 611–626.
>
> Lakoff, G., & Johnson, M. (1980). *Metaphors We Live By.* Chicago: University of Chicago Press.

This repository is maintained by Ligaya Beebe, who is completing her father's study. The skills are shared so that other researchers can put these methods to use.

## Related projects

This repo is one piece of a larger system for turning a physical archive into a coded, citable corpus:

- **[Archive Intelligence](https://github.com/1beebe/document-archivist)** — the intake pipeline. A MindStudio agent that receives scanned documents by email, extracts and cleans OCR text, generates structured metadata, and indexes everything to a Google Sheet. It feeds the corpus that these skills analyze — `qualigpt` and `beebe-policy-framing` pick up where Archive Intelligence's clean text and metadata leave off.
- **[lakoff-lens](https://github.com/1beebe/lakoff-lens)** — the first attempt. Built in January 2026, one of the first MindStudio agents Ligaya Beebe made: an AI workflow analyzing political text for sentiment and metaphorical framing, deliberately aimed at her father's methodology from the start. It took another five months of building skill to reach Archive Intelligence and, in turn, `beebe-policy-framing` — the version actually capable of running his method on his own archive.

## License

MIT — see [LICENSE](LICENSE). The QualiGPT methodology belongs to its authors; James Beebe's methodology is shared here with the intent that it be used, cited, and extended.
