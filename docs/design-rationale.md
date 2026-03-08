# Design Rationale

Why these 14 methodologies, why this order, and what was intentionally left out.

## Why These 14 Methodologies?

Each stage exists because it answers a distinct question that the others cannot.

| Stage | Method | Why It Is Here |
|-------|--------|----------------|
| 1 | Transcript preprocessing | Raw STT output is noisy. Without clean speaker separation and error correction, every downstream stage inherits garbage. |
| 2 | Verbatim extraction and coding | Qualitative research lives or dies on grounding claims in actual utterances. Codes are the atomic unit of all later analysis. |
| 3 | Behavioral sequence analysis | What users say and what they do often diverge. Timeline reconstruction captures observable behavior independent of self-report. |
| 4 | Emotional journey mapping | Kahneman's Peak-End Rule shows that memory of an experience is dominated by its emotional peak and final moments -- not the average. Tracking emotion over time identifies the moments that shape lasting impressions. |
| 5 | Empathy Map (NNG) | The Says/Thinks/Does/Feels quadrants force a structured comparison between surface statements and underlying experience. The cross-quadrant discrepancy analysis (e.g., Says vs Does) is where the real insights live. |
| 6 | Thematic analysis (Braun and Clarke) | The 6-phase method is the most widely cited qualitative analysis framework in social science. It provides a rigorous, reproducible path from raw codes to validated themes. |
| 7 | Affinity mapping | Where thematic analysis is theory-driven, affinity mapping is practical -- clustering insights by product relevance (feature, experience, value, need) for direct handoff to product teams. |
| 8 | Jobs-to-be-Done (Christensen) | Features are solutions. JTBD forces the question: what problem is the user actually hiring this product to solve? This reframes the entire analysis around user intent rather than product capability. |
| 9 | Proto-Persona (NNG) | Analysis results need to be memorable and shareable. A persona sketch turns abstract data into a character the team can reference in design reviews and sprint planning. |
| 10 | Mental model gap analysis (Norman) | When users struggle, the instinct is to blame the user. Norman's framework redirects: the system image failed to convey the correct conceptual model. This stage identifies where communication breaks down. |
| 11 | 7 Stages of Action (Norman) | The Gulf of Execution and Gulf of Evaluation provide a precise diagnostic for interaction failures -- pinpointing whether the user could not figure out what to do, or could not tell what happened after they did it. |
| 12 | 3 Levels of Processing (Norman) | Visceral, Behavioral, and Reflective processing operate on different timescales. A product can succeed at one level (beautiful UI) while failing at another (confusing interaction). This stage reveals the mix. |
| 13 | Hypothesis validation | Sprint-based product development runs on hypotheses. This stage closes the loop: did the data support what we assumed? Evidence-based verdicts prevent opinion-driven pivots. |
| 14 | Usability issues and Pain/Gain | Nielsen's 10 heuristics provide a shared severity language across teams. Pain/Gain analysis translates findings into prioritized action items for the next sprint. |

## Why This Order?

The pipeline follows a deliberate progression from raw data to actionable decisions:

```
Data Collection (1-2)
    ↓ Clean transcript, coded utterances
Observation Layer (3-4)
    ↓ What happened, how it felt
Synthesis Layer (5)
    ↓ Integrated user picture
Pattern Discovery (6-7)
    ↓ Themes and clusters
User Modeling (8-9)
    ↓ Jobs, persona
Interaction Diagnosis (10-12)
    ↓ Mental models, execution gaps, processing levels
Decision Layer (13-14)
    ↓ Validated hypotheses, prioritized issues
```

Each layer consumes the output of previous layers:

- Stage 5 (Empathy Map) pulls from Stage 2 (verbatim for Says), Stage 3 (behavior for Does), and Stage 4 (emotions for Feels).
- Stage 6 (Thematic Analysis) refines the codes generated in Stage 2.
- Stage 9 (Proto-Persona) synthesizes goals from Stage 8 (JTBD), behaviors from Stage 3, and pain points from Stage 14.
- Stage 13 (Hypothesis Validation) draws evidence from every preceding stage.

Reordering the stages would either require redundant work or produce analysis grounded in incomplete data.

## Why 14 and Not Fewer?

A valid concern. Each stage adds token cost and processing time. We tested consolidated versions (8-stage, 10-stage) during development and found:

- **8-stage version** (merging Norman's three frameworks into one): Lost the diagnostic precision of distinguishing mental model gaps from execution gaps from processing-level issues. Teams could not tell where to intervene.
- **10-stage version** (merging Thematic Analysis and Affinity Mapping): Produced clusters that were neither rigorous enough for research reports nor practical enough for sprint planning. Separating them serves both audiences.

The 14-stage version is the minimum set where removing any single stage produces a measurable gap in the analysis output.

For teams that need speed over depth, the Sprint Transcript Analyzer (`ut-transcript-analyzer.md`) provides a 6-tag analysis that completes in minutes.

## What Was Intentionally Excluded

| Method | Why Excluded |
|--------|-------------|
| Survey / quantitative methods | This toolkit analyzes qualitative transcripts. Quantitative data (if available) should be cross-validated separately. The interview guide template includes quantitative question slots for this purpose. |
| Contextual Inquiry | Requires in-situ observation -- watching users in their natural environment. Transcript-based analysis cannot capture physical context, workspace layout, or environmental interruptions. |
| Card sorting | A separate research method with its own session format. It does not map to the transcript-in, analysis-out pipeline. |
| Diary studies | Longitudinal data collection over days or weeks. Single-session transcript analysis cannot replicate this. Listed in the roadmap as a future agent. |
| A/B test interpretation | Requires quantitative experiment data, not qualitative transcripts. Also listed in the roadmap. |
| Cognitive walkthrough | Expert evaluation method that does not require user data. This toolkit is specifically for analyzing user-generated data. |

## Cross-User Analysis (C1-C8) Rationale

Individual analysis reveals what one user experienced. Cross-user analysis reveals what the product should do about it.

The 8 cross-analysis stages follow Dan Olsen's Lean Product Playbook progression:

1. **C1-C2** (Verbatim comparison, Hypothesis cross-validation): Establish what is consistent across users vs. what is idiosyncratic.
2. **C3-C4** (Theme mapping, Persona consolidation): Build shared models from individual data points.
3. **C5-C7** (Importance-Satisfaction Gap, PMF Pyramid, Kano Model): Apply product strategy frameworks to prioritize what to build, fix, or ignore.
4. **C8** (Actionable recommendations): Translate analysis into Problem Space vs. Solution Space actions with clear ownership.

This progression ensures that recommendations are grounded in cross-validated evidence rather than the loudest user's opinion.

## References

- Braun, V. and Clarke, V. (2006). Using thematic analysis in psychology. *Qualitative Research in Psychology*, 3(2), 77-101.
- Christensen, C. M. et al. (2016). *Competing Against Luck*. Harper Business.
- Kahneman, D. (2011). *Thinking, Fast and Slow*. Farrar, Straus and Giroux.
- Kano, N. et al. (1984). Attractive quality and must-be quality. *Journal of the Japanese Society for Quality Control*, 14(2), 39-48.
- Nielsen, J. (1994). *Usability Engineering*. Morgan Kaufmann.
- Norman, D. (2013). *The Design of Everyday Things* (Revised Edition). Basic Books.
- Norman, D. (2004). *Emotional Design*. Basic Books.
- Olsen, D. (2015). *The Lean Product Playbook*. Wiley.
