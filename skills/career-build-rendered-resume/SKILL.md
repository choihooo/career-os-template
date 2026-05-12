---
name: career-build-rendered-resume
description: Use when generating or updating the polished HTML/CSS resume render output in this career wiki, especially resume/index.html, resume/styles.css, and resume/assets from the current markdown resume output and wiki knowledge.
---

# Career Build Rendered Resume

## Purpose

이 스킬은 제출용 이력서 markdown 원본을 기반으로 `resume/`의 HTML/CSS 렌더링 산출물을 갱신할 때 사용한다.

`career-build-general`, `career-build-custom-package`, 또는 `career-apply-pipeline`이 이력서 내용 원본을 만든 뒤, 이 스킬은 실제로 열어 보는 A4 이력서 화면을 만든다.

## Read Order

Read these files before writing:

1. `AGENTS.md`
2. `index.md`
3. Resume source content:
   - default: `outputs/general/resume-general-v2.md`
   - alternative: `outputs/general/resume-general-v1.md`
   - company-specific: `outputs/custom/*/resume.md`
4. Supporting wiki pages only when needed:
   - `wiki/overview/career-overview.md`
   - `wiki/themes/positioning.md`
   - relevant experience, project, award, and skill pages
5. Existing rendered resume files:
   - `resume/index.html`
   - `resume/styles.css`

## Output Targets

Only write to these paths unless the user explicitly asks for more:

- `resume/index.html`
- `resume/styles.css`
- `resume/assets/*`
- `log.md`

Do not rewrite source markdown unless the rendered-output work reveals a factual source error that must be fixed first.

## Required Workflow

1. Identify the resume source version.
2. Compare the source resume against the current `resume/index.html`.
3. Update the HTML so visible resume content matches the chosen source.
4. Preserve the existing visual system unless the user asks for a redesign:
   - A4 page structure
   - compact recruiter-friendly hierarchy
   - local asset usage
   - print-friendly page boundaries
5. Keep assets local under `resume/assets/`.
6. Remove stale visible content that no longer exists in the chosen source.
7. Check for:
   - text overflow
   - broken links
   - missing images
   - inconsistent page numbering
   - excessive unused white space on each page
   - weak bullets copied only to fill layout space
8. If a browser or screenshot workflow is available, render-check the first page and every page touched by the edit.
9. If this skill is running inside `career-apply-pipeline`, report verification results back to the pipeline and let it own the final log entry. Otherwise, append one `output` entry to `log.md`.

## Resume Rules

- Keep the resume compact, scannable, and recruiter-friendly.
- Render resume content in 개조식 by default. The visible HTML should preserve bullet structure instead of turning source bullets into paragraphs.
- Prioritize summary, strongest experience, strongest projects, skills, awards, and links.
- Use bullets only when they carry concrete evidence.
- Avoid portfolio-style long narrative.
- Do not add unsupported metrics just to fill layout space.
- If content does not fit, cut weaker detail before shrinking text into unreadability.
- Summary areas may use a one-line positioning statement, but evidence and fit should be expressed as short bullets or compact rows.
- For experience and project sections, keep each bullet focused on one fact/action/result unit.
- Do not leave large empty areas when defensible source content exists. Fill pages with relevant evidence before ending the document.
- It is acceptable for content to move between pages or for the resume to gain additional pages if readability and layout integrity are preserved.
- Prefer adding stronger source-backed bullets, links, awards, education, external activity, or concise fit rows over stretching spacing or increasing font size.
- Never fill space with weak repetition. Empty space is better than padding, but source-backed detail should not be omitted solely to keep the page count low.

## HTML/CSS Rules

- Prefer editing the existing static HTML/CSS directly.
- Keep the output usable by opening `resume/index.html` in a browser.
- Use semantic structure where practical: `main`, `article`, `section`, `header`, `nav`, `figure`.
- Keep image `alt` text meaningful when the image carries content; use empty `alt` only for decorative icons.
- Do not reference remote images for core assets.
- Keep print layout stable with explicit page dimensions and predictable page breaks.
- Page count is flexible. Do not force all content into a fixed number of pages if doing so creates clipping, overlap, unreadable text, or excessive blank space.

## Validation

At minimum:

- Run `git diff --check`.
- Inspect changed HTML around edited sections.
- Confirm every referenced local resume asset exists.

When feasible:

- Start a local static server.
- Open `resume/index.html` in a browser.
- Check screenshots for overflow, broken images, and page boundary issues.

## Log Format

```md
## [YYYY-MM-DD] output | rendered resume updated

- Updated `resume/index.html` and/or `resume/styles.css`
- Synced rendered resume with `outputs/...`
- Verified local assets and layout basics
```

## Stop Conditions

Stop and ask the user if:

- the source resume and current rendered page disagree on important facts
- the user asks for a redesign but no target format or visual direction is clear
- required image assets are missing and cannot be replaced with existing local assets
- fitting the content would require deleting major evidence from the source resume
