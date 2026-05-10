---
name: career-build-general
description: Use when updating the general-purpose resume or portfolio versions in outputs/general, especially resume-general-v1, resume-general-v2, portfolio-general-v1, or portfolio-general-v2, based on the current career wiki pages and positioning.
---

# Career Build General

## Purpose

이 스킬은 범용 이력서와 범용 포트폴리오를 현재 위키 상태에 맞게 갱신할 때 사용한다.

## Read Order

Read these files before writing:

1. `AGENTS.md`
2. `index.md`
3. `wiki/overview/career-overview.md`
4. `wiki/themes/positioning.md`
5. `wiki/stories/story-bank.md`
6. `wiki/sentence-bank/resume-bullets.md`
7. Any directly relevant project, experience, award, or skill pages

## Output Targets

Only write to these files unless the task explicitly asks for more:

- `outputs/general/resume-general-v1.md`
- `outputs/general/resume-general-v2.md`
- `outputs/general/portfolio-general-v1.md`
- `outputs/general/portfolio-general-v2.md`

## Version Intent

Use this default interpretation unless the user overrides it:

- `resume-general-v1`: straightforward, broad, safe baseline
- `resume-general-v2`: stronger positioning, sharper emphasis, more opinionated
- `portfolio-general-v1`: balanced overview of projects and proof
- `portfolio-general-v2`: narrative-driven and positioning-heavy version

## Required Workflow

1. Identify which general output files the user wants updated.
2. Read the positioning and reusable evidence pages first.
3. Select only the strongest and most defensible stories.
4. Rewrite the target output files so they read as coherent final documents, not as notes.
5. If you discover missing reusable phrasing, backfill:
   - `wiki/sentence-bank/resume-bullets.md`
   - `wiki/themes/positioning.md`
   - `wiki/stories/story-bank.md`
6. Append one `output` entry to `log.md`.

## Writing Rules

- Default to Korean unless the user asks for English.
- Remove weak, generic, or unsupported claims.
- Prefer concrete impact over responsibility lists.
- Keep each version meaningfully distinct. Do not clone v1 into v2 with superficial wording changes.
- Do not add filler sections just because a template has space.

## Log Format

```md
## [YYYY-MM-DD] output | updated general resume or portfolio

- Updated `outputs/general/...`
- Refined positioning based on `wiki/...`
```

## Stop Conditions

Stop and ask the user if:

- the requested version goal is unclear
- the wiki lacks enough evidence to produce a credible general version
- two wiki pages conflict on core positioning
