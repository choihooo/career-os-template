# Career OS Index

권장 사용 순서: `index 확인 → cos-register-source → cos-ingest → cos-build-resume → cos-apply-resume → cos-render-resume → cos-lint`.

## Start Here

- [README](README.md) - 템플릿 사용법과 전체 흐름
- [AGENTS](AGENTS.md) - 에이전트 작업 규칙
- [log](log.md) - append-only 변경 기록
- [raw-readme](raw/README.md) - Source layer taxonomy
- [wiki-readme](wiki/README.md) - Knowledge layer 운영 기준
- [outputs-readme](outputs/README.md) - resume-only Output 기준
- [architecture](docs/architecture.html) - v0.2 설계 기록

## Public Docs

- [landing](docs/index.html) - Career OS 웹 랜딩 페이지
- [guide-page](docs/guide.html) - GitHub Pages용 사용 가이드
- [directory-page](docs/directory.html) - GitHub Pages용 작업공간 인덱스
- [prompts-page](docs/prompts.html) - GitHub Pages용 요청 프롬프트
- [checklist-page](docs/checklist.html) - GitHub Pages용 제출 전 체크리스트

## Folder Roles

- `raw/` - 사용자의 원천 자료를 저장하는 Source layer
- `wiki/` - 원천 자료를 정규화한 Knowledge layer
- `outputs/general/source/` - 범용 이력서 markdown 원본
- `outputs/general/final/` - 범용 이력서 HTML/PDF 렌더 결과
- `outputs/custom/YYYY-MM-DD-company-role/source/` - 회사별 맞춤 JD, brief, resume 원본
- `outputs/custom/YYYY-MM-DD-company-role/research/` - 회사 조사와 신호 정리
- `outputs/custom/YYYY-MM-DD-company-role/final/` - 회사별 이력서 HTML/PDF 렌더 결과
- `templates/resume/` - 이력서 HTML/PDF 렌더링 템플릿
- `docs/` - GitHub Pages 공개 문서
- `examples/` - 복붙용 입력 예시
- `skills/` - 반복 워크플로 스킬 지시서

## Raw Sources

- [raw-profile](raw/profile/profile.md) - 기본정보 원천
- [raw-links](raw/profile/links.md) - 공개 링크와 보조 링크
- [raw-preferences](raw/profile/preferences.md) - 목표 역할과 포지셔닝 경계
- [raw-assets-guide](raw/assets/README.md) - 프로필 사진과 증빙 파일 원본 보관 규칙

## Wiki

- [career-overview](wiki/overview/career-overview.md) - 현재 포지셔닝과 산출 우선순위
- [positioning](wiki/themes/positioning.md) - 목표 역할과 반복 강점
- [claims-ledger](wiki/claims-ledger.md) - 사용 가능한 claim 목록
- [proof-map](wiki/proof-map.md) - proof와 source 연결
- [resume-bullets](wiki/sentence-bank/resume-bullets.md) - 재사용 가능한 이력서 bullet 후보
- [story-bank](wiki/stories/story-bank.md) - 면접과 이력서에 재사용할 STAR/CAR 스토리

## Templates and Briefs

- [experience-template](wiki/templates/experience-template.md)
- [project-template](wiki/templates/project-template.md)
- [activity-template](wiki/templates/activity-template.md)
- [award-template](wiki/templates/award-template.md)
- [skill-template](wiki/templates/skill-template.md)
- [general-resume-brief](wiki/output-briefs/general-resume-brief.md)
- [resume-html-template](templates/resume/index.html)
- [resume-assets-guide](templates/resume/assets/README.md)

## Skills

- [cos-register-source](skills/cos-register-source/SKILL.md) - 외부 자료를 raw taxonomy에 안전하게 저장
- [cos-ingest](skills/cos-ingest/SKILL.md) - raw를 wiki, claim, proof, story, bullet로 승격
- [cos-ingest-github-repo](skills/cos-ingest-github-repo/SKILL.md) - GitHub repo/PR/commit 근거를 raw evidence로 수집
- [cos-build-resume](skills/cos-build-resume/SKILL.md) - 범용 이력서 markdown 생성
- [cos-apply-resume](skills/cos-apply-resume/SKILL.md) - JD 맞춤 이력서 패키지 생성
- [cos-render-resume](skills/cos-render-resume/SKILL.md) - 이력서 HTML/PDF 렌더링
- [cos-lint](skills/cos-lint/SKILL.md) - 레이어 경계, claim/proof, output 상태 점검

## Examples

- [raw-project](examples/raw-project.md) - 프로젝트 입력 예시
- [raw-experience](examples/raw-experience.md) - 경력 입력 예시
- [raw-award](examples/raw-award.md) - 수상 입력 예시
- [jd](examples/jd.md) - JD 입력 예시
- [request-prompts](examples/request-prompts.md) - 복붙용 요청 프롬프트

## Checklists

- [personal-ready-checklist](docs/checklists/personal-ready-checklist.md) - 개인 사용 준비도
- [beta-ready-checklist](docs/checklists/beta-ready-checklist.md) - 베타 배포 준비도
- [custom-output-quality-checklist](docs/checklists/custom-output-quality-checklist.md) - 회사별 이력서 품질 기준
- [product-readiness-criteria](docs/checklists/product-readiness-criteria.md) - 준비도 판단 기준

## Outputs

- [general-resume-source](outputs/general/source/resume.md) - 범용 이력서 markdown 원본
- [general-final-dir](outputs/general/final) - 범용 HTML/PDF 렌더 결과 저장 위치

## Notes

- `source/`는 사람이 수정하는 markdown 원본이며 source of truth다.
- `final/`은 검수, 공유, 제출에 사용하는 렌더 결과다.
- `templates/`는 공용 HTML/CSS 템플릿만 둔다.
- 과거 log나 architecture audit에는 이전 구조명이 남아 있을 수 있다. 현재 기준 구조와 규칙은 `README.md`, `AGENTS.md`, 이 파일을 우선 따른다.
