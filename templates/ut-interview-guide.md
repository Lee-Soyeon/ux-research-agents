# UT Interview Guide Template

A reusable template for planning and conducting usability test interviews. Adapt each section to your specific sprint, product, and hypotheses.

## 1. UT Design Purpose

Define 3-4 core questions this UT session aims to answer:

1. [Core question 1 -- e.g., "Do users understand the new feature without guidance?"]
2. [Core question 2 -- e.g., "Does the feature create measurable engagement?"]
3. [Core question 3 -- e.g., "What is the willingness to pay for this capability?"]
4. [Core question 4 -- e.g., "Does the experience differ by user segment?"]

Key focus: [State the single most important thing you want to learn]

## 2. Participants

### 2.1 Target Audience

- [Describe who should participate -- demographics, experience level, relationship with the product]
- Minimum number of participants: [recommend 5-10 for qualitative studies]

### 2.2 Segments

| Segment | Description | Target Count |
|---------|-------------|-------------|
| A. [Segment name] | [Key characteristics -- e.g., power users, daily active] | [N] |
| B. [Segment name] | [Key characteristics -- e.g., new users, first-time visitors] | [N] |
| C. [Segment name] | [Key characteristics -- e.g., lapsed users, general population] | [N] |

Include at least one general/non-target segment to avoid positive bias from testing only power users.

### 2.3 Recruiting Channels

- [Channel 1 -- e.g., in-app recruitment banner]
- [Channel 2 -- e.g., social media communities]
- [Channel 3 -- e.g., existing user database outreach]
- [Channel 4 -- e.g., user research panel service]

## 3. Interview Structure

### 3.1 Session Flow (approximately 30 minutes)

| Phase | Duration | Content |
|-------|----------|---------|
| Intro | 3 min | Self-introduction, explain interview purpose, obtain recording consent |
| Usage exploration | 7 min | Free-form conversation about service experience |
| Core questions (quantitative) | 10 min | PMF, NPS, WTP, and other scaled measures |
| Deep-dive questions (qualitative) | 8 min | Core value, churn risk, sharing motivation |
| Wrap-up | 2 min | Additional thoughts, thank the participant |

## 4. Validation Hypotheses

Define the hypotheses this sprint's UT aims to validate:

- H1: [Hypothesis text -- e.g., "Users who complete onboarding customization show higher retention intent"]
- H2: [Hypothesis text]
- H3: [Hypothesis text]

## 5. Quantitative Questions (Core Metric Measurement)

Ask these in order during the interview. Record responses immediately.

### 5.1 PMF (Sean Ellis Test)

> "If you could no longer use this service, how would you feel?"

| Option | Check |
|--------|-------|
| Very disappointed | |
| Somewhat disappointed | |
| Not disappointed | |
| N/A (don't use it) | |

Target: 40%+ "Very disappointed" responses

### 5.2 Reuse Intent

> "I want to continue using this service"

1 (Strongly disagree) -- 5 (Strongly agree): ___

Target: Average 4.0/5.0 or higher

### 5.3 Sharing Intent

> "I want to show my experience with this service to others"

1 (Strongly disagree) -- 5 (Strongly agree): ___

Target: Average 4.0/5.0 or higher

### 5.4 NPS (Net Promoter Score)

> "How likely are you to recommend this service to a friend, on a scale of 0 to 10? 0 means not at all, 10 means extremely likely."

Score: ___ / 10

Calculation:
- Promoter: 9-10
- Passive: 7-8
- Detractor: 0-6
- NPS = (Promoter %) - (Detractor %)

Target: NPS 30 or higher

### 5.5 Willingness to Pay

> "If [specific premium feature] were available at [price range] per month, would you subscribe?"

| Option | Check |
|--------|-------|
| Yes | |
| Maybe | |
| No | |

Follow-up: "What price would feel fair to you?" (free input): $___/month

Target: 10%+ "Yes" responses

## 6. Qualitative Questions (Deep Exploration)

Transition naturally from quantitative questions. Let respondents speak freely.

### 6.1 Core Value

- "What did you like most about this service?"
- "What would you say is the best thing about it?"
- (When they mention a specific feature) "Why did you like that?"

### 6.2 Improvement Areas

- "What would need to improve for you to use it more often?"
- "Was there anything frustrating or confusing?"

### 6.3 Churn Risk

- "If you were to stop using this, what would be the reason?"
- "What's the one thing this service absolutely must not lose?"

### 6.4 Sharing Motivation

- "Who would you show this to? Why?"
- "If you posted about it on social media, what would you say?"

### 6.5 Perceived Value

- "If you were to pay for this, which feature would you pay for?"
- "Is there any part of the current service you feel is worth paying for?"

### 6.6 Domain-Specific Questions

- [Add 2-3 questions specific to your product domain]
- [e.g., for a learning app: "Did you feel like you were actually learning something?"]
- [e.g., for a social app: "Did you feel a connection with other users?"]

## 7. Interviewer Guidelines

1. **Do not lead**: Avoid leading questions like "This is good, right?" Use open questions: "How did that feel?"
2. **Allow silence**: Give respondents time to think. Do not rush to the next question.
3. **Probe with "why"**: After surface-level answers, ask "Why did you feel that way?" at least once.
4. **Record everything**: Obtain consent, then record. Essential for post-session analysis.
5. **Note the segment**: Always record which segment (A/B/C) the participant belongs to.
6. **Watch for body language**: Note sighs, laughter, leaning in, looking away -- these are data too.
7. **Track interviewer influence**: Be self-aware of moments you may have influenced a response.

## 8. Recording Sheet Template

```
Interview date: ____-__-__ __:__
Interviewer:
Participant ID:
Segment: A / B / C

[Quantitative]
5.1 PMF: Very disappointed / Somewhat / Not / N/A
5.2 Reuse intent: __ /5
5.3 Sharing intent: __ /5
5.4 NPS: __ /10
5.5 WTP: Yes / Maybe / No
    Fair price: $___/month

[Qualitative Notes]
Core value:
Improvement areas:
Churn risk:
Sharing motivation:
Perceived value:
Domain-specific:

[Notable Observations / Key Utterances]

```

## 9. Results Aggregation

### 9.1 Quantitative Data

| Metric | Calculation | Target | Purpose |
|--------|-------------|--------|---------|
| PMF | "Very disappointed" count / total (excluding N/A) | 40%+ | Sean Ellis PMF benchmark |
| NPS | (9-10 %) - (0-6 %) | 30+ | Recommendation strength |
| Reuse intent | 5-point average | 4.0+ | Product satisfaction |
| Sharing intent | 5-point average | 4.0+ | Viral potential |
| WTP | "Yes" response rate | 10%+ | Monetization viability |

### 9.2 Qualitative Data

- Extract quotable key utterances (verbatim)
- Analyze differences by segment
- Compare with previous sprint UT results if available

### 9.3 Behavioral Data Cross-Validation

If available, compare interview responses with analytics data:
- Do users who said "good" in the interview actually use the feature frequently?
- Do users who expressed high sharing intent actually use share functionality?
- Behavioral pattern differences between interview respondents and non-respondents

## 10. Result Interpretation Scenarios

Define expected signal patterns and what they mean:

**Signal Pattern A: [Label -- e.g., "Passive consumption"]**
- [Condition 1 -- e.g., High satisfaction, low sharing intent]
- [Condition 2 -- e.g., Low WTP]
- [Condition 3 -- e.g., Low reuse intent]
- Implication: [What this means for the product]

**Signal Pattern B: [Label -- e.g., "Active engagement potential"]**
- [Condition 1 -- e.g., High engagement scores 4.0+]
- [Condition 2 -- e.g., Specific feature attachment]
- [Condition 3 -- e.g., WTP present at meaningful rate]
- Implication: [What this means for the product]
