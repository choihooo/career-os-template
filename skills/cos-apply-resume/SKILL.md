---
name: cos-apply-resume
description: Use when creating a JD-specific resume package with jd.md, brief.md, resume.md, optional research, and optional rendered resume files.
---

# COS Apply Resume

## Layer Movement

JD + `wiki/` Knowledge layer -> `outputs/custom/YYYY-MM-DD-company-role/` resume package.

## When to use

사용자가 JD, 회사명, 역할명, 채용 링크를 제공하고 맞춤 이력서 패키지를 만들거나 갱신하길 원할 때 사용한다.

## Inputs

- JD URL 또는 원문
- 회사명과 역할명
- 기존 custom package folder
- 선택적 회사 조사 요구

## Read first

1. `AGENTS.md`
2. `index.md`
3. `log.md`
4. `outputs/README.md`
5. `wiki/README.md`
6. `wiki/overview/career-overview.md`
7. `wiki/themes/positioning.md`
8. `wiki/claims-ledger.md`
9. `wiki/proof-map.md`
10. `wiki/sentence-bank/resume-bullets.md`
11. 기존 target package files
12. JD 또는 회사 context

## Allowed edits

- `raw/applications/**` if saving source JD is needed
- `outputs/custom/YYYY-MM-DD-company-role/source/jd.md`
- `outputs/custom/YYYY-MM-DD-company-role/source/brief.md`
- `outputs/custom/YYYY-MM-DD-company-role/source/resume.md`
- `outputs/custom/YYYY-MM-DD-company-role/research/**`
- 요청 시 `outputs/custom/YYYY-MM-DD-company-role/final/resume.html`
- 요청 시 `outputs/custom/YYYY-MM-DD-company-role/final/resume.pdf`
- 명확한 reusable backfill이 필요할 때 관련 `wiki/**`
- `log.md`

## Forbidden edits

- `templates/resume/**`
- 포트폴리오 파일 생성
- 근거 없는 fit, 수치, 직무 경험 추가
- 여러 회사나 역할을 한 패키지에 섞기
- 사용자 확인 없는 외부 제출/전송

## Resume content contract

`source/resume.md` must be shaped for the shared resume template.

- 기본 섹션은 `About Me`, `Work Experience`, `Projects`, `Awards & Activities`만 사용한다.
- `Skills`, `Education`, 또는 다른 새 섹션이 필요하면 shared template-design change로 분리한다.
- Work Experience와 Projects는 같은 content shape을 사용한다.
- 각 Work Experience item은 회사/역할명, 1문장 소개, 2개 이상의 contribution block을 가진다.
- 각 Project item은 프로젝트명, 1문장 소개, 2개 이상의 contribution block을 가진다.
- 각 contribution block은 제목, 태그 3-5개, 환경/문제/필요성이 드러나는 1-2줄 요약, 큰 구현 bullet, 하위 구현 detail bullet, Result line으로 작성한다.
- 요약은 구현 방법을 반복하지 않고 어떤 업무/서비스 환경에서 어떤 문제가 실제로 있었고 왜 재발 방지나 개선이 필요했는지 설명한다. 필요하면 두 줄까지 허용한다.
- 기본 기능 구현처럼 강한 문제 해결 claim이 없는 경우, 요약은 "구현해야 했던 상황"만 설명한다.
- 기술적 선택이 있으면 큰 구현 bullet에서 `A vs B` 선택과 이유를 쓴다.
- 기술적 선택이 없으면 큰 구현 bullet은 기본 구현 내용을 한 줄로 쓴다.
- Awards와 Activities는 기본적으로 `Awards & Activities` 단일 섹션에 합친다.
- 단일 프로젝트를 bullet list 하나로만 끝내지 않는다.
- JD 맞춤본에서는 contribution block 순서를 JD의 must-have와 evaluation themes에 맞춰 재배치한다.

## Workflow

1. target folder를 `outputs/custom/YYYY-MM-DD-company-role/` 형식으로 정한다.
2. JD 원문 또는 신뢰 가능한 요약을 `source/jd.md`에 저장한다.
3. 필요하면 원본 JD를 `raw/applications/`에도 저장한다.
4. 회사/역할 조사가 필요하면 공식 출처 우선으로 `research/company.md`, `research/signals.md`를 만든다.
5. `source/brief.md`에 must-have, preferred, repeated keywords, evaluation themes, emphasis, de-emphasis, gaps를 정리한다.
6. claim ledger와 proof map을 기준으로 JD에 맞는 근거만 선택한다.
7. Resume content contract에 맞춰 `source/resume.md`를 JD-specific final-form markdown으로 작성한다.
8. 품질 gate로 과장 표현, AI식 반복 문장, unsupported claim을 제거한다.
9. 렌더링은 요청된 경우에만 `cos-render-resume` 기준으로 수행하고 shared resume template은 수정하지 않는다.
10. `log.md`에 `output` 항목을 append 한다.

## Output files

- `outputs/custom/YYYY-MM-DD-company-role/source/jd.md`
- `outputs/custom/YYYY-MM-DD-company-role/source/brief.md`
- `outputs/custom/YYYY-MM-DD-company-role/source/resume.md`
- optional `outputs/custom/YYYY-MM-DD-company-role/research/company.md`
- optional `outputs/custom/YYYY-MM-DD-company-role/research/signals.md`
- optional `outputs/custom/YYYY-MM-DD-company-role/final/resume.html`
- optional `outputs/custom/YYYY-MM-DD-company-role/final/resume.pdf`

## Quality gates

- `brief.md`가 요구사항, 강조점, 제외점, gap을 분리한다.
- `resume.md`가 JD-specific이지만 source-backed다.
- Work Experience와 Projects가 같은 content shape을 사용한다.
- 각 경력/프로젝트 항목에 2개 이상의 contribution block이 있다.
- 큰 구현 bullet 아래에 하위 detail bullet을 두고, 마지막에 `Result:` 라인으로 개선 결과를 분리한다.
- 기본 기능 구현은 과장된 문제 해결처럼 쓰지 않고 구현 상황, 구현 범위, 완성된 사용 흐름을 기준으로 쓴다.
- unsupported claim은 삭제하거나 gap으로 이동한다.
- final markdown에 placeholder가 없다.
- 공식 출처가 필요한 최신 회사 정보는 날짜와 링크를 남긴다.

## Stop conditions

- JD, 역할, 회사 context가 모두 부족하다.
- 여러 역할이 섞여 하나의 resume으로 조립할 수 없다.
- 사용자가 요구한 맞춤 포지셔닝이 evidence와 맞지 않는다.
- 외부 제출 또는 전송을 요청했지만 최종 확인이 없다.

## Log format

```md
## [YYYY-MM-DD] output | custom resume package for <company-role>

- Created or updated `outputs/custom/YYYY-MM-DD-company-role/source/`
- Added `jd.md`, `brief.md`, and `resume.md`
- Added research or rendered files if requested
```
