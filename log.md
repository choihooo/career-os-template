# Career Wiki Log

## [2026-05-10] init | initial design spec created

- Added the first design spec for the career wiki.
- Defined the three-layer structure: raw, wiki, outputs.

## [2026-05-12] lint | output-ready wiki scaffold 보강

- Expanded overview, positioning, story bank, and sentence bank scaffolds
- Added general resume and portfolio output briefs
- Added experience, project, award, and skill templates for future ingest

## [2026-05-12] output | 16:9 portfolio HTML template 추가

- Added `figma-portfolio/` as a horizontal portfolio deck template
- Linked the template from `index.md`, `README.md`, and the portfolio output brief
- Matched the portfolio template visual style to the existing resume HTML template

## [2026-05-12] output | Figma 기반 최호 포트폴리오 HTML 구현

- Replaced `portfolio/` placeholder content with an 8-page portfolio document
- Downloaded and localized Figma assets for profile and project images
- Verified first page and full-page rendering with Playwright screenshots
- Reworked the first page against the Figma node with fixed coordinates and matching local assets
- Reworked pages 2 and 3 against Figma nodes `2624:757` and `2624:793`
- Reworked page 4 against Figma node `2624:807`
- Reworked pages 5-8 against Figma nodes `2295:459`, `2589:1497`, `2608:551`, and `2623:727`
- Refactored `portfolio/styles.css` into reusable page, typography, box, tag, and figure primitives for future template reuse

## [2026-05-12] output | Figma 기반 최호 이력서 HTML 구현

- Added `resume/` as a three-page A4 resume HTML template
- Implemented Figma nodes `2643:986`, `2643:1160`, and `2643:1072`
- Downloaded and localized resume icon/profile assets
- Updated `README.md` and `index.md` to distinguish `resume/` from A4 portfolio `portfolio/`

## [2026-05-12] output | HTML 산출물 디렉터리명 정리

- Renamed `figma-resume/` to `portfolio/`
- Renamed `html-resume/` to `resume/`

## [2026-05-12] lint | 미사용 HTML 템플릿 및 이미지 정리

- Removed obsolete `figma-portfolio/` horizontal template
- Removed unused image assets from `portfolio/assets/` and `resume/assets/`

## [2026-05-12] ingest | HTML 산출물 기반 커리어 지식 역반영

- Added raw sources for 아이겐코리아, 거부기린, 대피로 디자인 시스템, 수상한 녀석들, 수상/외부활동
- Created normalized wiki pages under `wiki/experiences/`, `wiki/projects/`, `wiki/awards/`, and `wiki/skills/`
- Updated career overview, positioning, sentence bank, and story bank for JD matching

## [2026-05-12] output | 범용 이력서/포트폴리오 markdown 완성

- Updated `outputs/general/resume-general-v1.md`
- Updated `outputs/general/resume-general-v2.md`
- Updated `outputs/general/portfolio-general-v1.md`
- Updated `outputs/general/portfolio-general-v2.md`
- Removed placeholder-only general outputs

## [2026-05-12] output | 내부 베타용 샘플과 온보딩 보강

- Added `examples/` input templates and request prompts
- Added readiness and output quality checklists under `docs/checklists/`
- Added sample custom package under `outputs/custom/2026-05-12-example-frontend/`
- Reworked `README.md` and `index.md` for product onboarding

## [2026-05-12] lint | 제품 준비도 판단 기준 문서화

- Added `docs/checklists/product-readiness-criteria.md`
- Documented personal, beta, and external readiness gates
- Linked readiness criteria from `README.md` and `index.md`
