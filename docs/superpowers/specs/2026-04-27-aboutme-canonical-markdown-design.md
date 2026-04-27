---
title: AboutMe Canonical Markdown Design
authorship: human-ai-coauthored
status: draft-design
human_author: Rich Haase
ai_role: drafting, organization, formatting
created: 2026-04-27
source_references:
  - README.md
  - leadership_philosophy.md
---

# AboutMe Canonical Markdown Design

## Objective

Improve this repository into a public-facing AboutMe that works for both human readers and AI/agent readers while making authorship and provenance explicit.

## Non-Objectives

- Do not invent biographical facts, preferences, credentials, employment history, or claims.
- Do not obscure which material is human-written, AI-written, or human/AI co-authored.
- Do not convert the project to JSON or make JSON the canonical robot-facing format.
- Do not rewrite the existing leadership philosophy body unless explicitly approved.

## Repository Shape

The intended structure is:

```text
README.md
AGENTS.md
references/
  leadership_philosophy.md
LICENSE
```

`README.md` is the canonical human-facing entry point.

`AGENTS.md` is the canonical robot/agent-facing entry point.

`references/` contains supporting source material. The initial reference is the existing leadership philosophy, moved from `leadership_philosophy.md` to `references/leadership_philosophy.md`.

## Provenance Model

Markdown files touched by this work should use YAML frontmatter for provenance and metadata. Frontmatter keeps the repository Markdown-native while giving humans and agents predictable fields to inspect.

Use these authorship values:

- `human-written`: written by Rich Haase without AI-generated prose in the body.
- `ai-written`: written by an AI assistant without human prose in the body.
- `human-ai-coauthored`: drafted, organized, or edited through human/AI collaboration.

Example reference frontmatter:

```yaml
---
title: Leadership Philosophy
authorship: human-written
status: canonical-reference
created_by: Rich Haase
ai_role: none
---
```

Example README frontmatter:

```yaml
---
title: About Rich Haase
authorship: human-ai-coauthored
status: canonical-human-entrypoint
human_author: Rich Haase
ai_role: drafting, organization, formatting
source_references:
  - references/leadership_philosophy.md
---
```

Example AGENTS frontmatter:

```yaml
---
title: Agent Guide for AboutMe
authorship: human-ai-coauthored
status: canonical-agent-entrypoint
human_author: Rich Haase
ai_role: drafting, organization, formatting
source_references:
  - README.md
  - references/leadership_philosophy.md
---
```

## File Responsibilities

### README.md

The README should serve people first. It should be concise, public-facing, and clear about provenance.

It should include:

- Frontmatter provenance.
- A short authorship note.
- A public AboutMe profile based only on approved source material.
- A concise values or leadership summary that links to the full reference.
- A pointer to `AGENTS.md` for AI/agent readers.
- A pointer to `references/leadership_philosophy.md` as human-written source material.

### AGENTS.md

The agent guide should tell AI systems how to interpret the repository.

It should include:

- Frontmatter provenance.
- Canonical source hierarchy.
- Authorship definitions.
- Instructions not to invent unsupported biographical facts.
- Instructions to distinguish direct human-written references from co-authored summaries.
- Instructions to prefer Markdown prose and frontmatter over JSON for this repository.

### references/leadership_philosophy.md

The leadership philosophy should become a reference document.

Its existing body should remain intact unless Rich explicitly approves content edits. The planned change is to move it into `references/` and add provenance frontmatter. If byte-for-byte preservation of the body is desired, the frontmatter should be the only body-adjacent addition.

## Risks and Decisions

- Some agents may not automatically discover `AGENTS.md`; mitigate by linking it prominently from `README.md`.
- Adding frontmatter changes the exact bytes of reference files; mitigate by preserving the original prose body.
- Summaries can accidentally overstate source material; mitigate by keeping the README summary short and linking to the human-written reference.
- Markdown frontmatter is not a universal standard, but it is readable and more appropriate here than JSON for LLM-facing guidance.

## Done When

- The design has user approval.
- A subsequent implementation plan exists before code/content changes.
- `README.md` is the human-facing canonical entry point.
- `AGENTS.md` is the robot/agent-facing canonical entry point.
- The leadership philosophy lives under `references/` as source material.
- Touched Markdown files include explicit provenance frontmatter.
- Existing human-written prose is preserved unless explicitly approved for edits.
