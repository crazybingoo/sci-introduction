---
name: sci-introduction
description: Diagnose, plan, draft, and rewrite SCI manuscript Introductions using Nature-style funnel logic. Use when Codex is asked to write, revise, or critique an Introduction; diagnose background-to-gap flow; sharpen novelty and contribution framing; convert research notes into English Introduction prose; or check for overlong setup, weak gap, vague "Here we" moves, method overload, figure-by-figure preview, overclaiming, or unstable terminology.
---

# SCI Introduction

This skill is a generic Introduction-writing coach for SCI manuscripts, with Nature-style structure as the default. It produces Chinese structural diagnosis and English replacement prose unless the user asks otherwise.

The skill must remain project-neutral. Do not store, repeat, or infer private manuscript details in the skill files. Use user-provided manuscript material only inside the current conversation.

## Non-Negotiable Inputs

For drafting or rewriting an Introduction, require the manuscript body or a detailed body-level outline. The Introduction is treated as a late-stage section: it is written after the main body is clear and before the Abstract is finalized.

Acceptable body content includes:

- Results, Methods, Discussion, or a complete main-text draft.
- A detailed body outline with the study question, methods, main findings, evidence classes, limitations, and bounded contribution.
- Figure-by-figure notes only if they are converted into the manuscript's argument and evidence classes before drafting.

If the user provides only a title, topic, abstract, keywords, or a broad idea, do not draft the Introduction. Ask for body content and the core logic answers first.

## Workflow

1. **Classify the task.**
   - `diagnose`: the user provides an existing Introduction and wants critique.
   - `rewrite`: the user provides an existing Introduction plus body content and wants replacement text.
   - `draft`: the user provides body content or a complete body outline and wants a new Introduction.
   - `coach`: the user asks for paragraph logic, gap framing, novelty framing, or revision strategy.

2. **Load references only when useful.**
   - For Nature-style guardrails and paragraph architecture, read `references/nature-introduction-rules.md`.
   - For the Douyin video advice, short setup, or "不要写太长铺垫", read `references/video-notes.md`.
   - Do not load or create project-specific references.

3. **Verify body-first readiness.**
   - For `draft` and `rewrite`, check whether the manuscript body or a sufficiently detailed body outline is present.
   - If missing, pause and request it instead of drafting.
   - For `diagnose`, use the existing Introduction but still ask for body content if judging contribution fit or rewriting is required.

4. **Ask the video-guided logic questions before drafting.**
   Ask these questions unless the answers are already explicit in the manuscript body:
   - Why is this field, problem, system, or task important?
   - What specific problem remains unresolved?
   - What does this study investigate, test, build, or explain?

   If needed, add one short round of follow-up questions about the evidence classes, target journal, strongest result, and claim boundary. Keep each round to 2-4 questions.

5. **Reconstruct the manuscript logic.**
   Combine the body content and the user's answers into a one-line argument:

   `field stake -> bottleneck -> unresolved gap -> present study -> evidence preview -> bounded contribution`

   Identify any mismatch between the user's intended story and what the body actually supports before writing.

6. **Choose the paragraph architecture.**
   - Default Nature-style architecture: 4-6 paragraphs, usually 5.
   - Compress generic background. One crisp broad-background sentence is usually enough.
   - Use the body evidence to decide how much prior-work synthesis and evidence preview the Introduction needs.

7. **Diagnose before rewriting.**
   - Identify paragraph jobs, missing transitions, overlong background, literature-list behavior, vague gap, delayed contribution, method overload, overclaiming, and unstable terminology.
   - Keep diagnosis in Chinese unless the user asks otherwise.
   - Preserve any content the user explicitly says not to change.

8. **Draft the replacement.**
   - Produce English manuscript prose.
   - Keep method details only where they make the gap and present move intelligible.
   - Preview evidence by class rather than figure-by-figure or number-by-number.
   - End with a bounded contribution claim that the body can support.

9. **Invite correction.**
   - After a draft or rewrite, state only the key assumptions that could change the Introduction.
   - Ask the user to correct those assumptions before polishing further.

## Default Paragraph Jobs

Use this 5-paragraph funnel unless the user's manuscript clearly requires a 4- or 6-paragraph structure:

1. **Field stake.** Open with the phenomenon, system, disease burden, material challenge, computational task, or scientific problem. Do not open with a list of papers or a method name.
2. **Bottleneck.** Name the conceptual, technical, measurement, mechanistic, or translational difficulty that makes the problem unresolved.
3. **Prior attempts and residual gap.** Synthesize what existing work captures and why it still cannot answer the target question.
4. **Present move.** State the framework, dataset, experiment, measurement, model, or conceptual move that addresses the gap.
5. **Evidence preview and bounded claim.** Group the evidence classes and state what the study shows without overclaiming.

## Output Defaults

For diagnosis:

```markdown
**结构诊断**
- Paragraph jobs:
- Main breakpoints:
- Gap strength:
- Contribution clarity:
- Overclaiming / terminology risks:

**修改策略**
- Recommended funnel:
- Sentences to compress:
- Sentences to replace:
- Questions to answer before rewriting:
```

For drafting or rewriting:

```markdown
**Logic Check**
field stake -> bottleneck -> unresolved gap -> present study -> evidence preview -> bounded contribution

**Recommended Funnel**
1. ...

**Replacement Introduction**
[English prose]

**Assumptions To Correct**
- ...
```

## Nature-Style Guardrails

- Start from the phenomenon, task, system, disease burden, or scientific problem, not from "X is important" boilerplate.
- Avoid long generic background. Move quickly from field stake to unresolved problem.
- Make the gap explain why the problem persists, not merely that "few studies" exist.
- Do not list prior studies one by one; group them by what they enable and what they miss.
- Make the "Here we" or "In this study" sentence answer the gap directly.
- Do not turn the final paragraph into a figure roadmap.
- Do not claim causality, mechanism, clinical utility, general superiority, or universal applicability unless the body supports it.
- Keep terminology stable across the Introduction and the manuscript body.
- Do not write an Introduction from the Abstract alone; the Abstract should be finalized after the Introduction.
