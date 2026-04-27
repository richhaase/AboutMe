---
title: AboutMe Canonical Markdown Design
authorship: human-ai-coauthored
status: implemented-design
human_author: Rich Haase
ai_role: drafting, organization, formatting
created: 2026-04-27
updated: 2026-04-27
source_references:
  - README.md
  - references/leadership_philosophy.md
  - references/public_content_interview.md
---

# AboutMe Canonical Markdown Design

## Objective

Improve this repository into a public AboutMe and working-with-me guide that is useful to any reader. The repository should also make authorship and AI collaboration clear for readers who care about provenance.

## Non-Objectives

* Do not invent biographical facts, preferences, credentials, employment history, or claims.
* Do not obscure which material is human-written, AI-written, or human-AI coauthored.
* Do not convert the project to JSON or make JSON the canonical format.
* Do not rewrite the existing leadership philosophy body unless explicitly approved.
* Do not split the project into separate audience-specific entry points.

## Repository Shape

The intended structure is:

```text
README.md
references/
  leadership_philosophy.md
  public_content_interview.md
LICENSE
```

`README.md` is the canonical public entry point.

`references/` contains supporting source material and workflows. The initial source reference is the existing leadership philosophy, moved from `leadership_philosophy.md` to `references/leadership_philosophy.md`. The interview workflow describes how to create or update public content by interviewing Rich first.

## Provenance Model

Markdown files touched by this work use YAML frontmatter for provenance and metadata. Frontmatter keeps the repository Markdown-native while giving readers predictable fields to inspect.

Use these authorship values:

* `human-written`: written by Rich Haase without AI-generated prose in the body.
* `ai-written`: written by an AI assistant without human prose in the body.
* `human-ai-coauthored`: drafted, organized, or edited through human/AI collaboration.

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
status: canonical-public-entrypoint
human_author: Rich Haase
ai_role: drafting, organization, formatting
source_references:
  - references/leadership_philosophy.md
  - references/public_content_interview.md
---
```

## File Responsibilities

### README.md

The README should serve as the single public entry point. It should be concise, useful to any reader, and clear about provenance.

It should include:

* frontmatter provenance
* a short authorship note
* a description of what the repository is and is not
* a working-with-me summary based only on approved source material
* links to supporting references

### references/leadership_philosophy.md

The leadership philosophy should be a source reference.

Its existing body should remain intact unless Rich explicitly approves content edits. The only planned change is provenance frontmatter above the original body.

### references/public_content_interview.md

The interview workflow should guide future public content updates.

It should require interviewing Rich before adding new claims, preserving provenance, avoiding invented facts, and keeping human-written source material distinguishable from co-authored summaries.

## Risks and Decisions

* Adding frontmatter changes the exact bytes of reference files; mitigate by preserving the original prose body.
* Summaries can accidentally overstate source material; mitigate by keeping the README summary short and linking to the human-written reference.
* Markdown frontmatter is not a universal standard, but it is readable and more appropriate here than JSON for this repository.
* Future contributors may be tempted to update public content without asking Rich; mitigate with a reusable interview workflow.

## Done When

* `README.md` is the canonical public entry point.
* The leadership philosophy lives under `references/` as source material.
* The public content interview workflow lives under `references/`.
* Touched Markdown files include explicit provenance frontmatter.
* Existing human-written prose is preserved unless explicitly approved for edits.
* The repo does not create separate audience-specific entry points.
