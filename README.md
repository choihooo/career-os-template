# Career Wiki

채용 지원용 커리어 위키다. 원천 자료를 `raw/`에 쌓고, 재사용 가능한 경력 지식으로 `wiki/`에 정리한 뒤, 범용 이력서/포트폴리오와 회사별 맞춤 패키지를 `outputs/`에 만든다.

## 3분 사용법

### 1. 새 경험 추가

프로젝트, 경력, 수상 자료를 아래 예시 중 하나에 맞춰 붙여 넣고 요청한다.

- `examples/raw-project.md`
- `examples/raw-experience.md`
- `examples/raw-award.md`

요청 예시:

```md
아래 자료를 career-ingest 기준으로 반영해줘. raw에 원천을 저장하고, 관련 wiki 페이지와 sentence bank/story bank/index/log까지 갱신해줘.
```

### 2. 범용 이력서/포트폴리오 만들기

요청 예시:

```md
현재 위키 기준으로 outputs/general의 resume-general-v1, resume-general-v2, portfolio-general-v1, portfolio-general-v2를 갱신해줘.
```

결과 위치:

- `outputs/general/resume-general-v1.md`
- `outputs/general/resume-general-v2.md`
- `outputs/general/portfolio-general-v1.md`
- `outputs/general/portfolio-general-v2.md`

### 3. JD 기반 맞춤 패키지 만들기

JD 링크나 원문을 주고 요청한다.

```md
이 JD 기준으로 회사별 맞춤 패키지를 만들어줘. outputs/custom/YYYY-MM-DD-company/ 아래에 jd.md, analysis.md, strategy.md, resume.md, portfolio.md를 생성해줘.
```

결과 위치:

- `outputs/custom/YYYY-MM-DD-company/jd.md`
- `outputs/custom/YYYY-MM-DD-company/analysis.md`
- `outputs/custom/YYYY-MM-DD-company/strategy.md`
- `outputs/custom/YYYY-MM-DD-company/resume.md`
- `outputs/custom/YYYY-MM-DD-company/portfolio.md`

샘플 패키지:

- `outputs/custom/2026-05-12-example-frontend/`

## Output Types

- `outputs/general/*.md`: 제출 문서의 원본 텍스트
- `outputs/custom/*/*.md`: 회사별 맞춤 문서의 원본 텍스트
- `resume/`: A4 세로 이력서 HTML 렌더링 템플릿
- `portfolio/`: A4 세로 포트폴리오 HTML 렌더링 템플릿
- PDF: HTML 또는 markdown 산출물을 기반으로 내보낸 최종 파일

markdown은 내용의 source of truth이고, HTML/PDF는 렌더링 결과물이다.

## Repository Structure

```text
carrer-wiki/
├── AGENTS.md
├── README.md
├── index.md
├── log.md
├── examples/
├── docs/checklists/
├── raw/
│   ├── awards/
│   ├── bios/
│   ├── experiences/
│   ├── links/
│   └── projects/
├── wiki/
│   ├── awards/
│   ├── experiences/
│   ├── overview/
│   ├── output-briefs/
│   ├── projects/
│   ├── sentence-bank/
│   ├── skills/
│   ├── stories/
│   ├── templates/
│   └── themes/
├── outputs/
│   ├── custom/
│   └── general/
├── resume/
├── portfolio/
└── skills/
```

## Core Files

- `index.md`: 전체 카탈로그
- `log.md`: append-only 작업 로그
- `wiki/overview/career-overview.md`: 현재 포지셔닝과 산출 우선순위
- `wiki/themes/positioning.md`: 목표 역할, 강점, 피해야 할 주장
- `wiki/stories/story-bank.md`: STAR 스토리
- `wiki/sentence-bank/resume-bullets.md`: 재사용 가능한 이력서 bullet
- `wiki/output-briefs/general-resume-brief.md`: 범용 이력서 조립 기준
- `wiki/output-briefs/general-portfolio-brief.md`: 범용 포트폴리오 조립 기준

## Current Knowledge Base

- `wiki/experiences/eigene-korea.md`
- `wiki/projects/geobugirin.md`
- `wiki/projects/daepiro-design-system.md`
- `wiki/projects/susanghan.md`
- `wiki/awards/awards-2021-2025.md`
- `wiki/skills/frontend-engineering.md`

## Quality Rules

- 근거 없는 수치나 역할은 만들지 않는다.
- 부족한 정보는 `Gaps` 또는 `analysis.md`에 남긴다.
- 최종 산출물에는 placeholder를 남기지 않는다.
- 같은 내용을 여러 산출물에 직접 복붙하지 않는다. 먼저 `wiki/`를 갱신하고 산출물을 다시 만든다.
- 제출 전에는 `career-output-polish` 기준으로 과장된 표현과 AI식 문장 패턴을 줄인다.

## Checklists

- 개인 사용 준비도: `docs/checklists/personal-ready-checklist.md`
- 내부 베타 준비도: `docs/checklists/beta-ready-checklist.md`
- 회사별 맞춤 산출물 품질: `docs/checklists/custom-output-quality-checklist.md`
- 제품 준비도 판단 기준: `docs/checklists/product-readiness-criteria.md`
