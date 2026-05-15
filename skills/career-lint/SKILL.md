---
name: career-lint
description: Use when auditing the health of this career wiki, especially to find orphan pages, duplicate project descriptions, conflicting metrics or facts, missing reusable strengths, and stale outputs across source and final layers.
---

# Career Lint

## Purpose

이 스킬은 커리어 위키와 output 구조의 품질을 점검하고, 어디를 보강해야 하는지 찾는 데 사용한다.

## Read First

Start with:

1. `AGENTS.md`
2. `index.md`
3. `log.md`

Then inspect relevant files under:

- `raw/`
- `wiki/`
- `outputs/`
- `samples/` when template examples are part of the task

## Lint Checks

Run these checks in order:

1. Orphan pages
   - pages under `wiki/` that are not linked from `index.md`
2. Duplicate coverage
   - multiple pages repeating the same project or experience without a clear reason
3. Conflicting facts
   - different dates, metrics, roles, or outcomes for the same item
4. Missing reusable assets
   - strong achievements present in raw or wiki, but absent from:
     - `wiki/sentence-bank/resume-bullets.md`
     - `wiki/stories/story-bank.md`
5. Stale outputs
   - `outputs/general/source/` or `outputs/custom/*/source/` no longer reflect current positioning
   - rendered outputs under `final/` clearly lag the current source files
6. Missing package structure
   - missing `source/jd.md`, `source/brief.md`, `source/resume.md`, `source/portfolio.md` in a custom package
7. Missing high-value pages
   - concepts, strengths, or major projects that are repeatedly referenced but lack a dedicated page

## Output Style

When reporting lint findings:

- list findings first
- order by severity or usefulness
- include exact file paths
- explain the consequence briefly
- suggest the next corrective action

If there are no findings, say that explicitly and mention any residual blind spots.

## Allowed Actions

By default, lint is read-only and diagnostic.

Only modify files if the user explicitly asks you to fix the findings in the same turn.

If you do fix things, also append one `lint` entry to `log.md`.
