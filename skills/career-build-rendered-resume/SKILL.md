---
name: career-build-rendered-resume
description: Use when generating or updating the polished HTML/PDF resume render output from source markdown into outputs/.../final using the shared resume template.
---

# Career Build Rendered Resume

## Purpose

이 스킬은 제출용 이력서 markdown 원본을 기반으로 HTML/PDF 결과물을 `outputs/.../final/`에 생성할 때 사용한다.

`templates/resume/`는 공용 템플릿이다. 최종 결과물은 항상 `outputs/general/final/` 또는 `outputs/custom/*/final/`에 저장한다.

## Read Order

1. `AGENTS.md`
2. `index.md`
3. Resume source content:
   - `outputs/general/source/resume.md`
   - or `outputs/custom/*/source/resume.md`
4. Supporting wiki pages only when needed
5. Shared resume template:
   - `templates/resume/index.html`
   - `templates/resume/styles.css`

## Output Targets

Write rendered results to one of:

- `outputs/general/final/resume.html`
- `outputs/general/final/resume.pdf`
- `outputs/custom/*/final/resume.html`
- `outputs/custom/*/final/resume.pdf`
- `outputs/.../final/assets/`

## Required Workflow

1. Identify the source resume version.
2. Confirm a usable local profile photo exists under `raw/assets/`.
3. Render the resume using the shared template.
4. Save the HTML result under `final/resume.html`.
5. Save or export the PDF result under `final/resume.pdf` if requested.
6. Keep any support images or icons under `final/assets/`.
7. Confirm the final HTML opens without broken links, broken images, overflow, or clipping.
8. If this skill is running inside `career-apply-pipeline`, let the pipeline own the final log entry. Otherwise, append one `output` entry to `log.md`.

## Resume Rules

- Keep the resume compact, scannable, and recruiter-friendly.
- Preserve bullet structure from the source markdown.
- Avoid portfolio-style long narrative.
- Do not add unsupported metrics just to fill layout space.
- If content does not fit, cut weaker detail before shrinking text into unreadability.

## Validation

At minimum:

- Run `git diff --check`.
- Confirm every referenced local resume asset exists.
- Open the HTML or inspect it closely enough to catch broken asset paths.

## Log Format

```md
## [YYYY-MM-DD] output | rendered resume updated

- Synced rendered resume with `outputs/.../source/resume.md`
- Wrote `outputs/.../final/resume.html`
- Wrote `outputs/.../final/resume.pdf` if requested
```
