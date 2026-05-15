---
name: career-apply-pipeline
description: Use when the user wants to go from a company JD or target role to a complete application package in one workflow, including company research when useful, outputs/custom/YYYY-MM-DD-company source files, optional final HTML/PDF outputs, quality checks, and log updates.
---

# Career Apply Pipeline

## Purpose

이 스킬은 JD 입력부터 제출 후보 산출물까지 한 번에 닫는 상위 워크플로다.

기존 스킬을 합치는 대신 순서를 정한다. 세부 작업은 `career-company-research`, `career-build-custom-package`, `career-output-polish`, `career-build-rendered-resume`, `career-build-rendered-portfolio`, `career-lint`의 규칙을 따른다.

## Inputs

Accept any of:

- JD URL
- JD 원문
- 회사명과 역할명
- 이미 존재하는 `outputs/custom/YYYY-MM-DD-company/` 폴더

## Pipeline Decision

Use the smallest complete path:

- Brief only: create `source/jd.md` and `source/brief.md`
- Markdown package: create `source/jd.md`, `source/brief.md`, `source/resume.md`, `source/portfolio.md`
- Submission package: create the markdown package, polish it, render requested HTML/PDF outputs under `final/`, then run quality checks
- Existing package refresh: reuse the folder, update only stale files, then polish and validate

## Read Order

Before writing:

1. `AGENTS.md`
2. `index.md`
3. `log.md`
4. `wiki/overview/career-overview.md`
5. `wiki/themes/positioning.md`
6. `wiki/stories/story-bank.md`
7. `wiki/sentence-bank/resume-bullets.md`
8. Existing target package files, if any
9. The JD or company context

## Required Workflow

1. Resolve the target package folder.
   - Use `outputs/custom/YYYY-MM-DD-company/`.
   - Use ASCII lowercase company slugs.
2. Capture the JD in `source/jd.md`.
3. Decide whether research is needed.
   - Use `career-company-research` when company fit, official signals, or interview signals matter.
4. Build the custom package with `career-build-custom-package`.
   - Create or update `source/brief.md`, `source/resume.md`, and `source/portfolio.md`.
   - Keep gaps explicit.
   - Do not fabricate full-stack, AI, traffic, revenue, or domain expertise.
5. Polish final markdown outputs.
   - Apply `career-output-polish` to `source/resume.md`.
   - Apply `career-output-polish` to `source/portfolio.md`.
6. Render only when requested or clearly implied.
   - Use `career-build-rendered-resume` and `career-build-rendered-portfolio`.
   - Save results under `final/`.
7. Quality-check the package.
   - Use `docs/checklists/custom-output-quality-checklist.md`.
   - Confirm `source/jd.md`, `source/brief.md`, `source/resume.md`, and `source/portfolio.md` exist.
   - Confirm final outputs have no placeholders.
   - Confirm strong claims trace back to `wiki/`, `raw/`, or `source/brief.md`.
8. Backfill reusable knowledge if the application produced a better general framing.
9. Append one `output` entry to `log.md`.

## Output Standard

A completed markdown package must contain:

- `source/jd.md`
- `source/brief.md`
- `source/resume.md`
- `source/portfolio.md`

A completed research package may also contain:

- `research/company.md`
- `research/signals.md`

A completed submission package may also contain:

- `final/resume.html`
- `final/resume.pdf`
- `final/portfolio.html`
- `final/portfolio.pdf`
- `final/assets/`

## Quality Gates

Do not call the package done until:

- `source/brief.md` separates must-have, preferred, repeated keywords, and gaps.
- `source/brief.md` states what to emphasize and de-emphasize.
- `source/resume.md` is compact, source-backed, and JD-specific.
- `source/portfolio.md` uses case studies rather than copied resume bullets.
- unsupported claims are removed or moved to gaps.
- `log.md` records what changed.

## Log Format

```md
## [YYYY-MM-DD] output | application pipeline for <company-role>

- Created or updated `outputs/custom/YYYY-MM-DD-company/source/`
- Built `brief.md`, `resume.md`, and `portfolio.md`
- Added `research/...` if needed
- Rendered `final/...` if requested
- Ran custom output quality checks
```

## Stop Conditions

Stop and ask the user if:

- there is no JD, no role, and no reliable company context
- multiple target roles are mixed into one package
- the requested positioning depends on facts not present in `raw/` or `wiki/`
- the user asks to submit or send materials externally without review
