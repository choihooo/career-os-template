# Career OS Agent Guide

## Purpose

이 저장소는 채용 지원용 resume-only Career OS 템플릿이다. 사용자의 원천 자료를 `raw/`에 보존하고, `wiki/`에서 claim/proof 중심의 경력 지식으로 정규화한 뒤, `outputs/`에 범용 또는 회사별 맞춤 이력서를 생성한다.

## Mandatory Read Order

작업을 시작할 때는 아래 순서를 따른다.

1. `AGENTS.md`
2. `index.md`
3. `log.md`
4. 해당 `skills/cos-*/SKILL.md`
5. 관련 `raw/`, `wiki/`, `outputs/` 파일

## Layer Rules

### raw/

- Source layer다.
- 원천 자료, 링크, JD, 증빙 설명, 이미지 원본을 저장한다.
- 사실 원형을 보존하고 덮어쓰기보다 추가를 우선한다.
- 새 자료 등록은 `cos-register-source`를 우선 사용한다.

### wiki/

- Knowledge layer다.
- 경험, 프로젝트, 활동, 수상, 기술, story, resume bullet, claim, proof를 관리한다.
- 직접 제출하지 않는 중간 컴파일 결과물이다.
- raw source를 정규화할 때는 `cos-ingest`를 사용한다.

### outputs/

- Output layer다.
- 제출 가능한 이력서와 제출 직전 markdown 원본을 저장한다.
- 범용본은 `outputs/general/`에 보관한다.
- 회사별 맞춤본은 `outputs/custom/YYYY-MM-DD-company-role/`에 보관한다.
- 수정은 `source/`에서 하고, 검수/공유/제출은 `final/`에서 한다.

## Standard Output Files

### General

- `outputs/general/source/resume.md`
- optional `outputs/general/final/resume.html`
- optional `outputs/general/final/resume.pdf`

### Company-specific Package

Required:

- `source/jd.md`
- `source/brief.md`
- `source/resume.md`

Optional research:

- `research/company.md`
- `research/signals.md`

Optional rendered files:

- `final/resume.html`
- `final/resume.pdf`
- `final/assets/`

## Recommended User Flow

1. Read `index.md`.
2. Fill `raw/profile/profile.md`, `raw/profile/links.md`, and `raw/profile/preferences.md`.
3. Store original profile and evidence assets in `raw/assets/`.
4. Add source material with `cos-register-source`.
5. Promote verified source material with `cos-ingest`.
6. Build the general source resume with `cos-build-resume`.
7. Render HTML/PDF only when needed with `cos-render-resume`.
8. Build JD-specific resume packages with `cos-apply-resume`.
9. Run `cos-lint` before submission.

## Workflows

### Register Source

1. 새 자료를 `raw/`의 새 taxonomy에 저장한다.
2. raw frontmatter에 `type`, `id`, `status`, `evidence_strength`를 기록한다.
3. 애매한 자료는 `raw/inbox/`에 둔다.
4. `index.md`와 `log.md`를 필요한 범위에서 갱신한다.

### Ingest

1. 관련 raw source와 기존 wiki 페이지를 먼저 읽는다.
2. 핵심 사실, 수치, 재사용 가능한 문장을 추출한다.
3. 관련 `wiki/` 페이지와 `wiki/sentence-bank/`, `wiki/stories/`를 업데이트한다.
4. 강한 주장은 `wiki/claims-ledger.md`와 `wiki/proof-map.md`에 연결한다.
5. `index.md`와 `log.md`를 갱신한다.

### Build General Resume

1. `wiki/overview/`, `wiki/themes/`, `wiki/claims-ledger.md`, `wiki/proof-map.md`를 우선 읽는다.
2. `wiki/output-briefs/general-resume-brief.md`에서 조립 기준을 확인한다.
3. `outputs/general/source/resume.md`를 갱신한다.
4. 최종 저장 전에 quality gate로 과장 표현, AI식 문장, unsupported claim을 제거한다.
5. HTML/PDF가 필요하면 `outputs/general/final/`에 렌더한다.
6. `log.md`에 변경 이유를 기록한다.

### Build Company-specific Resume

1. `outputs/custom/YYYY-MM-DD-company-role/` 디렉터리를 만든다.
2. `source/jd.md`에 JD 원문 또는 요약을 저장한다.
3. `source/brief.md`에 요구사항, 강조 포인트, 제외 포인트, gaps를 정리한다.
4. `source/resume.md`를 생성한다.
5. 필요하면 `research/company.md`, `research/signals.md`를 생성한다.
6. 최종 저장 전에 quality gate로 근거와 문체를 검수한다.
7. HTML/PDF가 필요하면 `final/`에 렌더한다.
8. 새롭게 정리된 강점이나 문장은 `wiki/`에 역반영한다.
9. `log.md`에 output 항목을 append 한다.

## Sample Repository Policy

- 실제 사용자 원천 자료는 이 레포의 `raw/`에 저장한다.
- 실제 사용자 정규화 지식은 이 레포의 `wiki/`에 저장한다.
- 실제 제출용 산출물은 이 레포의 `outputs/`에 저장한다.
- 데모 데이터와 예제 산출물은 별도 `career-os-template-samples` 레포에서 관리한다.

## Writing Rules

- 기본 언어는 한국어다.
- 사실과 해석을 섞지 않는다.
- 근거 없는 수치나 역할을 만들지 않는다.
- 새 경험, 프로젝트, 활동, 수상, 기술 페이지는 가능하면 `wiki/templates/`의 템플릿 구조를 따른다.
- 회사명은 가능하면 ASCII 소문자 slug를 사용한다.
- 맞춤본은 반드시 디렉터리 단위로 관리한다.
- `source/`가 source of truth다.
- 포트폴리오 산출물은 현재 scope에 포함하지 않는다.

## Index and Log

`index.md`는 주요 페이지를 분류별 링크와 한 줄 설명으로 정리한다.

`log.md`는 append-only 파일로 유지한다. 대표 항목 타입은 `ingest`, `output`, `lint`이며 필요하면 `init`, `setup`, `skill`, `research` 같은 타입도 사용할 수 있다. 각 항목은 아래 형식을 따른다.

```md
## [YYYY-MM-DD] ingest | 프로젝트 foo 소개 추가
## [YYYY-MM-DD] output | YYYY-MM-DD-company-role 맞춤 이력서 생성
## [YYYY-MM-DD] lint | claim/proof 연결 점검
```
