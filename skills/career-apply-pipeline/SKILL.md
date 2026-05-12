---
name: career-apply-pipeline
description: Use when the user wants to go from a company JD or target role to a complete application package in one workflow, including company research when useful, outputs/custom/YYYY-MM-DD-company files, polished resume and portfolio markdown, optional rendered HTML/PDF outputs, quality checks, and log updates.
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

If the user asks for "지원 패키지", "맞춤 이력서", "JD 기준으로 끝까지", "HTML/PDF까지", or "제출용으로 만들어줘", use this pipeline unless they explicitly ask for only one subtask.

## Pipeline Decision

Use the smallest complete path:

- JD analysis only: use `career-build-custom-package` up to `analysis.md` and `strategy.md`.
- Markdown package: run research if needed, then create `jd.md`, `analysis.md`, `strategy.md`, `resume.md`, `portfolio.md`.
- Submission package: create markdown package, polish it, render requested HTML/PDF outputs, then run quality checks.
- Existing package refresh: reuse the folder, update only stale files, then polish and validate.

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
   - If a folder already exists for the same company and role, update it instead of creating a near-duplicate unless the user wants a new version.
2. Capture the JD.
   - Save the JD text, URL, or structured summary to `jd.md`.
   - If the JD is too short, record the limitation in `analysis.md` and ask only if a credible package cannot be made.
3. Decide whether research is needed.
   - Use `career-company-research` when the user provides a URL, asks for company fit, or the role/company context affects positioning.
   - Skip broad research when the user provides enough JD context and wants speed.
4. Build the custom package with `career-build-custom-package`.
   - Create or update `analysis.md`, `strategy.md`, `resume.md`, and `portfolio.md`.
   - Keep gaps explicit.
   - Do not fabricate full-stack, AI, traffic, revenue, or domain expertise.
5. Polish final markdown outputs.
   - Apply `career-output-polish` to `resume.md`.
   - Apply `career-output-polish` to `portfolio.md`.
   - Preserve resume 개조식.
6. Render only when requested or clearly implied.
   - Use `career-build-rendered-resume` for `resume/` and PDF export.
   - Use `career-build-rendered-portfolio` for `portfolio/` and PDF export.
   - Treat markdown as source of truth and HTML/PDF as derived output.
7. Quality-check the package.
   - Use `docs/checklists/custom-output-quality-checklist.md`.
   - Confirm all required files exist.
   - Confirm final outputs have no placeholders.
   - Confirm strong claims trace back to `wiki/`, `raw/`, or `analysis.md`.
   - Confirm known gaps are not hidden in final claims.
8. Backfill reusable knowledge if the application produced a better general framing.
   - Update `wiki/themes/positioning.md`, `wiki/sentence-bank/resume-bullets.md`, or `wiki/stories/story-bank.md` only when the framing is reusable beyond one company.
9. Append one `output` entry to `log.md`.

## Output Standard

A completed markdown package must contain:

- `jd.md`
- `analysis.md`
- `strategy.md`
- `resume.md`
- `portfolio.md`

A completed submission package may also contain:

- `company-research.md`
- `culture-signals.md`
- `interview-signals.md`
- `fit-hypotheses.md`
- rendered PDF or screenshot checks

## Quality Gates

Do not call the package done until:

- `analysis.md` separates must-have, preferred, repeated keywords, candidate match, and gaps.
- `strategy.md` states what to emphasize and de-emphasize.
- `resume.md` is compact, source-backed, and JD-specific.
- `portfolio.md` uses case studies rather than copied resume bullets.
- unsupported claims are removed or moved to gaps.
- `log.md` records what changed.

## Log Format

```md
## [YYYY-MM-DD] output | application pipeline for <company-role>

- Created or updated `outputs/custom/YYYY-MM-DD-company/`
- Built JD analysis, strategy, resume, and portfolio
- Polished final markdown outputs
- Rendered HTML/PDF outputs if requested
- Ran custom output quality checks
```

## Stop Conditions

Stop and ask the user if:

- there is no JD, no role, and no reliable company context
- multiple target roles are mixed into one package
- the requested positioning depends on facts not present in `raw/` or `wiki/`
- rendering requires deleting major evidence from the source markdown
- the user asks to submit or send materials externally without review
