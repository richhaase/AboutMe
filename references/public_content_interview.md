---
title: Public Content Interview Workflow
authorship: human-ai-coauthored
status: reference-workflow
human_author: Rich Haase
ai_role: drafting, organization, formatting
source_references:
  - references/leadership_philosophy.md
---

# Public Content Interview Workflow

## Purpose

Use this workflow when creating or updating public content in this repository. The goal is to keep public statements accurate, grounded in Rich's own words, and clear about AI collaboration.

## When To Use This

Use this before changing public-facing content, including:

* the main `README.md`
* source references under `references/`
* summaries of Rich's values, working style, leadership philosophy, or preferences
* any new document intended to represent Rich to other people, organizations, or software systems

## Interview Rules

* Interview Rich before adding new claims.
* Ask no more than three independent questions at a time.
* Prefer specific questions over broad prompts.
* Do not infer biographical facts, credentials, experience, employment history, contact details, or availability.
* Separate direct source material from co-authored summaries.
* Preserve the body of human-written references unless Rich explicitly approves edits.
* Use Markdown and YAML frontmatter for provenance.
* Make uncertainty visible instead of smoothing it over.

## Core Questions

Start with the smallest set that fits the update:

* What should this content help a reader understand or do?
* Who is the likely reader?
* What should this content not say?
* Which existing reference should this be grounded in?
* Is this a personal statement, a working preference, a leadership principle, or a logistical detail?
* Should the final text sound direct, warm, formal, terse, or something else?
* Are there any facts that must be quoted exactly?
* Are there any words, claims, or framings to avoid?
* Should this be marked human-written, AI-written, or human-AI coauthored?

## Update Process

1. Read the existing `README.md` and relevant files under `references/`.
2. Identify whether the update changes source material, summary material, or both.
3. Interview Rich using the smallest useful question set.
4. Draft the change with conservative claims.
5. Label authorship and AI involvement in frontmatter.
6. Link to source references instead of duplicating long source material.
7. Review for invented facts, audience confusion, and overstatement.
8. Verify that the changed files still make sense to a first-time reader.

## Provenance Checklist

Before finishing an update, confirm:

* each touched Markdown file has frontmatter
* `authorship` is accurate
* `ai_role` is present when AI helped draft, organize, or format the text
* source references point to the documents that support the public claims
* human-written source material remains distinguishable from co-authored summaries
* no JSON file was introduced as a replacement for readable Markdown guidance
