---
name: public-content-interview
description: Use when creating or updating public content in this AboutMe repository, especially summaries of Rich's working style, leadership philosophy, preferences, or other statements that represent Rich to readers.
---

# Public Content Interview

## Purpose

Use this skill before creating or updating public content in this repository. Public content should be accurate, grounded in Rich's own words, and clear about AI collaboration.

## Rules

* Interview Rich before adding new claims.
* Ask no more than three independent questions at a time.
* Prefer specific questions over broad prompts.
* Do not infer biographical facts, credentials, experience, employment history, contact details, or availability.
* Separate direct source material from co-authored summaries.
* Preserve the body of human-written references unless Rich explicitly approves edits.
* Use readable Markdown sections or notes for provenance; do not add YAML frontmatter to public content.
* Make uncertainty visible instead of smoothing it over.

## Questions

Start with the smallest useful set:

* What should this content help a reader understand or do?
* Who is the likely reader?
* What should this content not say?
* Which existing reference should this be grounded in?
* Is this a personal statement, a working preference, a leadership principle, or a logistical detail?
* Should the final text sound direct, warm, formal, terse, or something else?
* Are there any facts that must be quoted exactly?
* Are there any words, claims, or framings to avoid?
* Should this be marked human-written, AI-written, or human-AI coauthored?

## Process

1. Read the existing `README.md` and relevant files under `docs/`.
2. Identify whether the update changes source material, summary material, or both.
3. Interview Rich using the smallest useful question set.
4. Draft the change with conservative claims.
5. Label authorship and AI involvement in readable Markdown prose.
6. Link to source references instead of duplicating long source material.
7. Review for invented facts, audience confusion, and overstatement.
8. Verify that the changed files still make sense to a first-time reader.

## Provenance Checklist

Before finishing an update, confirm:

* public content does not use YAML frontmatter
* authorship is stated accurately in readable prose
* AI involvement is stated when AI helped draft, organize, or format the text
* source references point to the documents that support the public claims
* human-written source material remains distinguishable from co-authored summaries
* no JSON file was introduced as a replacement for readable Markdown guidance
