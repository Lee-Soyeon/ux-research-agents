# UT Deep Analysis Prompt

A standalone prompt for any LLM to perform a comprehensive 14-stage UX research analysis on a usability test transcript. No agent setup required -- copy and paste this prompt along with your transcript.

## How to Use

1. Transcribe your UT recording to text (using any STT tool: Otter.ai, Rev, Whisper, Clova Note, etc.)
2. Replace `[INSERT YOUR HYPOTHESES HERE]` with your sprint's validation hypotheses
3. Paste the prompt + transcript into your LLM of choice

**Important**: This is a long analysis. Depending on your transcript length and LLM context window:
- **Short interviews (under 15 min)**: Paste everything in one go
- **Long interviews (15-60 min)**: Use Part 1 first, then Part 2 with the Part 1 output as context
- **Very long interviews (60+ min)**: Split the transcript into chunks and run Part 1 on each chunk, then combine

## Part 1: Data Extraction and Observation (Stages 1-7)

```
You are a UX research analysis expert. Analyze this usability test transcript using 7 established UX research methodologies in sequence.

[Analysis Premise]
This UT was conducted to validate the following hypotheses:
[INSERT YOUR HYPOTHESES HERE]

Critical Principles:
- All analysis must be grounded in user's actual utterances (verbatim). Quote the original text.
- No speculation. If there is no evidence, write "No evidence."
- All quotes must include the original timestamp.
- Mark whether each utterance was prompted by the interviewer or spontaneous.
- No subjective language. Instead of "seemed interested," describe specific behaviors and utterances.
- Distinguish between analyst interpretation [Inference] and user utterances.
- No emojis. Use hierarchical numbering.

Output the following stages in order:

--------------------------------------------

STAGE 1: PREPROCESSING

1.1 Speaker Identification
- Identify interviewer vs participant from transcript format
- Calculate speaking ratio per speaker

1.2 Participant Profile
- Age, gender, occupation (extract from early portion)
- Experience level with the product domain
- User segment classification

1.3 STT Error Log
- Only errors that change semantic meaning
- Format: Original | Estimated correction | Rationale

--------------------------------------------

STAGE 2: VERBATIM EXTRACTION AND CODING

Extract ALL meaningful utterances in this format:

| ID | Timestamp | Speaker | Verbatim | Initial Code | Context | Prompted? |

Extraction criteria -- extract utterances matching any of:
- Emotional expressions (surprise, joy, disappointment, confusion, frustration)
- Evaluative statements (any value judgment)
- Comparative statements (comparing with other services)
- Desire/expectation expressions ("I wish...", "It would be nice if...")
- Behavioral descriptions (explaining their own actions)
- Metaphors/analogies
- Spontaneous suggestions
- Resistance/rejection
- WTP (willingness to pay, pricing, value mentions)
- Mental model expressions ("Isn't this supposed to...?")
- Expectation mismatches

Rules:
- A single utterance may receive multiple codes
- Codes are generated inductively from data
- Extract minimum 15 utterances
- Include surrounding context for long utterances

--------------------------------------------

STAGE 3: BEHAVIORAL SEQUENCE ANALYSIS

3.1 Behavioral Timeline
| Segment | Time | Task | User Behavior (Observed) | Key Utterance | Duration | Notes |

3.2 Behavioral Patterns
- Exploration pattern, decision-making pattern, repetitive behavior
- Drop-off points and engagement peaks

3.3 Task Success/Failure Log
- Completion status, help requests, errors, actual vs expected time

--------------------------------------------

STAGE 4: EMOTIONAL JOURNEY MAPPING

4.1 Emotion Tracking
| Time | Segment | Emotion Level (--/-/0/+/++) | Emotion Label | Evidence |

4.2 Emotional Turning Points
- Moments of significant emotional change and their triggers
- Positive-to-negative and negative-to-positive transitions

4.3 Peak-End Analysis (Kahneman)
- Peak moment: strongest emotional reaction
- End moment: emotional state at interview end
- Implication for how the experience will be remembered

--------------------------------------------

STAGE 5: EMPATHY MAP (NNG)

5.1 Says: Representative verbatim utterances (direct quotes only)
5.2 Thinks: Inferred thoughts -- label [Inference], cite evidence
5.3 Does: Observable behaviors from Stage 3 (no interpretation)
5.4 Feels: Key emotions from Stage 4 (adjective + context)
5.5 Cross-Quadrant Discrepancy Analysis:
- Says vs Does: features praised but not used?
- Says vs Thinks: social desirability distortion?
- Thinks vs Feels: logically understood but emotionally rejected?

--------------------------------------------

STAGE 6: THEMATIC ANALYSIS (Braun and Clarke 6-Phase)

Phase 1: Re-read all verbatim, observe patterns
Phase 2: Refine initial codes -- merge similar, split broad
| Code | Associated Verbatim IDs | Count |
Phase 3: Group codes into themes
| Theme | Sub-codes | Representative Utterance | Count |
Phase 4: Review each theme for data support, internal consistency, distinctness
Phase 5: Define each final theme:
- One-sentence definition
- Core insight
- Minimum 3 representative utterances
Phase 6: Theme map -- how themes relate, central vs peripheral

--------------------------------------------

STAGE 7: AFFINITY MAPPING

7.1 Extract practical insights:
| Insight ID | Insight | Source Verbatim ID | Cluster |

7.2 Cluster by: Feature-related / Experience-related / Value-related / Needs-related

7.3 Per cluster: name, insight count, key verbatim (minimum 2), product implications
```

## Part 2: Modeling and Decision (Stages 8-14)

Use this after completing Part 1. Include Part 1 output as context.

```
Continue the UX research analysis using the verbatim extractions, behavioral data, and themes from Part 1. Apply Stages 8-14.

--------------------------------------------

STAGE 8: JOBS-TO-BE-DONE (Christensen)

8.1 Job Statements:
"When I [situation], I want to [motivation], so I can [expected outcome]"

8.2 Job Types: Functional / Emotional / Social

8.3 Job Fulfillment:
| Job | Type | Fulfillment (Fulfilled/Partial/Unfulfilled) | Evidence | Improvement Direction |

--------------------------------------------

STAGE 9: PROTO-PERSONA SKETCH (NNG)

9.1 Identity and Context (from Stage 1)
9.2 Goals and Motivations (from Stage 8 JTBD)
9.3 Behaviors and Patterns (from Stage 3)
9.4 Pain Points and Frustrations (with verbatim and severity)
9.5 Attitudes and Quotes (3-5 most representative utterances)
9.6 Tagline (one-sentence summary of this user)

--------------------------------------------

STAGE 10: MENTAL MODEL GAP ANALYSIS (Don Norman)

10.1 Mental Model Extraction:
| ID | Utterance/Behavior | User's Mental Model | Actual System Behavior | Match/Mismatch |

Signals: confirmation questions, expectation mismatches, wrong interactions, analogies to other services

10.2 Gap Types: Functional / Flow / Value / Scope

10.3 Metaphor/Analogy Analysis:
- What did the user compare the service to?
- What mental model does that analogy imply?

10.4 Gap Resolution: System change or communication change?
Principle: "The system image must convey the correct conceptual model" (Norman)

--------------------------------------------

STAGE 11: NORMAN'S 7 STAGES OF ACTION

For each major task, create a table with columns for "Stage", "Observation", and "Problem?". The rows should correspond to the 7 stages of action: Goal, Plan, Specify, Perform, Perceive, Interpret, and Compare.

Identify:
- Gulf of Execution: user could not translate intent into action
- Gulf of Evaluation: user could not understand system state

--------------------------------------------

STAGE 12: NORMAN'S 3 LEVELS OF PROCESSING

12.1 Visceral: First impressions, visual/sensory reactions
12.2 Behavioral: Usability, efficiency, flow during use
12.3 Reflective: Meaning-making, self-image, long-term value

| Verbatim ID | Target | Reaction | Positive/Negative |

Summary: Which level produced the strongest response? Is the product succeeding at all 3 levels?

--------------------------------------------

STAGE 13: HYPOTHESIS VALIDATION

For each hypothesis:

### H[N]: [Hypothesis text]
**Verdict**: Validated / Partially validated / Not validated / Refuted

**Supporting Evidence**
- [Verbatim ID] "[quote]" (timestamp) -- spontaneous/prompted

**Counter Evidence**
- [Verbatim ID] "[quote]" (timestamp) -- spontaneous/prompted

**Verdict Rationale**
- Supporting vs counter utterance count
- Spontaneous vs prompted ratio
- Behavior-utterance alignment

**Conditions and Nuances**

Emergent Findings: New patterns not covered by hypotheses

--------------------------------------------

STAGE 14: USABILITY ISSUES AND PAIN/GAIN

14.1 Usability Issues (Nielsen's 10 Heuristics):
| ID | Screen/Feature | Issue | Heuristic | Severity (1-4) | Utterance | UX Copy vs Structural |

Nielsen's 10: (1) System status visibility (2) Real-world match (3) User control (4) Consistency (5) Error prevention (6) Recognition > recall (7) Flexibility (8) Minimalist design (9) Error recovery (10) Help/docs

Severity: 1=Cosmetic, 2=Minor, 3=Major, 4=Catastrophic

14.2 Pain Points:
| Pain | Severity | Frequency | Utterance | Resolution Direction |

14.3 Gains:
| Gain | Intensity (+/++) | Utterance | Reinforcement Direction |

--------------------------------------------

FINAL SUMMARY

Top 5 Key Insights:
- Insight (one sentence)
- Source methodology
- Representative utterance
- Product implications

Cognitive Map: Text diagram of how the user understands the service

Next Sprint Suggestions (maximum 3): suggestion, evidence, priority (P0/P1/P2)

Items Requiring Follow-Up Validation

--------------------------------------------

Mark the output as: "AI-assisted analysis -- review by a qualified researcher recommended before sharing with stakeholders."
```

## Tips

- **Quality depends on transcript quality**: Clean, timestamped transcripts with clear speaker labels produce the best results.
- **Provide hypotheses**: Without hypotheses, Stage 13 cannot run. If you do not have formal hypotheses, write 2-3 assumptions you want to test.
- **Review before sharing**: LLM analysis can miss cultural nuance, tonal subtlety, and non-verbal cues. Always review AI-generated codes and themes against your own reading of the transcript.
- **Cross-user analysis**: This prompt analyzes one user at a time. For cross-user synthesis, run this on each transcript individually, then use the Cross-User Analysis stages from the full agent.
