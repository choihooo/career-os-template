---
name: career-lint
description: Use when auditing the health of this career wiki, especially to find orphan pages, duplicate project descriptions, conflicting metrics or facts, missing reusable strengths, stale outputs, and gaps between raw sources and wiki pages.
---

# Career Lint

## Purpose

이 스킬은 커리어 위키의 구조적 품질을 점검하고, 어디를 보강해야 하는지 찾는 데 사용한다.

## Read First

Start with:

1. `AGENTS.md`
2. `index.md`
3. `log.md`

Then inspect relevant files under:

- `raw/`
- `wiki/`
- `outputs/`

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
   - general or custom outputs that no longer reflect current positioning
6. Missing high-value pages
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

## Log Format

```md
## [YYYY-MM-DD] lint | short description

- Checked orphan pages, duplicates, and conflicts
- Fixed or documented the highest-priority issues
```

## Stop Conditions

Stop and ask the user if:

- you find a contradiction that changes the factual record materially
- a raw source appears corrupted or misleading
- the scope is too broad and needs to be split into diagnostic pass and fix pass
