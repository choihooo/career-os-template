---
name: cos-ingest-github-repo
description: Use when analyzing a GitHub repository, pull request, commit, or local clone into raw evidence for later wiki ingestion.
---

# COS Ingest GitHub Repo

## Layer Movement

GitHub or local repository evidence -> `raw/evidence/github/` and related raw source.

## When to use

GitHub repo, PR, commit, compare URL, or local clone에서 기여 근거를 수집해 raw evidence로 남길 때 사용한다.

## Inputs

- GitHub repository URL
- Pull request URL
- Commit or compare URL
- Local clone path
- 사용자의 GitHub username 또는 기여 범위 설명

## Read first

1. `AGENTS.md`
2. `index.md`
3. `log.md`
4. `raw/README.md`
5. 관련 기존 raw/wiki 프로젝트 파일

## Allowed edits

- `raw/evidence/github/**`
- 필요 시 `raw/projects/**`
- 필요 시 `raw/experiences/**`
- `index.md`
- `log.md`

## Forbidden edits

- `wiki/**` 직접 승격
- `outputs/**`
- 본인 기여로 확인되지 않은 repo 전체 성과를 claim으로 확정
- 외부 repo에 push, issue/comment 작성, PR 생성

## Workflow

1. 분석 범위를 owner/repo, branch, PR, commit, compare 중 하나로 고정한다.
2. README, package files, 주요 source, commit/PR metadata를 확인한다.
3. 사용자의 기여와 전체 repo 맥락을 분리한다.
4. 의미 있는 변경을 STAR/CAR 후보로 정리한다.
5. 각 후보에 proof link, 파일 경로, confidence, gap을 붙인다.
6. `raw/evidence/github/<slug>.md`에 저장한다.
7. 관련 project raw가 필요하면 요약 링크만 추가한다.
8. `index.md`와 `log.md`를 갱신한다.

## Output files

- `raw/evidence/github/<slug>.md`
- 필요 시 `raw/projects/<slug>.md`
- 필요 시 `index.md`, `log.md`

## Quality gates

- commit/PR/file evidence가 구체적이다.
- authorship과 role ownership이 분리되어 있다.
- metrics, users, business impact를 추정으로 만들지 않는다.
- 후속 wiki 반영은 `cos-ingest`로 넘긴다.

## Stop conditions

- private repo에 접근할 수 없고 local clone도 없다.
- 사용자의 GitHub identity 없이는 기여 구분이 불가능하다.
- repo 범위가 너무 넓어 목표 프로젝트를 특정할 수 없다.

## Log format

```md
## [YYYY-MM-DD] ingest | GitHub evidence for <project>

- Analyzed `<url-or-path>`
- Created `raw/evidence/github/<slug>.md`
- Captured STAR/CAR candidates, proof links, and gaps
```
