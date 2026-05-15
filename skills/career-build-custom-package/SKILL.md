---
name: career-build-custom-package
description: Use when preparing an application package for a specific company or role, including creating outputs/custom/YYYY-MM-DD-company/source, optional research, and final rendered outputs from the wiki and the job description.
---

# Career Build Custom Package

## Purpose

이 스킬은 특정 회사와 JD에 맞춰 지원 패키지의 markdown 원본을 만드는 작업을 고정된 절차로 수행한다.

JD 입력부터 렌더링, 품질 체크까지 끝까지 닫는 요청이면 이 스킬을 직접 시작하지 말고 `career-apply-pipeline`을 상위 런북으로 사용한다.

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
9. If present:
   - `research/company.md`
   - `research/signals.md`

## Required Output Folder

Create exactly one folder in this shape:

`outputs/custom/YYYY-MM-DD-company/`

Use ASCII lowercase slug for `company` unless the user explicitly wants otherwise.

## Required Files

Every package must contain:

- `source/jd.md`
- `source/brief.md`
- `source/resume.md`
- `source/portfolio.md`

Optional supporting files:

- `research/company.md`
- `research/signals.md`

Optional rendered files:

- `final/resume.html`
- `final/resume.pdf`
- `final/portfolio.html`
- `final/portfolio.pdf`
- `final/assets/`

## Required Workflow

1. Save the JD text or summary into `source/jd.md`.
2. In `source/brief.md`, capture:
   - target role
   - must-have requirements
   - preferred requirements
   - repeated keywords
   - likely evaluation themes
   - what to emphasize
   - what to de-emphasize
   - leading projects or stories
   - gaps or claims to avoid
3. Build `source/resume.md` from the strongest matching facts and bullets.
4. Build `source/portfolio.md` from the strongest matching case studies and proof.
5. Before finalizing `resume.md` and `portfolio.md`, invoke `career-output-polish` on both files.
6. If the package produces a better reusable framing, backfill the relevant wiki pages.
7. If the user asked for submission-ready HTML/PDF, hand off to:
   - `career-build-rendered-resume`
   - `career-build-rendered-portfolio`
8. If this skill is running inside `career-apply-pipeline`, let the pipeline own the final quality check and log entry. Otherwise, append one `output` entry to `log.md`.

## Writing Rules

- Tailor aggressively, but do not fabricate fit.
- Match the JD's language where accurate.
- Remove strong but irrelevant material if it weakens the application.
- Keep `brief.md` analytical and prescriptive, and keep `resume.md` and `portfolio.md` final-form.
- Do not leave placeholders in the final package.

## Resume Formatting Rules

Apply these rules specifically to `source/resume.md`:

- Default to 개조식.
- Keep any summary to a short title line plus 2-4 bullets.
- For experience and project sections, write bullets in a fact/action/result shape.
- Avoid plain feature lists such as `애플 소셜 로그인 구현` or `대시보드 개발`.
- If a numeric result is unavailable, still state the observable user, operator, QA, or developer experience improvement without inventing metrics.
- Keep portfolio-style narrative, motivation, and interpretation in `source/portfolio.md`.

## Log Format

```md
## [YYYY-MM-DD] output | built custom package for company

- Created `outputs/custom/YYYY-MM-DD-company/source/`
- Added `jd.md`, `brief.md`, `resume.md`, `portfolio.md`
- Added `research/...` if needed
- Rendered `final/...` if requested
```

## Stop Conditions

Stop and ask the user if:

- there is no JD text and no reliable summary
- multiple target roles are being mixed into one package
- the wiki does not contain enough evidence to support the requested positioning
