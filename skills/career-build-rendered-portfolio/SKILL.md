---
name: career-build-rendered-portfolio
description: Use when generating or updating the polished HTML/CSS portfolio render output in this career wiki, especially portfolio/index.html, portfolio/styles.css, and portfolio/assets from the current markdown portfolio output and wiki knowledge.
---

# Career Build Rendered Portfolio

## Purpose

이 스킬은 제출용 포트폴리오 markdown 원본을 기반으로 `portfolio/`의 HTML/CSS 렌더링 산출물을 갱신할 때 사용한다.

`career-build-general`, `career-build-custom-package`, 또는 `career-apply-pipeline`이 포트폴리오 내용 원본을 만든 뒤, 이 스킬은 실제로 열어 보는 A4 포트폴리오 화면을 만든다.

## Read Order

Read these files before writing:

1. `AGENTS.md`
2. `index.md`
3. Portfolio source content:
   - default: `outputs/general/portfolio-general-v2.md`
   - alternative: `outputs/general/portfolio-general-v1.md`
   - company-specific: `outputs/custom/*/portfolio.md`
4. Supporting wiki pages:
   - `wiki/overview/career-overview.md`
   - `wiki/themes/positioning.md`
   - `wiki/stories/story-bank.md`
   - relevant project, experience, award, and skill pages
5. Existing rendered portfolio files:
   - `portfolio/index.html`
   - `portfolio/styles.css`

## Output Targets

Only write to these paths unless the user explicitly asks for more:

- `portfolio/index.html`
- `portfolio/styles.css`
- `portfolio/assets/*`
- `log.md`

Do not rewrite source markdown unless the rendered-output work reveals a factual source error that must be fixed first.

## Required Workflow

1. Identify the portfolio source version.
2. Run the required profile photo gate before editing rendered files:
   - Confirm at least one original profile photo exists under `raw/assets/`:
     - `raw/assets/profile-photo.png`
     - `raw/assets/profile-photo.jpg`
     - `raw/assets/profile-photo.jpeg`
     - `raw/assets/profile-photo-square.png`
   - Confirm a portfolio-ready local image exists at `portfolio/assets/profile.png` or in the target rendered portfolio asset folder for company-specific output.
   - Do not use initials, gray boxes, generated placeholders, remote images, or broken image fallbacks in place of a profile photo.
   - If the user provided a photo in the current task, copy or convert it into the required local asset paths before continuing.
   - If no usable profile photo is available, stop before HTML/PDF generation and ask the user to provide one.
3. Compare the source portfolio against the current `portfolio/index.html`.
4. Update the HTML so visible portfolio content matches the chosen source.
5. Preserve the existing visual system unless the user asks for a redesign:
   - A4 page structure
   - project case-study hierarchy
   - local asset usage
   - print-friendly page boundaries
6. Keep assets local under `portfolio/assets/`.
7. Remove stale visible content that no longer exists in the chosen source.
8. Check for:
   - text overflow
   - broken links
   - missing images
   - inconsistent page numbering
   - case studies that read like copied resume bullets
9. If a browser or screenshot workflow is available, render-check the cover page and every page touched by the edit.
10. If this skill is running inside `career-apply-pipeline`, report verification results back to the pipeline and let it own the final log entry. Otherwise, append one `output` entry to `log.md`.

## Portfolio Rules

- Treat each project section as a case study, not a resume copy.
- Show problem, decision, action, and result.
- Keep proof links, images, architecture diagrams, or screenshots close to the related project.
- Preserve narrative flow across pages.
- If space is tight, reduce weaker projects before shrinking text into unreadability.
- Do not paste resume bullets verbatim unless a short repeated fact is unavoidable.

## HTML/CSS Rules

- Prefer editing the existing static HTML/CSS directly.
- Keep the output usable by opening `portfolio/index.html` in a browser.
- Use semantic structure where practical: `main`, `article`, `section`, `header`, `nav`, `figure`.
- Keep image `alt` text meaningful when the image carries content; use empty `alt` only for decorative icons.
- Do not reference remote images for core assets.
- Keep print layout stable with explicit page dimensions and predictable page breaks.

## Validation

At minimum:

- Run `git diff --check`.
- Inspect changed HTML around edited sections.
- Confirm every referenced local portfolio asset exists.

When feasible:

- Start a local static server.
- Open `portfolio/index.html` in a browser.
- Check screenshots for overflow, broken images, and page boundary issues.

## Log Format

```md
## [YYYY-MM-DD] output | rendered portfolio updated

- Updated `portfolio/index.html` and/or `portfolio/styles.css`
- Synced rendered portfolio with `outputs/...`
- Verified local assets and layout basics
```

## Stop Conditions

Stop and ask the user if:

- the source portfolio and current rendered page disagree on important facts
- the user asks for a redesign but no target format or visual direction is clear
- no usable profile photo exists in the required local asset paths
- required image assets are missing and cannot be replaced with existing local assets
- fitting the content would require deleting major evidence from the source portfolio
