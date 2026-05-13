# Career OS Log

이 파일은 append-only로 유지한다. 템플릿을 복사한 뒤 실제 작업부터 아래에 기록한다.

## [2026-01-01] init | template initialized

- Started from Career OS Template
- Keep future ingest, output, research, and lint entries below this line

## [2026-01-01] output | profile and asset structure documented

- Added `raw/bios/profile.md` for basic profile information
- Added asset guide files under `raw/assets/`, `resume/assets/`, and `portfolio/assets/`
- Updated README, index, and AGENTS with profile and asset placement rules

## [2026-05-13] output | landing page added

- Added a static root landing page for the Career OS template
- Linked the landing page from `README.md` and `index.md`

## [2026-05-13] output | card news landing connected

- Copied existing Career OS card news into `card-news/career-os-template/`
- Updated root landing page to show the exported PNG cards

## [2026-05-13] output | guide pages added

- Added HTML pages for guide, index, prompts, and checklist
- Updated landing navigation to link to HTML pages instead of markdown files

## [2026-05-13] output | JD-tailored sample package added

- Added raw sample candidate profile and Example Product frontend JD
- Added `outputs/custom/2026-05-13-example-product-frontend/` with jd, analysis, strategy, resume, and portfolio

## [2026-05-13] output | rendered resume and portfolio updated

- Kept root `resume/` and `portfolio/` as reusable HTML templates
- Exported `resume.pdf` and `portfolio.pdf` into the custom package rendered folder
- Copied the rendered resume and portfolio HTML/CSS into the custom package rendered folder

## [2026-05-13] output | sample package enriched with assets and cases

- Added additional sample raw experience and project memos
- Generated sample PNG assets for profile, dashboard, workflow, and form system pages
- Expanded the rendered sample resume to 3 pages and portfolio to 6 pages

## [2026-05-13] output | sample package converted to detailed persona

- Reworked the sample candidate into the fictional persona `정유진`
- Replaced generic sample company and project names with a coherent B2B SaaS narrative
- Updated raw memos, rendered HTML, and generated PNG assets to match the persona

## [2026-05-13] output | resume experience density improved

- Expanded the rendered resume with additional work items, project details, award, evidence, and working style sections
- Updated the matching markdown resume so the sample package reads like a fuller candidate profile

## [2026-05-13] output | resume third page replaced with credentials

- Removed template guidance sections from the rendered resume third page
- Replaced them with awards, activities, certifications, coursework, skills, and education

## [2026-05-13] output | resume credentials page filled

- Added more awards and external experiences to fill the rendered resume third page
- Kept the page limited to education, certification, awards, and external experience

## [2026-05-13] output | portfolio sample enriched with assets

- Generated a person profile image and additional project screen assets
- Expanded the rendered portfolio with dashboard detail, review detail, form error mapping, and QA checklist pages
- Updated the source portfolio markdown to match the richer case-study structure

## [2026-05-13] output | portfolio final summary page removed

- Removed the internal JD summary page from the rendered sample portfolio
- Updated the cover contents and regenerated the portfolio PDF

## [2026-05-13] output | rendered profile image replaced

- Replaced the sample resume and portfolio profile image with the provided profile photo
- Regenerated the rendered resume and portfolio PDFs

## [2026-05-13] output | profile image rendering fixed

- Removed the resume profile image corner mask that exposed the gray frame
- Added a cache-busting query to the portfolio profile image reference
- Regenerated the rendered resume and portfolio PDFs

## [2026-05-13] skill | profile photo required before rendering

- Added a profile photo gate to rendered resume and portfolio skills
- Added the same gate to the application pipeline before HTML/PDF generation
- Prevented final rendering with initials, gray boxes, generated placeholders, remote images, or broken profile image fallbacks
