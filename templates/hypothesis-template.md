# Sprint Hypothesis Template

Use this template to define validation hypotheses for each UT sprint. Well-structured hypotheses make analysis significantly more rigorous and actionable.

## Sprint Information

| Item | Content |
|------|---------|
| Sprint | [Sprint N] |
| Date range | [Start -- End] |
| Sprint goal | [One sentence: what this sprint aims to learn] |

## Hypothesis Structure

Each hypothesis should follow this format:

```
H[N]: [Clear, testable statement]

Validation criteria:
- Validated if: [specific observable condition]
- Partially validated if: [specific observable condition]
- Refuted if: [specific observable condition]

Key metrics:
- [Quantitative metric + target]
- [Qualitative signal to look for]

Related UT tasks:
- [Which tasks in the UT session test this hypothesis]
```

## Hypotheses

### H1: [Hypothesis Statement]

**Full statement**: [Write a clear, falsifiable hypothesis. e.g., "Users who complete the personalization flow will express higher attachment to their results than users who receive default results."]

**Validation criteria**:
- Validated if: [e.g., "3/5+ users spontaneously express attachment language (possessive pronouns, desire to keep/protect)"]
- Partially validated if: [e.g., "Attachment signals present but only when prompted by interviewer"]
- Refuted if: [e.g., "Users show indifference to results regardless of personalization completion"]

**Key metrics**:
- Quantitative: [e.g., "Attachment score average 4.0/5.0+"]
- Qualitative: [e.g., "Spontaneous use of 'my', 'mine' when referring to results"]

**Related UT tasks**: [e.g., "Task 1: Complete personalization flow, Task 3: Review results"]

### H2: [Hypothesis Statement]

**Full statement**: [Next hypothesis]

**Validation criteria**:
- Validated if: [condition]
- Partially validated if: [condition]
- Refuted if: [condition]

**Key metrics**:
- Quantitative: [metric + target]
- Qualitative: [signal to observe]

**Related UT tasks**: [task references]

### H3: [Hypothesis Statement]

**Full statement**: [Next hypothesis]

**Validation criteria**:
- Validated if: [condition]
- Partially validated if: [condition]
- Refuted if: [condition]

**Key metrics**:
- Quantitative: [metric + target]
- Qualitative: [signal to observe]

**Related UT tasks**: [task references]

## Hypothesis Quality Checklist

Before finalizing, verify each hypothesis against these criteria:

- [ ] **Testable**: Can this be validated or refuted with observable data from the UT session?
- [ ] **Specific**: Does it specify what behavior, utterance, or metric to look for?
- [ ] **Falsifiable**: Is it possible for the data to refute this hypothesis?
- [ ] **Non-leading**: Does it not presuppose a desired outcome?
- [ ] **Scoped**: Can it be tested within a single sprint's UT sessions?
- [ ] **Independent**: Can it be validated independently of other hypotheses?

## Writing Good Hypotheses

### Strong examples

- "Users will attempt to drag-and-drop items in the list view before discovering the edit button" (specific, observable, falsifiable)
- "First-time users will interpret the 'workspace' concept as a folder structure" (tests mental model, observable through behavior)
- "Users who spend 5+ minutes in the customization flow will score 4.0+ on attachment" (quantifiable, testable)

### Weak examples (avoid these)

- "Users will like the new feature" (too vague, not falsifiable)
- "The UX is intuitive" (not specific, not observable)
- "Users prefer our product over competitors" (not testable in a single UT session)

## Sprint Context

### Connection to Previous Sprint

- What did the previous sprint's UT reveal?
- Which hypotheses from the last sprint need follow-up?
- What new questions emerged from the last round of testing?

### Connection to Product Roadmap

- How do these hypotheses connect to upcoming product decisions?
- What will change in the product if H1 is validated vs. refuted?
- What will change if H2 is validated vs. refuted?

## Interpretation Guide

After UT completion, use this framework to interpret results:

| Outcome | H1 | H2 | H3 | Implication |
|---------|----|----|-----|-------------|
| Scenario A | Validated | Validated | Validated | [What this means, what to build next] |
| Scenario B | Validated | Refuted | Partial | [What this means, what to investigate] |
| Scenario C | Refuted | Validated | Validated | [What this means, what to pivot] |
| Scenario D | Refuted | Refuted | Refuted | [What this means, fundamental rethink needed] |
