---
name: career-build-rendered-portfolio
description: Use when generating or updating the polished HTML/PDF portfolio render output from source markdown into outputs/.../final using the shared portfolio template.
---

# Career Build Rendered Portfolio

## Purpose

이 스킬은 제출용 포트폴리오 markdown 원본을 기반으로 HTML/PDF 결과물을 `outputs/.../final/`에 생성할 때 사용한다.

`templates/portfolio/`는 공용 템플릿이다. 최종 결과물은 항상 `outputs/general/final/` 또는 `outputs/custom/*/final/`에 저장한다.

## Read Order

1. `AGENTS.md`
2. `index.md`
3. Portfolio source content:
   - `outputs/general/source/portfolio.md`
   - or `outputs/custom/*/source/portfolio.md`
4. Supporting wiki pages as needed
5. Shared portfolio template:
   - `templates/portfolio/index.html`
   - `templates/portfolio/styles.css`

## Output Targets

Write rendered results to one of:

- `outputs/general/final/portfolio.html`
- `outputs/general/final/portfolio.pdf`
- `outputs/custom/*/final/portfolio.html`
- `outputs/custom/*/final/portfolio.pdf`
- `outputs/.../final/assets/`

## Required Workflow

1. Identify the source portfolio version.
2. Confirm a usable local profile photo exists under `raw/assets/`.
3. Render the portfolio using the shared template.
4. Save the HTML result under `final/portfolio.html`.
5. Save or export the PDF result under `final/portfolio.pdf` if requested.
6. Keep support images, screenshots, and icons under `final/assets/`.
7. Confirm the final HTML opens without broken links, broken images, overflow, or clipping.
8. If this skill is running inside `career-apply-pipeline`, let the pipeline own the final log entry. Otherwise, append one `output` entry to `log.md`.

## Portfolio Rules

- Treat each project section as a case study, not a resume copy.
- Show problem, decision, action, and result.
- Keep proof links, images, architecture diagrams, or screenshots close to the related project.
- If space is tight, reduce weaker projects before shrinking text into unreadability.

## Validation

At minimum:

- Run `git diff --check`.
- Confirm every referenced local portfolio asset exists.
- Open the HTML or inspect it closely enough to catch broken asset paths.

## Log Format

```md
## [YYYY-MM-DD] output | rendered portfolio updated

- Synced rendered portfolio with `outputs/.../source/portfolio.md`
- Wrote `outputs/.../final/portfolio.html`
- Wrote `outputs/.../final/portfolio.pdf` if requested
```
