# sci-introduction

Codex skill for diagnosing, planning, drafting, and rewriting SCI manuscript Introductions, with a focus on Nature-style funnel logic.

## What It Does

- Diagnoses Introduction structure in Chinese.
- Drafts replacement Introduction prose in English.
- Requires manuscript body content or a detailed body-level outline before drafting.
- Uses a video-guided question workflow before writing: importance, unresolved problem, and present-study move.
- Applies a 4-6 paragraph Nature-style funnel: field stake, bottleneck, prior attempts/gap, present move, evidence preview.
- Keeps the skill generic and avoids project-specific manuscript memory.

## Contents

- `SKILL.md` - skill trigger metadata and working instructions.
- `agents/openai.yaml` - Codex UI metadata.
- `references/nature-introduction-rules.md` - generic Nature-style Introduction rules.
- `references/video-notes.md` - Douyin video notes for short setup and pre-drafting question logic.

## Install

Place this folder under your Codex skills directory:

```text
C:\Users\Administrator\.codex\skills\sci-introduction
```

Then invoke it with prompts such as:

```text
Use $sci-introduction to diagnose and rewrite this Nature-style Introduction.
```

## Notes

This skill does not store private project-specific manuscript details. Use manuscript content only inside the active conversation.
