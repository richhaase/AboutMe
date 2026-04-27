# AboutMe Canonical Markdown Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Convert the repository into a public, general-purpose AboutMe and working-with-me guide for any reader, with explicit AI co-authorship disclosure and a reusable interview workflow for future updates.

**Architecture:** Keep one canonical public entry point in `README.md`. Move source material into `references/`, preserving the human-written leadership philosophy body and adding Markdown frontmatter for provenance. Add a reference workflow that instructs future contributors to interview Rich before creating or updating public content.

**Tech Stack:** Markdown, YAML frontmatter, Git.

---

### Task 1: Reference Structure

**Files:**
- Create: `references/`
- Move: `leadership_philosophy.md` to `references/leadership_philosophy.md`
- Modify: `references/leadership_philosophy.md`

- [ ] **Step 1: Create the references directory**

Run: `mkdir -p references`

Expected: `references/` exists.

- [ ] **Step 2: Move the leadership philosophy**

Run: `mv leadership_philosophy.md references/leadership_philosophy.md`

Expected: The original file now lives at `references/leadership_philosophy.md`.

- [ ] **Step 3: Add provenance frontmatter**

Add provenance frontmatter above the existing `# Leadership Philosophy` heading. Preserve the original prose body unchanged below the frontmatter.

### Task 2: Canonical README

**Files:**
- Modify: `README.md`

- [ ] **Step 1: Replace README with canonical general-purpose content**

Use frontmatter to mark the README as human/AI co-authored. Present it as a guide for any reader, human or AI, without creating separate human-versus-agent sections.

Expected sections:

- `# About Rich Haase`
- `## Provenance`
- `## What This Is`
- `## How To Work With Me`
- `## What I Try To Provide`
- `## What I Ask From Others`
- `## References`

### Task 3: Public Content Interview Workflow

**Files:**
- Create: `references/public_content_interview.md`

- [ ] **Step 1: Create the interview workflow reference**

Write a reusable Markdown workflow for creating or updating public content. The workflow should require interviewing Rich first, asking questions in small batches, preserving authorship/provenance, avoiding invented facts, and updating references when source material changes.

Expected sections:

- `# Public Content Interview Workflow`
- `## Purpose`
- `## When To Use This`
- `## Interview Rules`
- `## Core Questions`
- `## Update Process`
- `## Provenance Checklist`

### Task 4: Verification

**Files:**
- Read: `README.md`
- Read: `references/leadership_philosophy.md`
- Read: `references/public_content_interview.md`

- [ ] **Step 1: Verify expected files**

Run: `rg --files`

Expected output includes:

```text
README.md
references/leadership_philosophy.md
references/public_content_interview.md
LICENSE
```

- [ ] **Step 2: Verify provenance fields**

Run: `rg -n "authorship:|status:|ai_role:" README.md references/leadership_philosophy.md references/public_content_interview.md`

Expected: Each touched Markdown file includes frontmatter provenance fields.

- [ ] **Step 3: Verify no audience-specific entry point remains**

Run: Review the file list and headings from `rg --files` and `rg -n "^#|^##" README.md references/leadership_philosophy.md references/public_content_interview.md docs/superpowers/specs/2026-04-27-aboutme-canonical-markdown-design.md docs/superpowers/plans/2026-04-27-aboutme-canonical-markdown.md`.

Expected: There is one canonical public entry point, `README.md`, and no separate audience-specific entry point.

- [ ] **Step 4: Review diff**

Run: `git diff -- README.md references/leadership_philosophy.md references/public_content_interview.md docs/superpowers/specs/2026-04-27-aboutme-canonical-markdown-design.md docs/superpowers/plans/2026-04-27-aboutme-canonical-markdown.md`

Expected: README contains the canonical general-purpose guide. The leadership philosophy body remains the same below frontmatter. The interview workflow gives future contributors a clear process for creating and updating public content.
