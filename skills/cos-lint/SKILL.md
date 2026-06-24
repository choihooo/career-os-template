---
name: cos-lint
description: Use when auditing Career OS layer boundaries, raw/wiki/output consistency, claim proof coverage, stale resume outputs, and deprecated structure references.
---

# COS Lint

## Layer Movement

All layers -> diagnostic report. Fixes only when explicitly requested.

## When to use

레포 구조, claim/proof 연결, stale output, deprecated path, 과장/근거 누락을 점검할 때 사용한다.

## Inputs

- 전체 repository tree
- `AGENTS.md`, `index.md`, `log.md`
- `raw/**`, `wiki/**`, `outputs/**`, `skills/**`

## Read first

1. `AGENTS.md`
2. `index.md`
3. `log.md`
4. `raw/README.md`
5. `wiki/README.md`
6. `outputs/README.md`

## Allowed edits

- 기본은 read-only
- 사용자가 fix를 명시하면 해당 파일
- fix 실행 시 `log.md`

## Forbidden edits

- 요청 없는 수정
- raw 원천 의미 변경
- evidence 없이 claim을 강하게 만들기
- output을 source보다 우선해 wiki를 덮어쓰기

## Workflow

1. deprecated path와 금지 산출물 참조를 검색한다.
2. raw taxonomy가 새 구조를 따르는지 확인한다.
3. wiki 페이지가 `index.md`에 연결되어 있는지 확인한다.
4. strong claim이 `wiki/claims-ledger.md`와 `wiki/proof-map.md`에 연결되는지 확인한다.
5. `outputs/general/source/resume.md`가 wiki 포지셔닝과 심하게 어긋나는지 확인한다.
6. custom package가 `source/jd.md`, `source/brief.md`, `source/resume.md` 구조를 지키는지 확인한다.
7. findings를 severity 순서로 보고한다.
8. fix 요청이 있으면 범위를 좁혀 수정하고 `log.md`에 `lint` 항목을 append 한다.

## Output files

- 기본은 없음
- fix 요청 시 명시된 파일
- fix 수행 시 `log.md`

## Quality gates

- findings는 파일 경로와 결과 영향을 포함한다.
- 과거 log나 architecture audit처럼 의도된 역사적 참조는 current-rule 위반과 구분한다.
- no finding이면 남은 blind spot을 명시한다.

## Stop conditions

- 사용자가 read-only audit만 요청했는데 수정이 필요하다.
- private source나 민감정보를 확인해야 판단 가능하다.
- 대규모 자동 수정이 raw 원문 보존 원칙을 침해할 수 있다.

## Log format

```md
## [YYYY-MM-DD] lint | fixed <scope>

- Checked layer boundaries and claim/proof coverage
- Fixed `<path>` if requested
- Left unresolved gaps if any
```
