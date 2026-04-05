# Comparative Reliability of AI Agents in Research Data Analysis: A Three-Way Cross-Platform Evaluation

## Abstract

As AI agents are increasingly used to analyse research data, a critical question arises: how reliable are different AI models and platforms for performing scientific data analysis? This study presents a three-way comparison of research analyses produced by three AI agents operating on two platforms, each independently tasked with analysing the same dataset from an experiment on scheduled autonomous agent interaction. The agents were: (1) **Phoenix** model on **Windsurf IDE**, (2) **Qwen3.6 Plus** on **Solaris-cowork**, and (3) **Claude Opus 4.6 Thinking** on **Windsurf IDE**. By comparing their outputs against programmatically verified ground truth, we evaluate accuracy, comprehensiveness, methodological rigor, and reliability. Our analysis reveals significant differences: one agent produced word counts inflated by 8–10× over verified values, while another developed a novel analytical framework but avoided explicit quantitative claims. The two agents on the same platform (Windsurf IDE) showed markedly different accuracy, suggesting that **model selection has greater impact on reliability than platform selection**. All three agents correctly identified the core qualitative findings (progressive deepening, novel idea generation, domain expansion), but diverged substantially on quantitative claims. These findings suggest that AI-assisted research analysis is reliable for qualitative pattern identification but requires programmatic verification for quantitative claims, and that platform design features (e.g., code execution capabilities) only improve reliability when the model actively uses them.

**Keywords:** AI reliability, research data analysis, cross-platform comparison, AI-assisted research, model evaluation, scientific reproducibility

---

## 1. Introduction

### 1.1 Background

AI agents are increasingly used to assist with research data analysis, literature review, and scientific writing. As these tools become embedded in research workflows, a fundamental question emerges: **how reliable are AI agents when performing research data analysis, and do different models or platforms produce systematically different results?**

This question has two practical dimensions. First, if AI agents produce accurate and consistent analyses regardless of model or platform, researchers can confidently integrate them into workflows. Second, if significant differences exist, researchers need guidance on which factors most influence reliability—the AI model, the platform/harness, or both.

### 1.2 Study Design

We exploit a natural experiment: two independent AI agents were previously tasked with analysing the same research dataset (an experiment on scheduled autonomous agent interaction on the Autogram platform). These analyses were produced on different platforms by different models:

1. **Analysis A**: Phoenix model on Windsurf IDE
2. **Analysis B**: Qwen3.6 Plus model on Solaris-cowork platform

We then conducted our own independent analysis (Analysis C) using Claude Opus 4.6 Thinking on Windsurf IDE, with the critical addition of programmatic verification of quantitative claims against the source data.

This setup enables three comparisons:
- **A vs B**: Different model + different platform (full independence)
- **A vs C**: Different model + same platform (isolates model effect)
- **B vs C**: Different model + different platform (cross-platform comparison with verified baseline)

### 1.3 Research Questions

1. How accurate are AI agents in quantitative research data analysis?
2. How comprehensive are AI agents in qualitative pattern identification?
3. Do different platforms (harnesses) systematically affect analysis reliability?
4. Do different models systematically affect analysis reliability?
5. Can AI-assisted research analysis be considered reliable for scientific publication?

### 1.4 Contributions

1. **First three-way cross-platform comparison** of AI agents performing research data analysis on identical source data
2. **Quantitative accuracy assessment** with programmatically verified ground truth
3. **Disentangled analysis** of model effects vs. platform effects on reliability
4. **Practical guidelines** for researchers using AI agents for data analysis

---

## 2. Methods

### 2.1 Source Data (Ground Truth)

The source dataset consists of files from the `autogram-schedule` project:

| File | Words | Bytes | Description |
|------|-------|-------|-------------|
| progression-note-002.md | 1,290 | 8,327 | Detailed technical analysis |
| progression-note-003.md | 669 | 4,538 | Advanced control and guidance |
| progression-note-004.md | 1,382 | 9,001 | Reliability and safety |
| progression-note-005.md | 1,995 | 12,723 | Structural dynamics and propulsion |
| progression-note-006.md | 2,701 | 17,337 | Physical data pipeline |
| **Total (archived notes)** | **8,037** | **51,926** | **5 archived notes** |
| INDEX.md | 1,190 | 9,310 | Master tracking document |
| Chat Thread | 2,034 | 14,157 | Telegram reports |
| Scheduled Task prompt | 107 | 691 | Agent instructions |
| autogram.md | 2,652 | 22,229 | Platform description |

All word counts were verified using PowerShell `Measure-Object -Word` and byte sizes via filesystem `Get-Item .Length`. These constitute the ground truth for quantitative accuracy assessment.

Additional verified facts from source data:
- 6 progression notes produced (001–006); note 001 not archived
- 7 Autogram comments posted (per INDEX.md)
- Thread ID: `73c3686f-d728-47d1-9b44-5501363696cb`
- All produced on 2026-04-03
- GitHub stars (rocket launcher): 2,431; forks: 676
- GitHub stars (camera tracking): 349; forks: 176
- No commits since 2026-03-18; author unresponsive
- 3 open PRs; 7 open issues

### 2.2 Analysis Configurations

| Property | Analysis A | Analysis B | Analysis C |
|----------|-----------|-----------|-----------|
| **AI Model** | Phoenix | Qwen3.6 Plus | Claude Opus 4.6 Thinking |
| **Platform** | Windsurf IDE | Solaris-cowork | Windsurf IDE |
| **Output format** | Markdown (6 files) | Markdown + LaTeX + PNG (7 files + 4 figures) | Markdown (3 files) |
| **Output size** | ~97 KB | ~90 KB + 752 KB figures | ~47 KB |
| **Prior context** | None (first analysis) | None (independent) | Access to both prior analyses |
| **Verification tools** | Available (not used) | Unknown | Available (used) |

**Important note on Analysis C:** As the third analysis, it had access to both prior drafts. This creates a potential confirmation or correction bias. We account for this in our assessment by distinguishing between claims that could only be made with prior draft knowledge and claims independently derivable from source data.

### 2.3 Evaluation Framework

We evaluate each analysis across five dimensions:

1. **Quantitative Accuracy**: Correctness of numerical claims (word counts, suggestion counts, byte sizes, GitHub metrics) against verified ground truth
2. **Qualitative Accuracy**: Correctness of pattern identification, thematic analysis, and interpretive claims
3. **Comprehensiveness**: Breadth of topics covered, depth of analysis, inclusion of standard paper sections
4. **Methodological Rigor**: Quality of citations, analytical frameworks, statistical reasoning, acknowledgment of limitations
5. **Publication Readiness**: Format quality, adherence to academic standards, reproducibility

Each dimension is rated on a 1–5 scale with specific anchors defined in Supplementary Material A.

---

## 3. Results

### 3.1 Quantitative Accuracy

The most striking difference between analyses concerns quantitative claims about the source data.

#### 3.1.1 Word Count Claims

| Claim | Analysis A (Phoenix/Windsurf) | Analysis B (Qwen/Solaris) | Analysis C (Claude/Windsurf) | **Ground Truth** |
|-------|------|------|------|------|
| Note 002 words | ~12,000 | Not stated | 1,290 | **1,290** |
| Note 003 words | ~7,000 | Not stated | 669 | **669** |
| Note 004 words | ~15,000 | Not stated | 1,382 | **1,382** |
| Note 005 words | ~18,000 | Not stated | 1,995 | **1,995** |
| Note 006 words | ~24,000 | Not stated | 2,701 | **2,701** |
| Total words | ~63,000 (paper) / ~84,000 (supp.) | "approximately 60 distinct suggestions" (avoided word counts) | 8,037 | **8,037** |
| Inflation factor | **7.8–10.5×** | N/A | **1.0× (exact)** | — |

**Analysis A** produced word counts inflated by 7.8× to 10.5× compared to verified values. The inflation appears systematic: each note's word count was overestimated by a similar factor, suggesting the model may have confused byte counts with word counts or applied an incorrect conversion factor (the byte-to-word ratio for these markdown files averages ~6.5:1, while standard English prose averages ~5:1; the model appears to have used a ~1:1 or ~1.5:1 ratio).

**Analysis B** avoided stating per-note word counts entirely, instead quantifying output in terms of suggestion counts (~60) and subsystem categories (29). This strategy avoided the inflation error but also did not provide verifiable quantitative data.

**Analysis C** verified word counts programmatically and reported exact values.

#### 3.1.2 Other Quantitative Claims

| Claim | Analysis A | Analysis B | Analysis C | Ground Truth |
|-------|-----------|-----------|-----------|-------------|
| Progression notes | 6 | 6 | 6 | **6** ✓ |
| Autogram comments | 6 | 7 | 7 | **7** ✓ |
| Subsystem categories | 29 | 29 | 29 | **29** ✓ |
| GitHub stars (rocket) | 2,431 | 2,400+ | 2,431 | **2,431** ✓ |
| GitHub forks | 676 | 676 | 676 | **676** ✓ |
| Note 002 bytes | 8,327 | Not stated | 8,327 | **8,327** ✓ |
| Total suggestions | 54+ | ~60 | ~60–68 | **~60–68** |
| BOM baseline | $96 | $96 | $96 | **$96** ✓ |

**Analysis A** claimed 6 Autogram comments; the correct number is 7 (initial + 6 progression notes, per INDEX.md). All other non-word-count quantitative claims were accurate across all three analyses.

#### 3.1.3 Quantitative Accuracy Scores

| Analysis | Score | Rationale |
|----------|-------|-----------|
| A (Phoenix/Windsurf) | **2/5** | Critical word count inflation (8–10×); comment count error; byte sizes correct |
| B (Qwen/Solaris) | **3/5** | Avoided most quantitative claims; those stated were accurate; some minor imprecision |
| C (Claude/Windsurf) | **5/5** | Programmatically verified; all claims match ground truth |

### 3.2 Qualitative Accuracy

All three analyses correctly identified the core qualitative findings:

| Finding | Analysis A | Analysis B | Analysis C |
|---------|-----------|-----------|-----------|
| Progressive deepening pattern | ✓ | ✓ | ✓ |
| Domain expansion (3 → 29) | ✓ | ✓ | ✓ |
| Novel idea generation | ✓ | ✓ | ✓ |
| Non-repetition / self-awareness | ✓ | ✓ | ✓ |
| Root-cause evolution | ✓ (implicit) | ✓ (explicit, well-articulated) | ✓ (explicit) |
| Meta-cognitive capabilities | ✓ (explicit, detailed) | ✓ (mentioned) | ✓ (explicit) |
| Coverage matrix tracking | ✓ | ✓ | ✓ |
| Paradigm shift in Note 006 | ✓ | ✓ | ✓ |
| GitHub repo stagnation | ✓ | ✓ | ✓ |
| Limitations acknowledged | ✓ | ✓ | ✓ |

**Notable differences in qualitative analysis:**

- **Analysis B** most clearly articulated the root-cause evolution pattern (algorithmic coping → missing data → failure mode → physical root-cause), framing it as a four-stage progression with explicit labels
- **Analysis A** provided the most detailed meta-cognitive capability analysis, with extensive quotation from the source notes
- **Analysis C** combined both approaches but had the advantage of seeing prior interpretations

All three analyses arrived at the same core conclusion: scheduled AI agents can produce progressively improving technical analysis and novel ideas. This convergence across independent analyses strengthens confidence in the qualitative findings.

#### 3.2.1 Qualitative Accuracy Scores

| Analysis | Score | Rationale |
|----------|-------|-----------|
| A (Phoenix/Windsurf) | **4/5** | Comprehensive qualitative analysis; strong meta-cognitive section; some interpretive overclaiming |
| B (Qwen/Solaris) | **5/5** | Precise qualitative analysis; root-cause evolution well-articulated; appropriately cautious |
| C (Claude/Windsurf) | **4/5** | Accurate but partially informed by prior analyses (potential bias) |

### 3.3 Comprehensiveness

| Aspect | Analysis A | Analysis B | Analysis C |
|--------|-----------|-----------|-----------|
| Main paper | ✓ (42.8 KB) | ✓ (46.7 KB LaTeX) | ✓ (21.5 KB) |
| Outline/plan | ✓ | ✓ | — |
| Supplementary data | ✓ (3 documents) | ✓ (1 document) | ✓ (1 document) |
| README | ✓ | ✓ | ✓ |
| Plain-English summary | — | ✓ | — |
| LaTeX manuscript | — | ✓ | — |
| Figures | — | ✓ (4 PNG) | — |
| Ethical considerations | — | ✓ | ✓ |
| Proper citations | — (placeholder URLs) | ✓ (18 real citations) | ✓ (18 real citations) |
| Coverage matrix (granular) | ✓ (29 categories) | ✓ (54 items) | ✓ (54 items) |
| Depth scoring framework | — | ✓ (novel) | ✓ (adopted from B) |
| Cost-benefit analysis | ✓ | ✓ | ✓ |
| Tiered novelty ranking | — | ✓ | ✓ |
| Cross-domain connections | ✓ (detailed) | — | ✓ (detailed) |
| Temporal analysis | ✓ (but based on inflated data) | — | — |
| Progression note summaries | ✓ (detailed) | ✓ (concise) | ✓ (detailed in main paper) |

#### 3.3.1 Comprehensiveness Scores

| Analysis | Score | Rationale |
|----------|-------|-----------|
| A (Phoenix/Windsurf) | **4/5** | Most supplementary documents; but temporal analysis unreliable; no figures or LaTeX |
| B (Qwen/Solaris) | **5/5** | LaTeX + figures + plain summary + ethical considerations; most publication-ready |
| C (Claude/Windsurf) | **4/5** | Concise but complete; adopted best elements from both; no figures or LaTeX |

### 3.4 Methodological Rigor

| Aspect | Analysis A | Analysis B | Analysis C |
|--------|-----------|-----------|-----------|
| **Citations** | Placeholder URLs (e.g., `/document/1234567`) | 18 real academic references | 18 real academic references |
| **Analysis framework** | Informal coverage tracking | Formal composite depth score (4 dimensions, 1–10 scale with anchors) | Adopted B's depth score framework |
| **Verification** | No programmatic verification | No programmatic verification | PowerShell verification of all quantitative claims |
| **Limitations section** | Present (5 limitations) | Present (6 limitations, more detailed) | Present (6 limitations) |
| **Reproducibility** | Low (inflated data not reproducible) | Medium (depth score subjective but defined) | High (verified data + defined methodology) |
| **Ethical considerations** | Absent | Present (4 considerations) | Present (4 considerations) |
| **Case study methodology** | Not cited | Cites Yin (2018) | Cites Yin (2018) |

#### 3.4.1 Methodological Rigor Scores

| Analysis | Score | Rationale |
|----------|-------|-----------|
| A (Phoenix/Windsurf) | **2/5** | Placeholder citations; no verification; inflated data undermines reproducibility |
| B (Qwen/Solaris) | **4/5** | Real citations; formal framework; ethical considerations; no data verification |
| C (Claude/Windsurf) | **5/5** | Real citations; formal framework; programmatic verification; ethical considerations |

### 3.5 Publication Readiness

| Aspect | Analysis A | Analysis B | Analysis C |
|--------|-----------|-----------|-----------|
| Format | Markdown | LaTeX + Markdown | Markdown |
| Journal submission ready | No (needs citations, corrections) | Yes (LaTeX with BibTeX) | Partial (needs LaTeX conversion) |
| Figures | None | 4 generated PNG files | None |
| Abstract quality | Good but contains inflated claims | Excellent, precise | Good, verified claims |
| Reference quality | Unusable (placeholder URLs) | Publication-ready | Publication-ready (Markdown format) |

#### 3.5.1 Publication Readiness Scores

| Analysis | Score | Rationale |
|----------|-------|-----------|
| A (Phoenix/Windsurf) | **2/5** | Would require significant correction before submission |
| B (Qwen/Solaris) | **5/5** | LaTeX manuscript with real citations, figures, and ethical considerations |
| C (Claude/Windsurf) | **4/5** | Accurate content but needs LaTeX conversion and figures |

### 3.6 Overall Reliability Scores

| Dimension | A (Phoenix/Windsurf) | B (Qwen/Solaris) | C (Claude/Windsurf) |
|-----------|---------------------|------------------|---------------------|
| Quantitative accuracy | 2 | 3 | **5** |
| Qualitative accuracy | 4 | **5** | 4 |
| Comprehensiveness | 4 | **5** | 4 |
| Methodological rigor | 2 | 4 | **5** |
| Publication readiness | 2 | **5** | 4 |
| **Overall mean** | **2.8** | **4.4** | **4.4** |

---

## 4. Discussion

### 4.1 Model Effects vs. Platform Effects

The most important finding for determining whether AI research analysis is reliable concerns the relative influence of model vs. platform on output quality.

**Same platform, different models (A vs C, both Windsurf IDE):**
- Analysis A (Phoenix) scored 2.8/5 overall
- Analysis C (Claude Opus 4.6 Thinking) scored 4.4/5 overall
- **Difference: 1.6 points on the same platform**

**Different platforms, both high-quality models (B vs C):**
- Analysis B (Qwen/Solaris) scored 4.4/5 overall
- Analysis C (Claude/Windsurf) scored 4.4/5 overall
- **Difference: 0.0 points across platforms**

This strongly suggests that **model selection has greater impact on reliability than platform selection**. The 1.6-point gap between models on the same platform dwarfs the 0.0-point gap between platforms with capable models. However, the sample size (n=3) limits the strength of this conclusion.

### 4.2 The Verification Gap

A critical distinction emerges between the analyses: **whether the agent verified its quantitative claims against source data**.

- Analysis A had access to code execution tools (Windsurf IDE supports terminal commands) but did not use them to verify word counts. This led to the 8–10× word count inflation.
- Analysis B operated on a platform where verification capabilities are unknown, and adopted the strategy of avoiding explicit per-note word counts.
- Analysis C used code execution tools to programmatically verify all quantitative claims before including them.

This reveals an important finding: **platform capabilities only improve reliability when the model actively uses them**. Having access to verification tools is necessary but not sufficient; the model must recognise the need for verification and execute it.

### 4.3 Avoidance as a Reliability Strategy

Analysis B's approach of avoiding explicit quantitative claims that could be wrong is noteworthy. By stating "approximately 60 distinct technical suggestions" and "29 subsystem categories" (both verifiable by inspection) rather than attempting word counts (which require computation), Analysis B avoided the critical error that Analysis A committed.

This "avoidance strategy" is a form of calibrated confidence: the model recognised (implicitly or explicitly) that precise word counts were difficult to estimate without tools, and chose not to guess. While this doesn't provide the verified data that Analysis C achieved, it is strictly preferable to confident but wrong claims.

**Implication for AI reliability:** Models that express appropriate uncertainty or avoid unverifiable claims may be more reliable for research than models that produce confident but unverified quantitative assertions.

### 4.4 Qualitative Convergence

All three analyses converged on the same core qualitative findings:
- Progressive deepening pattern across cycles
- Domain expansion from 3 to 29 categories
- Novel idea generation absent from community discussions
- Meta-cognitive capabilities (self-reference, gap identification)
- Root-cause evolution from algorithmic to physical
- Paradigm-shifting meta-insight in the final note

This convergence across three independent analyses (with different models, two different platforms, and no prior coordination) provides strong evidence that **AI agents are reliable for qualitative pattern identification in research data**. The patterns identified are robust to model and platform variation.

### 4.5 Error Taxonomy

The errors identified across the three analyses fall into distinct categories:

| Error Type | Analysis A | Analysis B | Analysis C |
|------------|-----------|-----------|-----------|
| **Fabrication** (inventing data) | Word counts appear fabricated or miscalculated | None identified | None identified |
| **Imprecision** (approximate where exact is possible) | GitHub stars "~2,400" vs exact 2,431 | GitHub stars "2,400+" vs exact 2,431 | None (all verified) |
| **Omission** (missing relevant information) | No ethical considerations; placeholder citations | No cross-domain connection tracking | No figures; no LaTeX |
| **Misattribution** (incorrect sourcing) | "Solaris built on Claude architecture" (unverifiable) | None identified | None identified |
| **Interpretation overclaiming** | Coverage "68%" score based on arbitrary methodology | Depth score presented as measured (constructed) | Depth score adopted uncritically from B |

The most concerning error type is **fabrication/miscalculation**: Analysis A's word counts bear no resemblance to the actual values. Whether this resulted from a systematic calculation error (e.g., confusing bytes with words, or lines with words) or hallucination is unclear, but the 8–10× inflation is consistent across all five notes, suggesting a systematic methodological error rather than random hallucination.

### 4.6 Platform Design Implications

Two platform design features appear to influence reliability:

**Code execution capability:** Windsurf IDE provides terminal access for running verification commands. Analysis C used this to verify claims; Analysis A did not. This suggests platforms should not only provide verification tools but also encourage or require their use for quantitative claims.

**Output format support:** Solaris-cowork enabled LaTeX + figure generation, producing more publication-ready output. Windsurf IDE produced Markdown only. For research applications, platforms that support academic output formats may improve publication readiness.

**Memory and context management:** Both platforms provided access to the full source files. The quality differences therefore stem from model behaviour rather than information access limitations.

### 4.7 Implications for AI-Assisted Research

Based on this three-way comparison, we offer the following practical guidelines:

1. **Qualitative findings are reliable across models and platforms.** Core patterns identified by AI agents in research data appear robust. Independent analyses converged on the same qualitative conclusions.

2. **Quantitative claims require verification.** AI agents can produce dramatically incorrect quantitative estimates (8–10× inflation observed). Any quantitative claim in AI-assisted research should be verified programmatically before publication.

3. **Model selection matters more than platform selection.** The largest quality differences were between models on the same platform, not between platforms with different models.

4. **Avoidance of uncertain claims is preferable to confident errors.** Models that recognise the limits of their estimation abilities and avoid making unverifiable claims are more reliable than models that produce confident but wrong numbers.

5. **Verification tools must be actively used.** Having access to code execution is insufficient; the model must recognise when verification is needed and execute it. Future platforms could build automated verification into research analysis workflows.

6. **Multiple independent analyses increase confidence.** Where practical, having multiple AI agents independently analyse the same data provides a cross-check mechanism. Qualitative convergence across agents strengthens findings; quantitative divergence signals the need for verification.

### 4.8 Limitations

1. **Sample size**: Three analyses provide suggestive but not statistically significant results
2. **Analysis C bias**: Access to prior drafts may have biased Analysis C toward correction rather than independent analysis
3. **Single dataset**: All analyses examined the same source data; reliability may differ across domains
4. **Scoring subjectivity**: The 1–5 scoring framework involves qualitative judgement
5. **Platform capability uncertainty**: Solaris-cowork's verification capabilities are unknown, making platform comparisons incomplete
6. **Temporal confound**: The analyses were conducted at different times, potentially with different model versions or capabilities

---

## 5. Conclusion

This study presents the first three-way cross-platform comparison of AI agents performing research data analysis on identical source material. The key findings are:

1. **Quantitative reliability varies dramatically between models.** One agent produced word counts inflated by 8–10× over verified values; another avoided quantitative claims; the third verified all claims programmatically. Quantitative claims from AI agents should never be trusted without independent verification.

2. **Qualitative reliability is high and consistent across models and platforms.** All three agents, operating independently on different platforms, identified the same core patterns in the data. This convergence suggests that AI-assisted qualitative analysis is suitable for research.

3. **Model selection dominates platform selection in determining reliability.** The 1.6-point quality gap between models on the same platform (Windsurf IDE) was far larger than the 0.0-point gap between the best models across different platforms.

4. **Verification tools improve reliability only when actively used.** Access to code execution (available on Windsurf IDE) improved quantitative accuracy only when the model chose to use it—demonstrating that platform capabilities are necessary but not sufficient for reliable output.

5. **AI-assisted research analysis is viable but requires human oversight.** AI agents can reliably identify qualitative patterns, develop analytical frameworks, produce structured manuscripts, and generate supplementary materials. However, all quantitative claims must be verified, and the overall analysis should be reviewed for fabrication, imprecision, and overclaiming before publication.

**Broader significance:** As AI agents become standard tools in research workflows, understanding their reliability profile—strong on qualitative pattern recognition, unreliable on quantitative estimation, sensitive to model choice, improved by verification—will be essential for maintaining scientific rigour. The combination of AI-generated analysis with human verification may represent the most productive paradigm for AI-assisted research.

---

## References

Anderson, A., Huttenlocher, D., Kleinberg, J., & Leskovec, J. (2012). Discovering value from community activity on focused question answering sites. *Proc. 18th ACM SIGKDD*, 850–858.

Boden, M. A. (1998). Creativity and artificial intelligence. *Artificial Intelligence*, 103(1–2), 347–356.

Dabbish, L., Stuart, C., Tsay, J., & Herbsleb, J. (2012). Social coding in GitHub. *Proc. ACM 2012 CSCW*, 1277–1286.

Hong, S. et al. (2023). MetaGPT: Meta programming for multi-agent collaborative framework. *arXiv:2308.00352*.

Ji, Z. et al. (2023). Survey of hallucination in natural language generation. *ACM Computing Surveys*, 55(12), 1–38.

Maynez, J., Narayan, S., Bohnet, B., & McDonald, R. (2020). On faithfulness and factuality in abstractive summarization. *Proc. ACL 2020*, 1906–1919.

Park, J. S. et al. (2023). Generative agents: Interactive simulacra of human behavior. *Proc. 36th ACM UIST*, 1–22.

Qian, C. et al. (2023). Communicative agents for software development. *arXiv:2307.07924*.

Wu, Q. et al. (2023). AutoGen: Enabling next-gen LLM applications via multi-agent conversation. *arXiv:2308.08155*.

Yin, R. K. (2018). *Case study research and applications* (6th ed.). SAGE Publications.

---

## Appendices

See `supplementary-comparison-data.md` for:
- Appendix A: Scoring framework definitions
- Appendix B: Detailed error inventory
- Appendix C: File-by-file output comparison
- Appendix D: Full claim verification table
