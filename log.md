# Career OS Log

이 파일은 append-only로 유지한다. 템플릿을 복사한 뒤 실제 작업부터 아래에 기록한다.
대표 항목 타입은 `ingest`, `output`, `lint`이며 필요하면 `init`, `setup`, `skill`, `research` 같은 타입도 사용할 수 있다.
이 파일은 과거 작업 이력을 보존하므로 이전 구조명이나 이전 운영 맥락이 남아 있을 수 있다. 현재 기준 구조와 규칙은 `README.md`, `AGENTS.md`, `index.md`를 우선 따른다.
현재 구조는 resume-only다. output 구조는 `outputs/general/source|final`과 `outputs/custom/YYYY-MM-DD-company-role/source|research|final` 기준으로 해석한다.
현재 스킬명은 `cos-*` 기준이며, 과거 `career-*` 항목은 historical log로만 해석한다.
데모 데이터와 예제 산출물은 별도 `career-os-template-samples` 레포 정책으로 해석한다.

## [2026-01-01] init | template initialized

- Career OS Template에서 시작
- 이후 ingest, output, research, lint, setup, skill 기록을 아래에 이어서 추가

## [2026-01-01] output | profile and asset structure documented

- 기본 프로필 정보용 `raw/bios/profile.md` 추가
- `raw/assets/`, `resume/assets/`, `portfolio/assets/` 아래 에셋 가이드 파일 추가
- 프로필과 에셋 배치 규칙에 맞춰 README, index, AGENTS 갱신

## [2026-05-13] output | landing page added

- Career OS 템플릿용 정적 랜딩 페이지 추가
- `README.md`, `index.md`에서 랜딩 페이지로 연결

## [2026-05-13] output | card news landing connected

- 기존 Career OS 카드뉴스를 `card-news/career-os-template/`로 복사
- export된 PNG 카드를 루트 랜딩 페이지에서 보이도록 연결

## [2026-05-13] output | guide pages added

- guide, index, prompts, checklist용 HTML 페이지 추가
- 랜딩 네비게이션이 markdown 대신 HTML 페이지를 가리키도록 갱신

## [2026-05-13] output | JD-tailored sample package added

- 샘플 후보 프로필 원천과 Example Product frontend JD 추가
- `outputs/custom/2026-05-13-example-product-frontend/`에 jd, analysis, strategy, resume, portfolio 추가

## [2026-05-13] output | rendered resume and portfolio updated

- 루트 `resume/`, `portfolio/`를 재사용 가능한 HTML 템플릿으로 유지
- `resume.pdf`, `portfolio.pdf`를 맞춤 패키지 rendered 폴더로 export
- 렌더링된 resume, portfolio HTML/CSS를 맞춤 패키지 rendered 폴더로 복사

## [2026-05-13] output | sample package enriched with assets and cases

- 샘플 raw 경험과 프로젝트 메모 추가
- profile, dashboard, workflow, form system용 샘플 PNG 에셋 생성
- rendered 샘플 resume을 3페이지, portfolio를 6페이지로 확장

## [2026-05-13] output | sample package converted to detailed persona

- 샘플 후보를 가상의 페르소나 `정유진`으로 재구성
- 일반적인 샘플 회사명과 프로젝트명을 일관된 B2B SaaS 서사에 맞게 교체
- raw 메모, rendered HTML, 생성 PNG 에셋을 페르소나에 맞게 갱신

## [2026-05-13] output | resume experience density improved

- rendered resume에 추가 업무 항목, 프로젝트 상세, 수상, 근거, working style 섹션 확장
- 샘플 패키지가 더 풍부한 후보 프로필처럼 읽히도록 대응 markdown resume 갱신

## [2026-05-13] output | resume third page replaced with credentials

- rendered resume 3페이지에서 템플릿 안내 섹션 제거
- 해당 영역을 수상, 활동, 자격, coursework, skills, education으로 교체

## [2026-05-13] output | resume credentials page filled

- rendered resume 3페이지를 채우기 위해 추가 수상과 외부 경험 보강
- 페이지 범위를 education, certification, awards, external experience로 제한

## [2026-05-13] output | portfolio sample enriched with assets

- 인물 프로필 이미지와 추가 프로젝트 화면 에셋 생성
- rendered portfolio에 dashboard detail, review detail, form error mapping, QA checklist 페이지 확장
- 더 풍부한 케이스 스터디 구조에 맞게 source portfolio markdown 갱신

## [2026-05-13] output | portfolio final summary page removed

- rendered 샘플 portfolio에서 내부 JD 요약 페이지 제거
- 표지 목차를 갱신하고 portfolio PDF 재생성

## [2026-05-13] output | rendered profile image replaced

- 샘플 resume, portfolio 프로필 이미지를 제공된 프로필 사진으로 교체
- rendered resume, portfolio PDF 재생성

## [2026-05-13] output | profile image rendering fixed

- 회색 프레임이 드러나던 resume 프로필 이미지 코너 마스크 제거
- portfolio 프로필 이미지 참조에 cache-busting query 추가
- rendered resume, portfolio PDF 재생성

## [2026-05-13] skill | profile photo required before rendering

- rendered resume, portfolio 스킬에 프로필 사진 게이트 추가
- HTML/PDF 생성 전 application pipeline에도 같은 게이트 추가
- initials, 회색 박스, 생성 placeholder, remote image, 깨진 fallback 이미지로 최종 렌더링되지 않도록 제한

## [2026-05-13] setup | repository structure cleaned up

- 재사용 가능한 render, card-news 소스를 `templates/` 아래로 이동
- GitHub Pages HTML/CSS 진입 파일을 `docs/` 아래로 이동
- GitHub Pages 배포 아티팩트를 `docs/`로 제한
- 새 경로에 맞게 README, index, agent guide, skills 갱신

## [2026-05-16] setup | sample artifacts grouped under samples

- 샘플 raw 입력, 샘플 wiki 페이지, 샘플 custom package를 `samples/` 아래로 이동
- 실제 작업용 `raw/`, `wiki/`, `outputs/custom/`과 데모용 샘플 경로를 분리
- README, index, checklist, docs directory, 샘플 내부 참조 경로를 새 구조에 맞게 갱신

## [2026-05-16] setup | output structure simplified

- 범용 산출물을 `outputs/general/source/`와 `outputs/general/final/` 구조로 단순화
- 회사별 맞춤 패키지를 `source/`, `research/`, `final/` 구조로 재정의
- `analysis.md`, `strategy.md`를 `brief.md` 중심 구조로 통합
- 샘플 custom package와 스킬 문서를 새 output 구조에 맞게 갱신

## [2026-06-24] setup | resume-only cos workflow structure applied

- Moved profile source from `raw/bios/profile.md` to `raw/profile/profile.md`
- Added raw taxonomy folders for profile, activities, applications, evidence, assets, and inbox
- Added `wiki/claims-ledger.md`, `wiki/proof-map.md`, and `wiki/activities/`
- Removed in-repo sample package/data tree and portfolio output/template targets
- Replaced legacy workflow skills with `cos-*` resume-only skills
- Updated README, AGENTS, index, and layer README files to the v0.2 structure

## [2026-06-24] skill | resume template contract tightened

- Added read-only shared template rules to `cos-render-resume`
- Added resume content contract gates to build, apply, render, and general resume brief
- Aligned the general resume source example with About Me, Work Experience, Projects, and Awards & Activities
- Removed remaining active portfolio usage wording from wiki templates
- Removed resume template section-specific bullet indentation override
- Standardized contribution blocks as environment/problem summary, main implementation bullet, nested detail bullets, and result line
