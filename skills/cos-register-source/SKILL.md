---
name: cos-register-source
description: Use when saving external career material into the raw source taxonomy before it is normalized into wiki knowledge.
---

# COS Register Source

## Layer Movement

External material -> `raw/` Source layer.

## When to use

사용자가 새 경력 자료, 링크, JD, 피드백, 스크린샷 설명, 수상/활동/프로젝트 메모를 제공했고 아직 wiki로 정규화하지 않을 때 사용한다.

## Inputs

- 붙여넣은 원문 메모
- 외부 링크 또는 파일 설명
- JD 원문
- GitHub 외 증빙 메모
- 분류가 애매한 임시 자료

## Read first

1. `AGENTS.md`
2. `index.md`
3. `log.md`
4. `raw/README.md`
5. 관련 기존 `raw/**` 파일

## Allowed edits

- `raw/profile/**`
- `raw/experiences/**`
- `raw/projects/**`
- `raw/activities/**`
- `raw/awards/**`
- `raw/applications/**`
- `raw/evidence/**`
- `raw/inbox/**`
- `index.md`
- `log.md`

## Forbidden edits

- `wiki/**` 정규화 지식 생성
- `outputs/**` 제출 산출물 생성
- `templates/**`
- `docs/**`
- 외부 제출, 전송, 업로드

## Workflow

1. 자료의 primary type을 정한다.
2. 애매하면 `raw/inbox/`에 저장하고 분류 질문을 남긴다.
3. raw markdown 파일에 frontmatter를 붙인다.
4. 원문 표현, 출처, 날짜, 링크, 증빙 강도를 보존한다.
5. 같은 사실을 여러 raw 파일에 복붙하지 말고 related ID로 연결한다.
6. 중요한 source면 `index.md`에 추가한다.
7. `log.md`에 `ingest` 또는 `setup` 항목을 append 한다.

## Output files

- `raw/<taxonomy>/<slug>.md`
- 필요 시 `index.md`
- 필요 시 `log.md`

## Quality gates

- raw 파일이 source 원문과 해석을 구분한다.
- `type`, `id`, `status`, `evidence_strength`가 있다.
- 근거가 약한 내용은 `needs-proof` 또는 `low`로 표시한다.
- 이력서용 claim으로 단정하지 않는다.

## Stop conditions

- 자료의 소유자나 공개 가능 여부가 불명확하다.
- 민감정보가 포함되어 저장 위치를 결정할 수 없다.
- 하나의 파일에 섞으면 안 되는 여러 대상 회사/JD가 섞여 있다.

## Log format

```md
## [YYYY-MM-DD] ingest | registered source for <topic>

- Added `raw/<taxonomy>/<slug>.md`
- Preserved source, evidence strength, and gaps
- Updated `index.md` if needed
```
