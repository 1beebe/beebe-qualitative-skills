---
name: qualigpt
description: Run QualiGPT-style qualitative thematic analysis on a batch of documents (interviews, focus groups, social media posts, or archival documents). Use when the user asks for thematic analysis, qualitative coding, theme identification, or "run qualigpt" on transcripts or documents. Produces a structured theme table (Theme | Description | Quotes | Source Count) plus CSV export.
---

# QualiGPT: LLM-Assisted Qualitative Thematic Analysis

This skill replicates the methodology of QualiGPT (Zhang et al., https://github.com/KindOPSTAR/QualiGPT — cite arXiv:2310.07061 and arXiv:2309.10771), a tool for LLM-assisted thematic analysis of qualitative data. The original tool sends structured prompts to an LLM; here, Claude performs the analysis directly using the same prompt structure, segmentation strategy, and output format.

## Methodology overview

QualiGPT automates the *coding* step of qualitative analysis: identifying key themes in a dataset, describing them, and grounding each theme in verbatim quotes with a count of how many participants/sources support it. It follows this pipeline:

1. **Ingest** data (.docx, .xlsx, .csv, .txt). For tabular data, expect a header row like `Speaker | Content`.
2. **Specify dataset type** — interview, focus group, or social media posts (extend to "archival documents" for document corpora). The prompt wording adapts to the type.
3. **Specify number of themes** N (QualiGPT default: 10, range 1–20). Ask the user or default to 10.
4. **Choose coding mode**: inductive (themes emerge from data — default) or deductive (user supplies a codebook; themes must map to it).
5. **Segment** if the corpus exceeds the context that can be carefully analyzed in one pass (original: ~3,800 tokens per segment, split on sentence boundaries, never mid-sentence). Analyze each segment separately.
6. **Consolidate**: if multiple segments were analyzed, merge all segment-level theme tables and re-analyze the merged responses to produce one final consolidated theme table (deduplicate overlapping themes, re-tally counts).
7. **Export** results as .csv (parse the pipe-delimited table) and a human-readable report.

## Analysis prompt (apply this to each segment)

Act as an experienced qualitative researcher. Apply this instruction pattern, adapted from QualiGPT verbatim:

> You need to analyze a dataset of {interviews | a focus group | Social Media Posts | archival documents}. Please identify the top {N} key themes from the data and organize the results in a structured table. The table must have exactly 4 columns: **Theme**, **Description**, **Quotes**, and **Participant Count** (for documents: **Source Count** — number of distinct documents supporting the theme). Use `|` to separate columns, include a header separator row `|---|---|---|---|`, and end the table with a line of `**********` before and after so it can be parsed.

Rules for faithful application:
- **Quotes must be verbatim** from the source text — never paraphrase inside the Quotes column. Include 1–3 short representative quotes per theme, each attributed to its source document/speaker.
- **Counts must be real tallies** — count the distinct participants/sources that evidence the theme; do not estimate.
- Themes should be distinct (minimal overlap), descriptive, and ranked roughly by prevalence.
- For deductive coding, only use themes from the user's codebook; note codebook themes with no supporting data.

## Batch workflow for multiple files

1. Convert every file to plain text (e.g., `textutil -convert txt` for .docx on macOS; pandas for .xlsx/.csv). Keep a file → source ID mapping.
2. Read every document in full. Prepend each document's text with a source marker like `[SOURCE: doc_id]` so quotes can be attributed.
3. If the total corpus is small enough to analyze carefully in one pass (roughly < 8,000 words), analyze the whole corpus at once. Otherwise segment per the rules above, analyze each segment, then run the consolidation pass.
4. Produce three deliverables in an output folder next to the source files (e.g., `qualigpt_output/`):
   - `themes.csv` — the final theme table parsed into CSV (columns: Theme, Description, Quotes, Source Count, Source IDs)
   - `analysis_report.md` — the formatted theme table plus a short narrative summary, methodology note, and per-document inventory
   - `raw_response.txt` — the full pipe-delimited table(s) with `**********` markers, mirroring QualiGPT's raw output format
5. Report the top themes to the user in chat with the table.

## Limitations to disclose

Per the QualiGPT paper: LLM-assisted coding is a first-pass aid, not a replacement for researcher judgment. Recommend the researcher (a) verify quotes against sources, (b) review theme boundaries, and (c) treat counts as approximate guides for salience. Note any documents that contributed little signal (e.g., forms, boilerplate). If documents duplicate one another, flag it — duplicates inflate source counts.
