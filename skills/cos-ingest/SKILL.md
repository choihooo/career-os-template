---
name: cos-ingest
description: Use when promoting raw source material into normalized wiki knowledge, claims, proofs, stories, and reusable resume bullets.
---

# COS Ingest

## Layer Movement

`raw/` Source layer -> `wiki/` Knowledge layer.

## When to use

등록된 raw 자료를 이력서와 면접에 재사용 가능한 지식으로 승격할 때 사용한다.

## Inputs

- `raw/**` source 파일
- 관련 기존 wiki 페이지
- 사용자가 확인한 역할, 기간, 성과, 증빙

## Read first

1. `AGENTS.md`
2. `index.md`
3. `log.md`
4. `raw/README.md`
5. `wiki/README.md`
6. 대상 raw 파일
7. 관련 `wiki/**` 파일
8. `wiki/claims-ledger.md`
9. `wiki/proof-map.md`

## Allowed edits

- `wiki/overview/**`
- `wiki/themes/**`
- `wiki/projects/**`
- `wiki/experiences/**`
- `wiki/activities/**`
- `wiki/awards/**`
- `wiki/skills/**`
- `wiki/stories/**`
- `wiki/sentence-bank/**`
- `wiki/claims-ledger.md`
- `wiki/proof-map.md`
- raw frontmatter의 `status`, `related`, `updated_at`
- `index.md`
- `log.md`

## Forbidden edits

- `outputs/**` 산출물 생성
- `templates/**`
- `docs/**`
- raw 원문을 의미가 바뀌게 덮어쓰기
- 근거 없는 claim 확정

## Workflow

1. 대상 raw source의 type, id, evidence strength를 확인한다.
2. 같은 경험/프로젝트/활동/수상이 이미 wiki에 있는지 확인한다.
3. 사실, 해석, gap을 분리한다.
4. 관련 wiki 페이지를 생성하거나 업데이트한다.
5. 이력서에 쓸 수 있는 문장은 `wiki/sentence-bank/resume-bullets.md`에 후보로 추가한다.
6. 면접 답변으로 쓸 수 있는 단위는 `wiki/stories/story-bank.md`에 추가한다.
7. 강한 주장은 `wiki/claims-ledger.md`에 claim으로 등록하고 `wiki/proof-map.md`의 proof와 연결한다.
8. 새 파일이나 중요한 변경은 `index.md`에 반영한다.
9. `log.md`에 `ingest` 항목을 append 한다.

## Output files

- 관련 `wiki/**` 페이지
- `wiki/claims-ledger.md`
- `wiki/proof-map.md`
- `wiki/sentence-bank/resume-bullets.md`
- `wiki/stories/story-bank.md`
- 필요 시 `index.md`, `log.md`

## Quality gates

- claim마다 source/proof 연결이 있다.
- 수치, 기간, 역할은 raw source와 충돌하지 않는다.
- 확신이 낮은 내용은 caveat 또는 gap으로 남긴다.
- 기존 wiki와 중복 페이지를 만들지 않는다.

## Stop conditions

- raw source가 기존 wiki와 핵심 사실에서 충돌한다.
- 사용자의 역할과 전체 프로젝트 성과를 구분할 수 없다.
- 지표가 출처 없이 강한 claim으로 쓰이고 있다.

## Log format

```md
## [YYYY-MM-DD] ingest | promoted source to wiki for <topic>

- Read `raw/<taxonomy>/<slug>.md`
- Updated `wiki/...`
- Updated claims/proofs/stories/bullets as applicable
```
