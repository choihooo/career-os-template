---
name: cos-build-resume
description: Use when building or refreshing the general resume markdown from the current wiki knowledge.
---

# COS Build Resume

## Layer Movement

`wiki/` Knowledge layer -> `outputs/general/source/resume.md`.

## When to use

범용 이력서 markdown을 현재 wiki 기준으로 갱신할 때 사용한다.

## Inputs

- `wiki/overview/career-overview.md`
- `wiki/themes/positioning.md`
- `wiki/claims-ledger.md`
- `wiki/proof-map.md`
- `wiki/sentence-bank/resume-bullets.md`
- 관련 wiki 경험/프로젝트/활동/수상/기술 페이지

## Read first

1. `AGENTS.md`
2. `index.md`
3. `log.md`
4. `outputs/README.md`
5. `wiki/README.md`
6. `wiki/overview/career-overview.md`
7. `wiki/themes/positioning.md`
8. `wiki/output-briefs/general-resume-brief.md`
9. `wiki/claims-ledger.md`
10. `wiki/proof-map.md`
11. `wiki/sentence-bank/resume-bullets.md`
12. 관련 wiki pages

## Allowed edits

- `outputs/general/source/resume.md`
- 명시 요청이 있을 때 `outputs/general/final/resume.html`
- 명시 요청이 있을 때 `outputs/general/final/resume.pdf`
- 명확한 backfill이 필요할 때 관련 `wiki/**`
- `log.md`

## Forbidden edits

- `raw/**` 원천 변경
- 회사별 `outputs/custom/**`
- `templates/resume/**`
- 포트폴리오 파일 생성
- 근거 없는 수치, 역할, 성과 추가

## Resume content contract

`outputs/general/source/resume.md` must be shaped for the shared resume template.

- 기본 섹션은 `About Me`, `Work Experience`, `Projects`, `Awards & Activities`만 사용한다.
- `Skills`, `Education`, 또는 다른 새 섹션이 필요하면 shared template-design change로 분리한다.
- Work Experience와 Projects는 같은 content shape을 사용한다.
- 각 Work Experience item은 회사/역할명, 1문장 소개, 2개 이상의 contribution block을 가진다.
- 각 Project item은 프로젝트명, 1문장 소개, 2개 이상의 contribution block을 가진다.
- 각 contribution block은 제목, 태그 3-5개, 환경/문제/필요성이 드러나는 1-2줄 요약, 큰 구현 bullet, 하위 구현 detail bullet, Result line으로 작성한다.
- 요약은 구현 방법을 반복하지 않고 어떤 업무/서비스 환경에서 어떤 문제가 실제로 있었고 왜 재발 방지나 개선이 필요했는지 설명한다. 필요하면 두 줄까지 허용한다.
- Awards와 Activities는 기본적으로 `Awards & Activities` 단일 섹션에 합친다.
- 단일 프로젝트를 bullet list 하나로만 끝내지 않는다.

## Workflow

1. 범용 이력서의 목표 역할과 우선순위를 정한다.
2. claim ledger에서 resume 사용이 허용된 claim만 고른다.
3. proof map으로 강한 claim의 근거를 확인한다.
4. section order와 bullet 밀도를 `general-resume-brief.md` 기준으로 정한다.
5. Resume content contract에 맞춰 `outputs/general/source/resume.md`를 final-form markdown으로 작성한다.
6. 품질 gate로 과장 표현, AI식 반복 문장, feature-only bullet을 줄인다.
7. 새로 발견한 reusable phrasing은 필요한 경우 wiki에 backfill한다.
8. 렌더링은 요청된 경우에만 `cos-render-resume` 기준으로 수행하고 shared resume template은 수정하지 않는다.
9. `log.md`에 `output` 항목을 append 한다.

## Output files

- `outputs/general/source/resume.md`
- 필요 시 `outputs/general/final/resume.html`
- 필요 시 `outputs/general/final/resume.pdf`
- 필요 시 `log.md`

## Quality gates

- 모든 강한 claim이 `wiki/claims-ledger.md` 또는 명확한 wiki/source 근거와 연결된다.
- 이력서는 개조식, compact, recruiter-friendly 형태다.
- Work Experience와 Projects가 같은 content shape을 사용한다.
- 각 경력/프로젝트 항목에 2개 이상의 contribution block이 있다.
- feature list가 아니라 context/problem/implementation-detail/result 흐름의 contribution block을 우선한다.
- 큰 구현 bullet 아래에 하위 detail bullet을 두고, 마지막에 `Result:` 라인으로 개선 결과를 분리한다.
- 수치가 없으면 관찰 가능한 개선만 쓴다.
- 빈 placeholder가 없다.

## Stop conditions

- wiki에 credible general resume을 만들 근거가 부족하다.
- 핵심 역할, 기간, 성과가 서로 충돌한다.
- 사용자가 요구한 포지셔닝이 현재 evidence로 뒷받침되지 않는다.

## Log format

```md
## [YYYY-MM-DD] output | updated general resume

- Updated `outputs/general/source/resume.md`
- Used claim/proof checks
- Rendered final resume only if requested
```
