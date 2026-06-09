---
name: sci-introduction
description: Diagnose, plan, draft, and rewrite SCI manuscript Introductions using Nature-style funnel logic. Use when Codex is asked to write, revise, or critique an Introduction; diagnose background-to-gap flow; sharpen novelty and contribution framing; convert research notes into English Introduction prose; or check for overlong setup, weak gap, vague "Here we" moves, method overload, figure-by-figure preview, overclaiming, or unstable terminology.
metadata:
  version: 1.1.0
  author: Generic Nature-style Introduction workflow
---

# SCI Introduction - Router

This skill uses a router/static-dynamic split inspired by the `nature-*` skill layout:

- `SKILL.md` is the short router and trigger surface.
- `manifest.yaml` declares which static fragments to load for each request.
- `static/` holds always-loaded stance, workflow, output format, and task/style/language fragments.
- `references/` holds deeper supporting notes such as the video summary and Nature-style rules.

Do not apply the workflow from memory. When this skill is invoked, load the manifest and the matching fragments from disk.

## Routing Protocol

### 1. Load The Manifest And Core Layer

Read `manifest.yaml`, then read every file listed under `always_load`. These files define the body-first rule, privacy stance, video-guided intake, and output defaults.

### 2. Detect Axis Values

Use the manifest's `detect` hints to choose:

- `task`: `diagnose`, `draft`, `rewrite`, or `coach`
- `language`: `en` or `zh-to-en`
- `style`: `nature` or `generic`

State the detected axis values in one short line before drafting or rewriting so the user can correct them cheaply.

### 3. Load Matching Fragments

Read the static fragment for each detected axis value. Load only the selected fragments, not every file in `static/`.

### 4. Apply The Body-First Gate

For drafting or rewriting an Introduction, require the manuscript body or a detailed body-level outline. If the user only provides a title, topic, abstract, keywords, or a broad idea, ask for body content before drafting.

### 5. Ask The Three Video Questions

Before writing prose, answer or ask:

1. Why is this field, problem, system, or task important?
2. What specific problem remains unresolved?
3. What does this study investigate, test, build, or explain?

Then combine the answers with the manuscript body into:

`field stake -> bottleneck -> unresolved gap -> present study -> evidence preview -> bounded contribution`

### 6. Draft Or Diagnose

Use the loaded fragments in this priority order:

1. Core stance and source hierarchy
2. Core workflow
3. Task-specific fragment
4. Style fragment
5. Language fragment
6. On-demand references

Do not invent results, citations, limitations, mechanisms, clinical utility, or significance claims that are not supported by the manuscript body.

### 7. Reach For References Only When Needed

Use `references/video-notes.md` when the user mentions the Douyin video, short setup, or "不要写太长铺垫". Use `references/nature-introduction-rules.md` when the user needs deeper paragraph architecture, diagnosis, or a self-check.
