# UX Research Agents

**AI-powered UX research analysis toolkit** — Turn raw user test transcripts into structured, evidence-based insights using proven UX methodologies.

Built with [Claude Code](https://claude.ai/claude-code) agents. Battle-tested on 50+ real user interviews across multiple product sprints.

<p align="center">
  <img src="docs/images/overview-diagram.png" alt="UX Research Agents Overview" width="800">
</p>

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Claude Code](https://img.shields.io/badge/Built%20with-Claude%20Code-blueviolet)](https://claude.ai/claude-code)

---

## Why This Exists

UX researchers spend **60-70% of their time** on analysis and synthesis — not research itself. Commercial tools (Dovetail, Maze, Marvin) cost $100-500/month and still require manual work.

This toolkit automates the heavy lifting:

- **Raw transcript in** → **Structured analysis out** (in minutes, not days)
- **14 proven UX methodologies** applied systematically
- **Evidence-based**: Every insight links back to exact user quotes with timestamps
- **No hallucination**: Strict rules against speculation — if there's no evidence, it says so

## What's Inside

### 1. Deep Research Analyzer (`agents/ut-research-analyzer.md`)

A comprehensive 14-stage analysis pipeline that applies established UX research frameworks to raw interview transcripts.

**Individual User Analysis (14 Stages):**

| Stage | Method | Framework |
|-------|--------|-----------|
| 1 | Transcript preprocessing & speaker identification | — |
| 2 | Verbatim extraction & semantic coding | Qualitative coding (14 rules) |
| 3 | Behavioral sequence analysis | Timeline mapping |
| 4 | Emotional journey mapping | Peak-end analysis |
| 5 | Empathy Map | NNG Says/Thinks/Does/Feels |
| 6 | Thematic analysis | Braun & Clarke 6-phase |
| 7 | Affinity mapping | Cluster by type |
| 8 | Jobs-to-be-Done analysis | JTBD framework |
| 9 | Proto-Persona sketch | NNG methodology |
| 10 | Mental model gap analysis | Don Norman |
| 11 | 7 Stages of Action analysis | Don Norman |
| 12 | 3 Levels of Processing | Don Norman (Visceral/Behavioral/Reflective) |
| 13 | Hypothesis validation | Evidence-based mapping |
| 14 | Usability issues & Pain/Gain | Nielsen's 10 heuristics |

**Cross-User Analysis (8 Stages):**

| Stage | Method | Framework |
|-------|--------|-----------|
| C1 | Verbatim cross-comparison | — |
| C2 | Hypothesis cross-validation | — |
| C3 | Theme cross-mapping | Universal/Major/Segment/Unique |
| C4 | Persona consolidation | 2-3 representative personas |
| C5 | Importance-Satisfaction Gap | Lean Product Playbook |
| C6 | PMF Pyramid mapping | 5-layer product-market fit |
| C7 | Kano Model classification | Must-be/Performance/Delighter |
| C8 | Actionable recommendations | Problem vs Solution space |

### 2. Sprint Transcript Analyzer (`agents/ut-transcript-analyzer.md`)

Fast, hypothesis-driven analysis for sprint retrospectives. Auto-tags every utterance and validates sprint hypotheses.

**6 Semantic Tags:**

| Tag | Meaning | Example |
|-----|---------|---------|
| `[PAIN]` | Frustration, complaint, negative emotion | "The options are too limited" |
| `[AHA]` | Positive surprise, engagement, delight | "I didn't expect to get so into this" |
| `[WTP]` | Willingness to pay, recommend, reuse | "At $3, I'd consider it" |
| `[BEHAV]` | Observable behavior (hesitation, repeated exploration, skip) | Timestamped observations |
| `[NEED]` | Feature request, improvement suggestion | "It would be nice if it had..." |
| `[COMP]` | Competitor/existing service comparison | "Bubble does X, but this..." |

**Auto-generates:**
- Tagged utterance report
- Hypothesis validation (Validated / Partially Validated / Rejected / Insufficient Data)
- UX vs Functional Architecture issue classification
- Next sprint action items (max 3)

### 3. UT Auto-Summary Prompt (`prompts/ut-auto-summary.md`)

Lightweight prompt for quick Slack-ready sprint retrospective summaries. No agent setup required — paste into any LLM.

## Quick Start

### Prerequisites

- [Claude Code CLI](https://docs.anthropic.com/en/docs/claude-code) installed
- Interview transcripts (from Clova Note, Otter.ai, or any STT tool)

### Installation

```bash
# Clone the repo
git clone https://github.com/Lee-Soyeon/ux-research-agents.git

# Copy agents to your Claude Code config
cp ux-research-agents/agents/*.md ~/.claude/agents/
```

### Usage

**Deep analysis (14-stage):**
```
# In Claude Code, invoke the agent:
@ut-research-analyzer Analyze /path/to/transcript.txt
Hypotheses: "Users will form emotional attachment through the onboarding flow"
```

**Sprint analysis (quick):**
```
@ut-transcript-analyzer Analyze /path/to/transcript.txt
Hypothesis: "The new casting flow increases user engagement"
```

**Standalone prompt (any LLM):**
Copy `prompts/ut-auto-summary.md` and paste into ChatGPT, Claude, or any LLM with your transcript.

## Example Output

<details>
<summary>Click to see sample analysis output</summary>

```markdown
# Sprint 2 - UT Sprint Summary: User #8

> Testing scope: Casting flow + relationship setting + content consumption

## User Info
- 24F, college student, K-pop fan (BTS), no AI product experience
- Segment: A (Fan-oriented)

## 0. One-line Key Finding
- Casting flow successfully created emotional attachment,
  but content consumption did not convert to payment intent.

## 1. Tagged Key Utterances

### [PAIN]
> "I don't really get what this button does" (03:42)

### [AHA]
> "Wait, this actually feels like my own group" (08:15)

### [WTP]
> "Maybe if it were $3... I'd think about it" (22:30)

## 2. Hypothesis Validation

**H1: Casting creates emotional attachment**
**Verdict: Validated**

| Axis | Verdict | Evidence |
|------|---------|----------|
| Emotional response | Present | "feels like my own group" (08:15) |
| Time spent | Present | 4min on casting (above average) |
| Return intent | Present | "I'd come back to check on them" (25:10) |
```

</details>

## Methodology References

This toolkit is built on established UX research frameworks:

- **Nielsen Norman Group (NNG)**: Empathy Mapping, Persona Development, Usability Heuristics
- **Don Norman**: Mental Model Gap Analysis, 7 Stages of Action, 3 Levels of Emotional Design
- **Braun & Clarke**: Thematic Analysis (6-phase)
- **Dan Olsen**: Lean Product Playbook, Importance-Satisfaction Gap, PMF Pyramid
- **Clayton Christensen**: Jobs-to-be-Done
- **Noriaki Kano**: Kano Model

## Project Structure

```
ux-research-agents/
├── agents/                          # Claude Code agents
│   ├── ut-research-analyzer.md      # 14-stage deep analysis (1,200+ lines)
│   └── ut-transcript-analyzer.md    # Sprint-level quick analysis
├── prompts/                         # Standalone prompts (works with any LLM)
│   └── ut-auto-summary.md           # Quick summary prompt
├── examples/                        # Sample transcripts and outputs
│   ├── sample-transcript.md         # Anonymized sample input
│   └── sample-analysis-output.md    # What the output looks like
├── docs/                            # Documentation
│   ├── methodology-guide.md         # Deep dive into each methodology
│   ├── customization-guide.md       # How to adapt for your product
│   └── images/                      # Diagrams and screenshots
├── templates/                       # Reusable templates
│   ├── ut-interview-guide.md        # Interview guide template
│   └── hypothesis-template.md       # Sprint hypothesis template
└── README.md
```

## Roadmap

- [x] Core analysis agents (14-stage + sprint-level)
- [x] Standalone prompt for any LLM
- [ ] PostHog session replay AI analysis agent
- [ ] Playwright-based automated UX testing agent
- [ ] Hotjar/FullStory session replay analysis
- [ ] Multi-language support (currently Korean-optimized, English WIP)
- [ ] Video/screen recording analysis (mp4 → UX insights)
- [ ] Integration with Notion/Linear for issue tracking

## Who Is This For

- **UX Researchers** who want to speed up analysis without losing rigor
- **Product Managers** who need evidence-based sprint retrospectives
- **Startup Founders** running lean user tests with limited resources
- **Students & Educators** learning UX research methodologies through practice
- **Anyone** who interviews users and needs structured insights fast

## Contributing

Contributions welcome! See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

Some ways to contribute:
- Add new analysis methodologies
- Share anonymized example transcripts
- Improve multi-language support
- Build integrations with other tools (PostHog, Hotjar, Maze)
- Report issues or suggest improvements

## About

Built by [Soyeon Lee](https://github.com/Lee-Soyeon), CEO @ [AIoIA](https://aioia.ai) — from real pain of analyzing 50+ user interviews across multiple product discovery sprints.

This toolkit was born from the belief that **rigorous UX research shouldn't require expensive tools or weeks of manual analysis**. Every framework and rule in these agents comes from hands-on experience running user tests and iterating on products.

## License

MIT License — use it, modify it, share it.

---

**If this saves you time on your next user test, consider giving it a star!**
