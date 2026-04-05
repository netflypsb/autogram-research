# AI Research Reliability: Cross-Platform Comparative Analysis

## Overview

This repository contains a comparative study evaluating the **reliability of AI agents in performing research data analysis**. Three AI agents on two different platforms independently analysed the same research dataset, and their outputs were compared against programmatically verified ground truth to assess accuracy, comprehensiveness, and overall reliability.

## Research Question

> How reliable are different AI models and platforms for performing scientific research data analysis? Does the choice of model, platform (harness), or both systematically affect the quality and accuracy of the analysis?

## The Three Analyses Compared

| Property | Analysis A | Analysis B | Analysis C |
|----------|-----------|-----------|-----------|
| **AI Model** | Phoenix | Qwen3.6 Plus | Claude Opus 4.6 Thinking |
| **Platform** | Windsurf IDE | Solaris-cowork | Windsurf IDE |
| **Location** | `../autogram-research-draft/` | `../autogram-research-draft-02/` | `../final/autogram-schedule-FINAL/` |
| **Output format** | Markdown (6 files) | Markdown + LaTeX + PNG (7 files + 4 figures) | Markdown (3 files) |
| **Prior context** | None (first analysis) | None (independent) | Access to both prior analyses |

## Key Findings

### 1. Quantitative Reliability Varies Dramatically

| Agent | Word Count Claim | Actual (Verified) | Error Factor |
|-------|-----------------|-------------------|--------------|
| Phoenix / Windsurf | ~63,000–84,000 words | 8,037 words | **8–10× inflation** |
| Qwen / Solaris | Avoided per-note word counts | 8,037 words | N/A (avoidance) |
| Claude / Windsurf | 8,037 words | 8,037 words | **1.0× (exact)** |

### 2. Qualitative Reliability Is High and Consistent

All three agents independently identified the same core findings:
- Progressive deepening pattern across cycles
- Domain expansion from 3 → 29 categories
- Novel idea generation absent from community discussions
- Meta-cognitive capabilities and paradigm shift in final note
- **14/17 qualitative claims had unanimous agreement (82%)**

### 3. Model Selection > Platform Selection

| Comparison | Quality Gap | Interpretation |
|-----------|------------|----------------|
| Same platform, different models (A vs C) | **1.6 points** | Model matters most |
| Different platforms, capable models (B vs C) | **0.0 points** | Platform matters less |

### 4. Overall Reliability Scores (1–5 scale)

| Dimension | A (Phoenix/Windsurf) | B (Qwen/Solaris) | C (Claude/Windsurf) |
|-----------|---------------------|------------------|---------------------|
| Quantitative accuracy | 2 | 3 | **5** |
| Qualitative accuracy | 4 | **5** | 4 |
| Comprehensiveness | 4 | **5** | 4 |
| Methodological rigor | 2 | 4 | **5** |
| Publication readiness | 2 | **5** | 4 |
| **Overall mean** | **2.8** | **4.4** | **4.4** |

## Practical Guidelines for AI-Assisted Research

1. **Qualitative findings are reliable** across models and platforms — use AI for pattern identification
2. **Quantitative claims require verification** — never trust word counts, statistics, or measurements without programmatic confirmation
3. **Model selection matters more than platform** — invest in model evaluation, not just tooling
4. **Avoidance > confident errors** — models that decline to guess are preferable to models that fabricate
5. **Verification tools must be actively used** — having code execution available doesn't help if the model doesn't use it
6. **Multiple independent analyses increase confidence** — cross-check qualitative findings across agents

## Repository Contents

```
ai-research-reliability/
├── README.md                          # This file
├── main-paper.md                      # Full comparative analysis paper
└── supplementary-comparison-data.md   # Detailed comparison tables and data
```

## Document Descriptions

### main-paper.md
Full research paper (~5,000 words) covering:
- **Introduction** — Background, study design, research questions, contributions
- **Methods** — Ground truth verification, analysis configurations, evaluation framework
- **Results** — Quantitative accuracy, qualitative accuracy, comprehensiveness, methodological rigor, publication readiness, overall scores
- **Discussion** — Model vs platform effects, verification gap, avoidance strategy, qualitative convergence, error taxonomy, platform design implications, practical guidelines, limitations
- **Conclusion** — Five key findings on AI research reliability

### supplementary-comparison-data.md
Comprehensive supporting data:
- **A.** Scoring framework definitions (5 dimensions, 1–5 scale with anchors)
- **B.** Detailed error inventory (15 errors in A, 6 in B, 5 in C)
- **C.** File-by-file output comparison
- **D.** Full claim verification table (word counts, structural claims, GitHub metrics, byte sizes)
- **E.** Hypothesis for word count inflation (systematic ~1.5 bytes/word estimation error)
- **F.** Unique contributions by each analysis
- **G.** Qualitative agreement matrix (82% unanimous, 100% majority agreement)

## Source Data

The source dataset analysed by all three agents:
- `../artifacts/rocket-launcher/` — Progression notes 002–006
- `../INDEX.md` — Master tracking document
- `../research/# Scheduled Task.txt` — Agent prompt
- `../research/# Chat Thread.txt` — Telegram reports
- `../autogram.md` — Autogram platform description

The three analyses compared:
- `../autogram-research-draft/` — Analysis A (Phoenix / Windsurf IDE)
- `../autogram-research-draft-02/` — Analysis B (Qwen3.6 Plus / Solaris-cowork)
- `../final/autogram-schedule-FINAL/` — Analysis C (Claude Opus 4.6 Thinking / Windsurf IDE)

## Ground Truth Verification

All quantitative ground truth was verified programmatically:
```powershell
# Word counts
foreach ($f in Get-ChildItem "artifacts\rocket-launcher\*.md") {
    $wc = (Get-Content $f.FullName | Measure-Object -Word).Words
    Write-Output "$($f.Name): $wc words"
}

# Results:
# progression-note-002.md: 1290 words
# progression-note-003.md: 669 words
# progression-note-004.md: 1382 words
# progression-note-005.md: 1995 words
# progression-note-006.md: 2701 words
# Total: 8,037 words
```

## Target Publication Venues

1. **Nature Machine Intelligence** — AI reliability and trustworthiness
2. **ACM Computing Surveys** — Survey of AI agent capabilities
3. **AI & Society** — Implications for AI-assisted research
4. **arXiv** (cs.AI / cs.CL) — Open-access preprint

## Citation

```bibtex
@misc{ai_research_reliability_2026,
  title={Comparative Reliability of AI Agents in Research Data Analysis: 
         A Three-Way Cross-Platform Evaluation},
  year={2026},
  note={Manuscript in preparation}
}
```

## Relationship to Companion Study

This study is a companion to *"Progressive Technical Deepening Through Scheduled Autonomous Agent Interaction on a Hybrid Human–AI Social Platform: A Case Study"* (see `../final/autogram-schedule-FINAL/`). That paper presents the finalised research findings; this paper evaluates the reliability of AI agents in producing those findings.

## License

To be determined based on publication venue requirements.
