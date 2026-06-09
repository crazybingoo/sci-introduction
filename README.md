# `sci-introduction` skill

A Nature-style Introduction skill for diagnosing, planning, drafting, and rewriting SCI manuscript Introductions from manuscript-body evidence.

This skill is bilingual-aware. It accepts Chinese or English manuscript bodies, figure/result notes, existing Introductions, and author answers, then returns Chinese structural diagnosis and English replacement prose by default.

## What It Does

- diagnoses paragraph jobs, gap strength, contribution clarity, and overclaiming risk
- requires manuscript body content or a detailed body-level outline before drafting
- uses the video-guided three-question gate: importance, unresolved problem, present-study move
- builds a one-line argument before writing prose
- drafts or rewrites a 4-6 paragraph Nature-style Introduction
- keeps manuscript details in the active conversation only, not in skill files

## Source Hierarchy

1. User-provided manuscript body, results, methods, discussion, figures, and limitations.
2. User answers to the three video-guided questions.
3. Generic Nature-style Introduction rules bundled with this skill.
4. On-demand references in `references/`.

## File Structure

The skill follows a router/static-dynamic split like the `nature-*` skills:

```text
sci-introduction/
├── README.md
├── SKILL.md                     # short router
├── manifest.yaml                # always_load core + task/language/style axes
├── agents/
│   └── openai.yaml              # Codex UI metadata
├── static/
│   ├── core/                    # always loaded
│   │   ├── stance.md
│   │   ├── workflow.md
│   │   └── output-format.md
│   └── fragments/               # loaded by manifest axes
│       ├── task/
│       ├── language/
│       └── style/
└── references/
    ├── nature-introduction-rules.md
    └── video-notes.md
```

## When To Use

- writing a new Introduction after the manuscript body is clear
- rewriting an existing Introduction against the body evidence
- diagnosing whether background, gap, "Here we", and contribution logic work
- converting Chinese result notes or author logic into English Introduction prose
- compressing overlong setup into a Nature-style funnel

Do not use this skill to invent a paper from only a topic, title, or abstract.

## Install

Place this folder under your Codex skills directory:

```text
C:\Users\Administrator\.codex\skills\sci-introduction
```

Then invoke it with prompts such as:

```text
Use $sci-introduction to diagnose and rewrite this Nature-style Introduction.
```

## Design Intent

- The Introduction is written late: after the body is clear and before the Abstract is finalized.
- The video's three questions are treated as the pre-drafting logic gate.
- Nature-style compression means short setup, strong gap, and evidence-bounded contribution.
- The skill should ask for missing body evidence rather than fabricate content.
