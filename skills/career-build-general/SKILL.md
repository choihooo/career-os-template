---
name: career-build-general
description: Use when updating the single general-purpose resume and portfolio in outputs/general/source based on the current career wiki pages and positioning.
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
7. Relevant files under `wiki/output-briefs/`
8. Any directly relevant project, experience, award, or skill pages

## Output Targets

Only write to these files unless the task explicitly asks for more:

- `outputs/general/source/resume.md`
- `outputs/general/source/portfolio.md`

If the user asks for rendered output too, write to:

- `outputs/general/final/resume.html`
- `outputs/general/final/resume.pdf`
- `outputs/general/final/portfolio.html`
- `outputs/general/final/portfolio.pdf`

## Required Workflow

1. Read the positioning and reusable evidence pages first.
2. Read the relevant output brief before choosing section order or emphasis.
3. Select only the strongest and most defensible stories.
4. Rewrite the target output files so they read as coherent final documents, not as notes.
5. Before finalizing the target output files, invoke `career-output-polish` on each final-form resume or portfolio file.
6. If you discover missing reusable phrasing, backfill:
   - `wiki/sentence-bank/resume-bullets.md`
   - `wiki/themes/positioning.md`
   - `wiki/stories/story-bank.md`
7. Render HTML/PDF only when the user asks for them or they are clearly needed.
8. Append one `output` entry to `log.md`.

## Writing Rules

- Default to Korean unless the user asks for English.
- Remove weak, generic, or unsupported claims.
- Prefer concrete impact over responsibility lists.
- Keep the general outputs broadly reusable.
- Do not add filler sections just because a template has space.

## Resume Formatting Rules

Apply these rules to `outputs/general/source/resume.md`:

- Default to 개조식.
- Keep summary sections short: one positioning line plus 2-4 bullets is enough.
- Experience and project bullets should follow a fact/action/result shape whenever possible.
- Do not write feature-only bullets like `애플 소셜 로그인 구현` or `관리자 대시보드 개발`.
- If no measured metric exists, use a defensible observable result such as 사용자 경험 개선, 운영자 확인 흐름 단축, QA 재현 비용 감소, 유지보수 범위 축소.
- Skills, awards, education, links, roles, and periods should use compact phrases rather than prose.
- Do not write portfolio-style paragraphs in a resume.

## Log Format

```md
## [YYYY-MM-DD] output | updated general resume and portfolio

- Updated `outputs/general/source/resume.md`
- Updated `outputs/general/source/portfolio.md`
- Rendered `outputs/general/final/...` if requested
```

## Stop Conditions

Stop and ask the user if:

- the wiki lacks enough evidence to produce a credible general version
- two wiki pages conflict on core positioning
