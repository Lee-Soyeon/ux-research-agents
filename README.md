# UX Research Agents

![License](https://img.shields.io/badge/License-MIT-green?style=flat-square) ![Claude Code](https://img.shields.io/badge/Claude_Code-Agent-7c3aed?style=flat-square)

AI-powered UX research analysis toolkit that turns raw user test transcripts into structured, evidence-based insights. It applies 14 proven UX methodologies systematically — from verbatim coding to Kano Model classification — so you spend minutes instead of hours on each interview. Built as [Claude Code](https://claude.ai/claude-code) agents, battle-tested on 50+ real user interviews.

**Read the [agents](#whats-inside) to get started.**

<img src="https://github.com/user-attachments/assets/placeholder-demo" alt="Demo" width="700"/>

<!-- TODO: Replace with actual demo GIF showing analysis in action -->

## Get started

### Prerequisites

- [Claude Code CLI](https://docs.anthropic.com/en/docs/claude-code) installed
- Interview transcripts from any STT tool (Otter.ai, Whisper, Clova Note, etc.)

### Installation

```bash
git clone https://github.com/Lee-Soyeon/ux-research-agents.git

# Copy agents to your Claude Code config
cp ux-research-agents/agents/*.md ~/.claude/agents/
```

### Usage

Deep analysis (14-stage):

```
@ut-research-analyzer Analyze /path/to/transcript.txt
Hypotheses: "Users will complete onboarding without help"
```

Sprint analysis (quick):

```
@ut-transcript-analyzer Analyze /path/to/transcript.txt
Hypothesis: "The new search flow increases task completion rate"
```

The standalone prompt in `prompts/ut-auto-summary.md` works with any LLM — copy-paste it into ChatGPT, Claude, or Gemini with your transcript.

> [!TIP]
> Start with the Sprint Transcript Analyzer for quick results, then use the Deep Research Analyzer when you need comprehensive insights.

## What's inside

### 1. Deep Research Analyzer

`agents/ut-research-analyzer.md` — 1,200+ lines

A 14-stage analysis pipeline that applies established UX research frameworks to raw interview transcripts:

| Stage | Method | Framework |
|:------|:-------|:----------|
| 1 | Transcript preprocessing & speaker identification | — |
| 2 | Verbatim extraction & semantic coding | Qualitative coding (14 rules) |
| 3 | Behavioral sequence analysis | Timeline mapping |
| 4 | Emotional journey mapping | Peak-end analysis (Kahneman) |
| 5 | Empathy Map | NNG Says/Thinks/Does/Feels |
| 6 | Thematic analysis | Braun & Clarke 6-phase |
| 7 | Affinity mapping | Cluster by type |
| 8 | Jobs-to-be-Done analysis | JTBD (Christensen) |
| 9 | Proto-Persona sketch | NNG methodology |
| 10 | Mental model gap analysis | Don Norman |
| 11 | 7 Stages of Action | Don Norman |
| 12 | 3 Levels of Processing | Don Norman |
| 13 | Hypothesis validation | Evidence-based mapping |
| 14 | Usability issues & Pain/Gain | Nielsen's 10 heuristics |

When you have multiple users analyzed, run **Cross-User Analysis** (8 additional stages) to consolidate:

| Stage | Method | Framework |
|:------|:-------|:----------|
| C1 | Verbatim cross-comparison | Pattern matching |
| C2 | Hypothesis cross-validation | Evidence aggregation |
| C3 | Theme cross-mapping | Universal / Major / Segment / Unique |
| C4 | Persona consolidation | 2-3 representative personas |
| C5 | Importance-Satisfaction Gap | Lean Product Playbook (Dan Olsen) |
| C6 | PMF Pyramid mapping | 5-layer product-market fit |
| C7 | Kano Model classification | Must-be / Performance / Delighter |
| C8 | Actionable recommendations | Problem Space vs Solution Space |

### 2. Sprint Transcript Analyzer

`agents/ut-transcript-analyzer.md`

Fast, hypothesis-driven analysis for sprint retrospectives. Tags every user utterance with 6 semantic labels:

| Tag | Meaning | Example |
|:----|:--------|:--------|
| `[PAIN]` | Frustration, complaint | "The options are too limited" |
| `[AHA]` | Positive surprise, delight | "I didn't expect to get so into this" |
| `[WTP]` | Willingness to pay/reuse | "At $3, I'd consider it" |
| `[BEHAV]` | Observable behavior | Hesitation at 03:42, repeated exploration |
| `[NEED]` | Feature request | "It would be nice if it had..." |
| `[COMP]` | Competitor comparison | "Notion does X, but this..." |

Generates hypothesis validation verdicts: **Validated** / **Partially Validated** / **Rejected** / **Insufficient Data**, plus UX vs Functional Architecture issue classification and next sprint actions (max 3).

### 3. Standalone Prompt

`prompts/ut-auto-summary.md`

A lightweight prompt for Slack-ready sprint retrospective summaries. No agent setup required — paste into any LLM.

## Example output

<details>
<summary>Sample analysis output</summary>

```markdown
# Sprint 2 - UT Sprint Summary: User #8

> Testing scope: Onboarding flow + task creation + dashboard comprehension

## User Info
- 24F, college student, no prior experience with this product category
- Segment: New User

## 0. One-line Key Finding
- Onboarding successfully built initial understanding,
  but dashboard complexity caused confusion and reduced task completion.

## 1. Tagged Key Utterances

### [PAIN]
> "I don't really get what this button does" (03:42)
> "There are too many things on this screen" (11:20)

### [AHA]
> "Oh wait, this actually makes sense now" (08:15)

### [WTP]
> "If it saved me this much time every week... maybe $5/month?" (22:30)

## 2. Hypothesis Validation

**H1: Users complete onboarding without assistance**
**Verdict: Partially Validated**

| Axis            | Verdict | Evidence                               |
|-----------------|---------|----------------------------------------|
| Task completion | Present | Completed 4/5 steps independently      |
| Comprehension   | Weak    | "What does this icon mean?" (05:12)    |
| Satisfaction    | Present | "That was pretty straightforward" (07:45) |

## 3. Usability Issues

| Screen    | Issue                   | Heuristic                | Severity |
|-----------|-------------------------|--------------------------|----------|
| Dashboard | Icon meaning unclear    | Recognition > Recall     | 3/4      |
| Settings  | No confirmation on save | System Status Visibility | 2/4      |
```

</details>

## Methodology

Built on established, peer-reviewed UX research frameworks:

- **Nielsen Norman Group** — Empathy Mapping, Persona Development, Usability Heuristics
- **Don Norman** — Mental Model Gap Analysis, 7 Stages of Action, 3 Levels of Emotional Design
- **Braun & Clarke** — 6-Phase Thematic Analysis
- **Dan Olsen** — Lean Product Playbook, Importance-Satisfaction Gap, PMF Pyramid
- **Clayton Christensen** — Jobs-to-be-Done
- **Noriaki Kano** — Kano Model
- **Daniel Kahneman** — Peak-End Rule

## Project structure

```
ux-research-agents/
├── agents/
│   ├── ut-research-analyzer.md      # 14-stage deep analysis (1,200+ lines)
│   └── ut-transcript-analyzer.md    # Sprint-level quick analysis
├── prompts/
│   └── ut-auto-summary.md           # Standalone prompt for any LLM
├── examples/
│   └── sample-transcript.md         # Fictional sample interview
├── templates/
│   ├── ut-interview-guide.md        # Interview guide template
│   └── hypothesis-template.md       # Sprint hypothesis template
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

## Roadmap

- [x] Core analysis agents (14-stage + sprint-level)
- [x] Cross-user analysis (8-stage, Lean Product Playbook)
- [x] Standalone prompt for any LLM
- [x] Interview guide & hypothesis templates
- [ ] PostHog session replay AI analysis
- [ ] Playwright-based automated UX testing
- [ ] Video/screen recording analysis (mp4 to UX insights)
- [ ] Multi-language transcript support
- [ ] Integration with Notion/Linear for issue tracking

## Contributing

Contributions welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## About

Built by [Soyeon Lee](https://github.com/Lee-Soyeon) from real pain of analyzing 50+ user interviews across multiple product discovery sprints.

## License

[MIT](LICENSE)
