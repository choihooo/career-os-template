---
name: career-build-custom-package
description: Use when preparing an application package for a specific company or role, including creating outputs/custom/YYYY-MM-DD-company and filling jd.md, analysis.md, strategy.md, resume.md, and portfolio.md from the wiki and the job description.
---

# Career Build Custom Package

## Purpose

이 스킬은 특정 회사와 JD에 맞춰 지원 패키지를 만드는 작업을 고정된 절차로 수행한다.

## Read Order

Read these files before writing:

1. `AGENTS.md`
2. `index.md`
3. `wiki/overview/career-overview.md`
4. `wiki/themes/positioning.md`
5. `wiki/stories/story-bank.md`
6. `wiki/sentence-bank/resume-bullets.md`
7. The most relevant project, experience, award, and skill pages
8. The incoming JD or company context

## Required Output Folder

Create exactly one folder in this shape:

`outputs/custom/YYYY-MM-DD-company/`

Use ASCII lowercase slug for `company` unless the user explicitly wants otherwise.

## Required Files

Every package must contain:

- `jd.md`
- `analysis.md`
- `strategy.md`
- `resume.md`
- `portfolio.md`

## Required Workflow

1. Save the JD text or summary into `jd.md`.
2. In `analysis.md`, extract:
   - target role
   - must-have requirements
   - preferred requirements
   - repeated keywords
   - likely evaluation themes
3. In `strategy.md`, decide:
   - what to emphasize
   - what to de-emphasize
   - which projects and stories to surface
   - the positioning angle for this application
4. Build `resume.md` from the strongest matching facts and bullets.
5. Build `portfolio.md` from the strongest matching case studies and proof.
6. If the package produces a better reusable framing, backfill the relevant wiki pages.
7. Append one `output` entry to `log.md`.

## Writing Rules

- Tailor aggressively, but do not fabricate fit.
- Match the JD's language where accurate.
- Remove strong but irrelevant material if it weakens the application.
- Keep `analysis.md` analytical, `strategy.md` prescriptive, and `resume.md` or `portfolio.md` final-form.
- Do not leave placeholders in the final package.

## Folder Naming

Use the current local date and company slug:

- `2026-05-10-openai`
- `2026-05-10-kakao`

If multiple roles exist for the same company on the same day, append a short role slug:

- `2026-05-10-openai-research-engineer`

## Log Format

```md
## [YYYY-MM-DD] output | built custom package for company

- Created `outputs/custom/YYYY-MM-DD-company/`
- Added JD analysis and strategy
- Wrote tailored resume and portfolio
```

## Stop Conditions

Stop and ask the user if:

- there is no JD text and no reliable summary
- multiple target roles are being mixed into one package
- the wiki does not contain enough evidence to support the requested positioning
