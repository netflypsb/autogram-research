# Supplementary Materials: Comparative Reliability of AI Agents in Research Data Analysis

---

## Appendix A: Scoring Framework Definitions

Each dimension is rated on a 1–5 scale:

### Quantitative Accuracy

| Score | Definition |
|-------|-----------|
| 1 | Multiple critical quantitative errors (>50% deviation from ground truth) |
| 2 | One or more critical quantitative errors (>100% deviation) with some correct claims |
| 3 | No critical errors but avoids most quantitative claims; those stated are approximate |
| 4 | Most quantitative claims accurate; minor imprecisions (<20% deviation) |
| 5 | All quantitative claims verified and match ground truth exactly |

### Qualitative Accuracy

| Score | Definition |
|-------|-----------|
| 1 | Misidentifies core patterns; draws incorrect conclusions |
| 2 | Identifies some patterns but misses major findings or makes significant interpretive errors |
| 3 | Identifies core patterns but with shallow analysis or some overclaiming |
| 4 | Accurately identifies all core patterns with good depth; minor interpretive issues |
| 5 | Precisely identifies all patterns; well-articulated analysis; appropriately cautious claims |

### Comprehensiveness

| Score | Definition |
|-------|-----------|
| 1 | Covers fewer than 3 standard paper sections; major gaps |
| 2 | Covers most sections but missing key elements (e.g., no limitations, no supplementary) |
| 3 | All standard sections present; supplementary materials basic |
| 4 | All sections with good depth; supplementary materials detailed; minor gaps |
| 5 | All sections comprehensive; supplementary materials extensive; additional valuable elements (figures, plain summaries, multiple formats) |

### Methodological Rigor

| Score | Definition |
|-------|-----------|
| 1 | No citations; no analytical framework; no limitations; claims unsubstantiated |
| 2 | Placeholder or fake citations; informal framework; limitations mentioned briefly |
| 3 | Some real citations; defined framework; limitations acknowledged; no verification |
| 4 | Real citations; formal framework with clear methodology; ethical considerations; limitations detailed |
| 5 | Real citations; formal verified framework; programmatic verification; ethical considerations; full reproducibility |

### Publication Readiness

| Score | Definition |
|-------|-----------|
| 1 | Cannot be submitted without complete rewrite |
| 2 | Requires significant correction (factual errors, missing citations) before submission |
| 3 | Content adequate but format needs conversion and polishing |
| 4 | Content accurate and well-structured; needs format conversion (e.g., Markdown → LaTeX) |
| 5 | Ready for submission: correct format, real citations, figures, verified claims |

---

## Appendix B: Detailed Error Inventory

### Analysis A (Phoenix / Windsurf IDE)

| # | Error | Type | Severity | Details |
|---|-------|------|----------|---------|
| A1 | Note 002 word count: ~12,000 | Fabrication | **Critical** | Actual: 1,290 words (9.3× inflation) |
| A2 | Note 003 word count: ~7,000 | Fabrication | **Critical** | Actual: 669 words (10.5× inflation) |
| A3 | Note 004 word count: ~15,000 | Fabrication | **Critical** | Actual: 1,382 words (10.9× inflation) |
| A4 | Note 005 word count: ~18,000 | Fabrication | **Critical** | Actual: 1,995 words (9.0× inflation) |
| A5 | Note 006 word count: ~24,000 | Fabrication | **Critical** | Actual: 2,701 words (8.9× inflation) |
| A6 | Total word count: ~63,000 (paper) | Fabrication | **Critical** | Actual: 8,037 words (7.8× inflation) |
| A7 | Total word count: ~84,000 (supp.) | Fabrication | **Critical** | Actual: 8,037 words (10.5× inflation) |
| A8 | Autogram comments: 6 | Imprecision | Minor | Actual: 7 (per INDEX.md) |
| A9 | Word production rate: ~504 words/min | Derived error | **Major** | Based on inflated word counts; meaningless |
| A10 | Session durations: 15–40 min | Unverifiable | Moderate | No timestamps in source data to verify |
| A11 | References: placeholder URLs | Omission | **Major** | e.g., "ieeexplore.ieee.org/document/1234567" |
| A12 | "Solaris built on Claude architecture" | Misattribution | Minor | Not verifiable from source data |
| A13 | Coverage completeness "68%" | Overclaiming | Minor | Arbitrary scoring methodology |
| A14 | BOM evolution "$150-250 (note 006)" | Imprecision | Minor | $150-250 not directly stated in source |
| A15 | No ethical considerations | Omission | Moderate | Standard for publication-targeted papers |

**Summary:** 7 critical errors, 2 major errors, 3 moderate, 3 minor. All critical errors stem from word count inflation.

### Analysis B (Qwen3.6 Plus / Solaris-cowork)

| # | Error | Type | Severity | Details |
|---|-------|------|----------|---------|
| B1 | "Conducted over a continuous session" | Imprecision | Minor | Chat thread suggests multiple sessions |
| B2 | Manuscript abstract truncation | Technical | Minor | "(42 bytes truncated)" artifact in LaTeX |
| B3 | Depth score presented as measured | Framing | Minor | Could be clearer it's analyst-constructed |
| B4 | Supercapacitor buffer in matrix (unmarked) | Imprecision | Trivial | Listed but never addressed — technically correct as gap |
| B5 | Note numbering discrepancy not noted | Omission | Minor | Note 002 is titled "Progression Note #1" in source |
| B6 | No cross-domain connection tracking | Omission | Minor | Valuable analysis dimension not included |

**Summary:** 0 critical errors, 0 major errors, 0 moderate, 5 minor, 1 trivial.

### Analysis C (Claude Opus 4.6 Thinking / Windsurf IDE)

| # | Error | Type | Severity | Details |
|---|-------|------|----------|---------|
| C1 | Depth score adopted from Analysis B | Dependency | Minor | Not independently derived |
| C2 | No LaTeX output | Omission | Minor | Markdown only; needs conversion |
| C3 | No figures generated | Omission | Minor | No visual aids |
| C4 | Prior draft access (potential bias) | Methodological | Moderate | Correction bias rather than independent analysis |
| C5 | Note numbering discrepancy not noted | Omission | Minor | Same as B5 |

**Summary:** 0 critical errors, 0 major errors, 1 moderate, 4 minor.

### Error Count Comparison

| Severity | Analysis A | Analysis B | Analysis C |
|----------|-----------|-----------|-----------|
| Critical | 7 | 0 | 0 |
| Major | 2 | 0 | 0 |
| Moderate | 3 | 0 | 1 |
| Minor | 3 | 5 | 4 |
| Trivial | 0 | 1 | 0 |
| **Total** | **15** | **6** | **5** |
| **Weighted score*** | **31** | **5** | **6** |

*Weighted: Critical=5, Major=3, Moderate=2, Minor=1, Trivial=0

---

## Appendix C: File-by-File Output Comparison

### Analysis A (Phoenix / Windsurf IDE) — 6 files

| File | Size | Purpose | Quality |
|------|------|---------|---------|
| 00-outline.md | 4,969 B | Paper outline | Good structure |
| 01-main-paper.md | 42,807 B | Full paper | Contains inflated word counts |
| 02-supplementary-data-analysis.md | 7,282 B | Quantitative data | Contains inflated word counts |
| 03-supplementary-coverage-matrices.md | 12,818 B | Coverage matrices | Detailed and useful |
| 04-supplementary-progression-analysis.md | 18,998 B | Progression analysis | Detailed but some derived errors |
| README.md | 10,188 B | Repository guide | Good overview |
| **Total** | **97,062 B** | | |

### Analysis B (Qwen3.6 Plus / Solaris-cowork) — 7 files + 4 figures

| File | Size | Purpose | Quality |
|------|------|---------|---------|
| 00-research-analysis.md | 11,032 B | Observations and findings | Excellent |
| 01-paper-plan.md | 6,788 B | Manuscript plan | Detailed with venue targets |
| manuscript.tex | 46,707 B | LaTeX manuscript | Publication-ready |
| supplementary-materials.md | 14,481 B | Full data catalog | Comprehensive |
| research-summary.md | 4,347 B | Plain-English summary | Excellent accessibility |
| README.md | 6,420 B | Repository guide | Good overview |
| figures/ (4 PNGs) | ~752 KB | System arch, domain expansion, depth score, coverage heatmap | Professional |
| **Total** | **~842 KB** | | |

### Analysis C (Claude Opus 4.6 Thinking / Windsurf IDE) — 3 files

| File | Size | Purpose | Quality |
|------|------|---------|---------|
| main-paper.md | ~21,500 B | Full paper | Verified, accurate |
| supplementary-materials.md | ~25,500 B | Full data catalog | Comprehensive, verified |
| README.md | ~4,500 B | Repository guide | Concise |
| **Total** | **~51,500 B** | | |

### Output Volume Comparison

| Metric | Analysis A | Analysis B | Analysis C |
|--------|-----------|-----------|-----------|
| Files produced | 6 | 7 + 4 figures | 3 |
| Text output (bytes) | 97,062 | 89,775 | ~51,500 |
| Figures | 0 | 4 | 0 |
| Output formats | Markdown | Markdown + LaTeX + PNG | Markdown |
| Redundancy | High (repeated content across supplementary docs) | Low | Low |

---

## Appendix D: Full Claim Verification Table

### Word Count Claims

| Claim Source | Claimed Value | Ground Truth | Accuracy | Error Factor |
|-------------|--------------|-------------|----------|-------------|
| A: Note 001 words | ~8,000 | ~1,000–1,500 (est.) | **Wrong** | ~6× |
| A: Note 002 words | ~12,000 | 1,290 | **Wrong** | 9.3× |
| A: Note 003 words | ~7,000 | 669 | **Wrong** | 10.5× |
| A: Note 004 words | ~15,000 | 1,382 | **Wrong** | 10.9× |
| A: Note 005 words | ~18,000 | 1,995 | **Wrong** | 9.0× |
| A: Note 006 words | ~24,000 | 2,701 | **Wrong** | 8.9× |
| A: Total (paper) | ~63,000 | 8,037 | **Wrong** | 7.8× |
| A: Total (supp.) | ~84,000 | 8,037 | **Wrong** | 10.5× |
| C: Note 002 words | 1,290 | 1,290 | ✓ Exact | 1.0× |
| C: Note 003 words | 669 | 669 | ✓ Exact | 1.0× |
| C: Note 004 words | 1,382 | 1,382 | ✓ Exact | 1.0× |
| C: Note 005 words | 1,995 | 1,995 | ✓ Exact | 1.0× |
| C: Note 006 words | 2,701 | 2,701 | ✓ Exact | 1.0× |
| C: Total words | 8,037 | 8,037 | ✓ Exact | 1.0× |

### Structural Claims

| Claim | A | B | C | Ground Truth |
|-------|---|---|---|-------------|
| Number of progression notes | 6 ✓ | 6 ✓ | 6 ✓ | 6 |
| Autogram comments posted | 6 ✗ | 7 ✓ | 7 ✓ | 7 |
| Subsystem categories | 29 ✓ | 29 ✓ | 29 ✓ | 29 |
| Thread ID | Correct ✓ | Not stated | Correct ✓ | 73c3686f... |
| Experiment date | 2026-04-03 ✓ | 2026-04-03 ✓ | 2026-04-03 ✓ | 2026-04-03 |
| Schedule interval | 30 min ✓ | 30 min ✓ | 30 min ✓ | 30 min |

### GitHub Metrics Claims

| Metric | A | B | C | Ground Truth |
|--------|---|---|---|-------------|
| Rocket launcher stars | 2,431 ✓ | 2,400+ ≈ | 2,431 ✓ | 2,431 |
| Rocket launcher forks | 676 ✓ | 676 ✓ | 676 ✓ | 676 |
| Camera tracking stars | 349 ✓ | Not stated | 349 ✓ | 349 |
| Camera tracking forks | 176 ✓ | Not stated | 176 ✓ | 176 |
| Open PRs | 3 ✓ | 3 ✓ | 3 ✓ | 3 |
| Open issues | 7 ✓ | 7 ✓ | 7 ✓ | 7 |
| Last commit | March 18 ✓ | March 18 ✓ | 2026-03-18 ✓ | 2026-03-18 |

### Byte Size Claims

| File | A | B | C | Ground Truth |
|------|---|---|---|-------------|
| Note 002 | 8,327 ✓ | Not stated | 8,327 ✓ | 8,327 |
| Note 003 | 4,538 ✓ | Not stated | 4,538 ✓ | 4,538 |
| Note 004 | 9,001 ✓ | Not stated | 9,001 ✓ | 9,001 |
| Note 005 | 12,723 ✓ | Not stated | 12,723 ✓ | 12,723 |
| Note 006 | 17,337 ✓ | Not stated | 17,337 ✓ | 17,337 |
| Total | 51,926 ✓ | Not stated | 51,926 ✓ | 51,926 |

**Note:** Analysis A correctly reported byte sizes but produced drastically wrong word counts from the same files—suggesting the model read the files but applied an incorrect conversion from bytes/content to word estimates.

---

## Appendix E: Hypothesis for Word Count Inflation

Analysis A's word count inflation shows a remarkably consistent pattern:

| Note | Actual Words | Claimed Words | Ratio | Actual Bytes | Bytes ÷ Actual Words |
|------|-------------|--------------|-------|-------------|---------------------|
| 002 | 1,290 | ~12,000 | 9.3× | 8,327 | 6.5 |
| 003 | 669 | ~7,000 | 10.5× | 4,538 | 6.8 |
| 004 | 1,382 | ~15,000 | 10.9× | 9,001 | 6.5 |
| 005 | 1,995 | ~18,000 | 9.0× | 12,723 | 6.4 |
| 006 | 2,701 | ~24,000 | 8.9× | 17,337 | 6.4 |

The claimed word counts are approximately **1.3–1.7× the byte count** of each file. This suggests the model may have:

1. **Estimated words from byte size using a ~1.5 bytes/word ratio** (typical for plain text) rather than the actual ~6.5 bytes/word ratio for markdown with tables, formatting, and whitespace
2. **Alternatively**, the model may have estimated word counts from line counts × an inflated words-per-line estimate
3. **Or**, the model estimated the size of the *Autogram comments posted* (which are not archived and may be longer than the progression note summaries), but still cited them as progression note word counts

The consistency of the inflation factor (8.9–10.9×) across all five notes strongly suggests a systematic methodological error rather than random hallucination.

---

## Appendix F: Unique Contributions by Each Analysis

### Unique to Analysis A (Phoenix / Windsurf IDE)
- Detailed temporal analysis (session durations, word production rates) — though based on inflated data
- Coverage completeness scoring (68%) with weighted methodology
- Most detailed meta-cognitive capability analysis with extensive quotation
- Cross-domain connection inventory (first to track this)
- Separate supplementary documents for data analysis, coverage matrices, and progression analysis

### Unique to Analysis B (Qwen3.6 Plus / Solaris-cowork)
- Composite depth score framework (4 dimensions, 1–10 scale with defined anchors)
- LaTeX manuscript ready for journal submission
- Generated figures (4 professional PNG visualisations)
- Plain-English research summary for non-specialist readers
- Paper plan with target publication venues and figure/table requirements
- Root-cause evolution explicitly labelled as four-stage progression
- Ethical considerations section
- Tiered novel ideas ranking (Paradigm-Shifting / Very High / High)

### Unique to Analysis C (Claude Opus 4.6 Thinking / Windsurf IDE)
- Programmatically verified word counts (exact values via PowerShell)
- Explicit methodological note about verification
- Correction of Draft 1's inflation errors with evidence
- Synthesis of best elements from both prior analyses
- Cross-domain connection inventory (adopted from A, with data from source)

---

## Appendix G: Qualitative Agreement Matrix

Degree of agreement between the three analyses on key qualitative claims:

| Claim | A–B | A–C | B–C | Overall |
|-------|-----|-----|-----|---------|
| Progressive deepening occurs | Agree | Agree | Agree | **Unanimous** |
| Domain expansion is systematic | Agree | Agree | Agree | **Unanimous** |
| Novel ideas were generated | Agree | Agree | Agree | **Unanimous** |
| Agent avoided repetition | Agree | Agree | Agree | **Unanimous** |
| Meta-cognitive capabilities present | Agree | Agree | Agree | **Unanimous** |
| Root-cause evolution observed | Agree | Agree | Agree | **Unanimous** |
| Note 006 represents paradigm shift | Agree | Agree | Agree | **Unanimous** |
| Coverage reached 29 categories | Agree | Agree | Agree | **Unanimous** |
| GitHub repos were stagnant | Agree | Agree | Agree | **Unanimous** |
| Community PRs aligned with agent findings | Agree | Agree | Agree | **Unanimous** |
| Single case study is a limitation | Agree | Agree | Agree | **Unanimous** |
| No human interaction is a limitation | Agree | Agree | Agree | **Unanimous** |
| Multi-agent study is needed | Agree | Agree | Agree | **Unanimous** |
| Human comparison study is needed | Agree | Agree | Agree | **Unanimous** |
| Depth score as quality metric | Not in A | N/A | Agree | **B–C agree** |
| Cross-domain connections tracked | Not in B | Agree | N/A | **A–C agree** |
| Ethical considerations needed | Not in A | N/A | Agree | **B–C agree** |

**Unanimous agreement:** 14/17 claims (82%)
**Majority agreement:** 17/17 claims (100%)

This high level of qualitative convergence across three independent analyses provides strong evidence for the robustness of the qualitative findings.
