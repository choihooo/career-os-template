# Career OS Index

권장 사용 순서: `index 확인 → 자료 준비 → career-ingest → career-build-general → career-apply-pipeline → rendered output → quality check`.

## Start Here

- [landing](docs/index.html) - Career OS 카드뉴스를 보여주는 웹 랜딩 페이지
- [guide-page](docs/guide.html) - GitHub Pages용 사용 가이드
- [directory-page](docs/directory.html) - GitHub Pages용 작업공간 인덱스
- [prompts-page](docs/prompts.html) - GitHub Pages용 요청 프롬프트
- [checklist-page](docs/checklist.html) - GitHub Pages용 제출 전 체크리스트
- [README](README.md) - 템플릿 사용법과 전체 흐름
- [AGENTS](AGENTS.md) - 에이전트 작업 규칙
- [log](log.md) - append-only 변경 기록

## Folder Roles

- `raw/` - 사용자의 원천 자료를 저장하는 입력 계층
- `wiki/` - 원천 자료를 정규화한 경력 지식 계층
- `outputs/general/source/` - 범용 이력서와 포트폴리오 markdown 원본
- `outputs/general/final/` - 범용 HTML/PDF 렌더 결과
- `outputs/custom/YYYY-MM-DD-company/source/` - 회사별 맞춤 JD, brief, resume, portfolio 원본
- `outputs/custom/YYYY-MM-DD-company/research/` - 회사 조사와 신호 정리
- `outputs/custom/YYYY-MM-DD-company/final/` - 회사별 HTML/PDF 렌더 결과
- `samples/` - 샘플 입력, 샘플 위키, 샘플 맞춤 패키지
- `templates/` - HTML/PDF/카드뉴스 렌더링 템플릿
- `docs/` - GitHub Pages 공개 문서
- `examples/` - 복붙용 입력 예시
- `skills/` - 반복 워크플로 스킬 지시서

## Examples

- [raw-project](examples/raw-project.md) - 프로젝트 입력 예시
- [raw-experience](examples/raw-experience.md) - 경력 입력 예시
- [raw-award](examples/raw-award.md) - 수상 입력 예시
- [jd](examples/jd.md) - JD 입력 예시
- [request-prompts](examples/request-prompts.md) - 복붙용 요청 프롬프트

## Checklists

- [personal-ready-checklist](docs/checklists/personal-ready-checklist.md) - 개인 사용 준비도
- [beta-ready-checklist](docs/checklists/beta-ready-checklist.md) - 베타 배포 준비도
- [custom-output-quality-checklist](docs/checklists/custom-output-quality-checklist.md) - 회사별 산출물 품질 기준
- [product-readiness-criteria](docs/checklists/product-readiness-criteria.md) - 준비도 판단 기준

## Skills

- [career-apply-pipeline](skills/career-apply-pipeline/SKILL.md) - JD에서 조사, 맞춤 패키지, polish, 선택적 렌더링, 품질 체크까지 이어지는 상위 워크플로
- [career-ingest](skills/career-ingest/SKILL.md) - 새 커리어 원천 자료 반영
- [career-ingest-github-repo](skills/career-ingest-github-repo/SKILL.md) - GitHub repo/PR/commit 근거 분석
- [career-build-general](skills/career-build-general/SKILL.md) - 범용 이력서/포트폴리오 markdown 생성
- [career-build-custom-package](skills/career-build-custom-package/SKILL.md) - 회사별 맞춤 markdown 패키지 생성
- [career-build-rendered-resume](skills/career-build-rendered-resume/SKILL.md) - 이력서 HTML/PDF 렌더링
- [career-build-rendered-portfolio](skills/career-build-rendered-portfolio/SKILL.md) - 포트폴리오 HTML/PDF 렌더링
- [career-company-research](skills/career-company-research/SKILL.md) - 회사/JD/문화/인터뷰 신호 조사
- [career-output-polish](skills/career-output-polish/SKILL.md) - 최종 이력서/포트폴리오 문장 polish
- [career-lint](skills/career-lint/SKILL.md) - 위키 구조와 산출물 상태 점검

## Samples

- [samples-guide](samples/README.md) - 샘플 자료 범위와 사용 원칙
- [sample-candidate-profile](samples/raw/bios/sample-candidate-profile.md) - 개인정보 없는 샘플 후보 프로필
- [example-product-frontend-jd-raw](samples/raw/applications/2026-05-13-example-product-frontend-jd.md) - JD 맞춤 패키지용 원천 JD
- [sample-experience](samples/raw/experiences/sample-company-intern.md) - 샘플 경력 원천
- [sample-project](samples/raw/projects/sample-dashboard.md) - 샘플 프로젝트 원천
- [sample-award](samples/raw/awards/sample-award.md) - 샘플 수상 원천
- [sample-experience-wiki](samples/wiki/experiences/sample-company.md) - 샘플 경력 정규화 페이지
- [sample-project-wiki](samples/wiki/projects/sample-dashboard.md) - 샘플 프로젝트 정규화 페이지
- [sample-award-wiki](samples/wiki/awards/sample-award.md) - 샘플 수상 정규화 페이지
- [frontend-engineering-sample](samples/wiki/skills/frontend-engineering.md) - 샘플 기술 역량 정리
- [example-product-frontend-brief](samples/custom-packages/2026-05-13-example-product-frontend/source/brief.md) - JD 맞춤 brief 예시
- [example-product-frontend-resume](samples/custom-packages/2026-05-13-example-product-frontend/source/resume.md) - JD 맞춤 이력서 예시
- [example-product-frontend-portfolio](samples/custom-packages/2026-05-13-example-product-frontend/source/portfolio.md) - JD 맞춤 포트폴리오 예시
- [example-product-frontend-resume-pdf](samples/custom-packages/2026-05-13-example-product-frontend/final/resume.pdf) - JD 맞춤 이력서 PDF 예시
- [example-product-frontend-portfolio-pdf](samples/custom-packages/2026-05-13-example-product-frontend/final/portfolio.pdf) - JD 맞춤 포트폴리오 PDF 예시
- [example-frontend-package](samples/custom-packages/2026-01-01-example-frontend/source/jd.md) - 샘플 회사별 패키지

## Raw Sources

- [profile](raw/bios/profile.md) - 이름, 연락처, 링크, 학력, 선호 직무 등 기본정보 원천
- [raw-assets-guide](raw/assets/README.md) - 프로필 사진과 프로젝트 이미지 원본 보관 규칙

## Wiki

- [career-overview](wiki/overview/career-overview.md) - 현재 포지셔닝과 산출 우선순위
- [positioning](wiki/themes/positioning.md) - 목표 역할과 반복 강점
- [resume-bullets](wiki/sentence-bank/resume-bullets.md) - 재사용 가능한 이력서 bullet 후보
- [story-bank](wiki/stories/story-bank.md) - 면접과 포트폴리오에 재사용할 STAR 스토리

## Templates and Briefs

- [experience-template](wiki/templates/experience-template.md)
- [project-template](wiki/templates/project-template.md)
- [award-template](wiki/templates/award-template.md)
- [skill-template](wiki/templates/skill-template.md)
- [general-resume-brief](wiki/output-briefs/general-resume-brief.md)
- [general-portfolio-brief](wiki/output-briefs/general-portfolio-brief.md)

## Outputs

- [general-resume-source](outputs/general/source/resume.md) - 범용 이력서 markdown 원본
- [general-portfolio-source](outputs/general/source/portfolio.md) - 범용 포트폴리오 markdown 원본
- [general-final-dir](outputs/general/final) - 범용 HTML/PDF 렌더 결과 저장 위치
- [resume-html-template](templates/resume/index.html) - 공용 이력서 HTML 템플릿
- [resume-assets-guide](templates/resume/assets/README.md) - 이력서 템플릿 자산 규칙
- [portfolio-html-template](templates/portfolio/index.html) - 공용 포트폴리오 HTML 템플릿
- [portfolio-assets-guide](templates/portfolio/assets/README.md) - 포트폴리오 템플릿 자산 규칙

## Notes

- `source/`는 사람이 수정하는 markdown 원본이며 source of truth다.
- `final/`은 실제 검수, 공유, 제출에 사용하는 렌더 결과다.
- `templates/`는 공용 HTML/CSS 템플릿만 둔다.
- 실제 작업 결과는 `outputs/custom/`에 쌓고, 데모와 설명용 결과는 `samples/custom-packages/`에서 관리한다.
- `log.md`는 과거 구조명이나 작업 맥락을 그대로 보존하는 이력 파일이다. 현재 기준 구조와 규칙은 `README.md`와 `AGENTS.md`를 우선 따른다.
