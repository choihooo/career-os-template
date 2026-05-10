# Career Wiki Agent Guide

## Purpose

이 저장소는 채용 지원용 커리어 위키다. 원천 자료를 구조화된 경력 지식으로 정리하고, 그 지식을 바탕으로 범용 이력서/포트폴리오와 회사별 맞춤 지원 패키지를 생성한다.

## Layers

### raw/

- 원천 자료 저장소다.
- 수상경력, 자기소개 조각, 경력 사실, 프로젝트 링크와 소개, 성과 메모를 저장한다.
- 사실 원형을 보존하고 덮어쓰기보다 추가를 우선한다.

### wiki/

- LLM이 유지하는 정규화 지식 계층이다.
- 경험, 프로젝트, 수상, 기술, 스토리, 강점, 문장 뱅크를 관리한다.
- 직접 제출하지 않는 중간 컴파일 결과물이다.

### outputs/

- 제출 가능한 문서를 저장한다.
- 범용본은 `outputs/general/`에 보관한다.
- 회사별 맞춤본은 `outputs/custom/YYYY-MM-DD-company/`에 보관한다.

## Standard Output Files

### General

- `outputs/general/resume-general-v1.md`
- `outputs/general/resume-general-v2.md`
- `outputs/general/portfolio-general-v1.md`
- `outputs/general/portfolio-general-v2.md`

### Company-specific package

Each company folder must contain:

- `jd.md`
- `analysis.md`
- `strategy.md`
- `resume.md`
- `portfolio.md`

Optional research files:

- `company-research.md`
- `culture-signals.md`
- `interview-signals.md`
- `fit-hypotheses.md`

## Workflows

### Ingest

1. 새 자료를 `raw/`의 적절한 위치에 저장한다.
2. 관련 `wiki/` 페이지가 있는지 먼저 확인한다.
3. 핵심 사실, 수치, 재사용 가능한 문장을 추출한다.
4. 관련 `wiki/` 페이지와 `wiki/sentence-bank/`, `wiki/stories/`를 업데이트한다.
5. `index.md`를 갱신한다.
6. `log.md`에 ingest 항목을 append 한다.

### Build General Outputs

1. `wiki/themes/`, `wiki/stories/`, `wiki/sentence-bank/`를 우선 읽는다.
2. 전달하려는 포지셔닝에 맞게 문장을 선택한다.
3. 해당 범용 산출물 파일을 갱신한다.
4. 최종 저장 전에 `career-output-polish` 기준으로 AI식 문장 패턴을 교정한다.
5. `log.md`에 변경 이유를 기록한다.

### Build Company-Specific Outputs

1. `outputs/custom/YYYY-MM-DD-company/` 디렉터리를 만든다.
2. `jd.md`에 JD 원문 또는 요약을 저장한다.
3. `analysis.md`에 요구사항과 키워드를 정리한다.
4. `strategy.md`에 강조 포인트와 제외 포인트를 정리한다.
5. `resume.md`와 `portfolio.md`를 생성한다.
6. 최종 저장 전에 `career-output-polish` 기준으로 AI식 문장 패턴을 교정한다.
7. 새롭게 정리된 강점이나 문장은 `wiki/`에 역반영한다.
8. `log.md`에 output 항목을 append 한다.

### Query

- 질문에 답하기 전에 `index.md`를 먼저 읽는다.
- 관련 `wiki/` 페이지를 읽고 합성한다.
- 가치 있는 분석 결과는 새 위키 페이지나 산출물로 저장할 수 있다.

### Lint

- 고아 페이지를 찾는다.
- 중복된 프로젝트 설명을 찾는다.
- 상충되는 수치나 사실을 찾는다.
- 반복적으로 쓰이는 강점인데 독립 페이지가 없는 경우를 찾는다.
- 원천 자료 대비 업데이트가 누락된 페이지를 찾는다.

## Writing Rules

- 기본 언어는 한국어다.
- 사실과 해석을 섞지 않는다.
- 같은 내용을 여러 산출물에 직접 복붙하지 않는다. 먼저 `wiki/`를 갱신하고 산출물을 다시 만든다.
- 회사명은 가능하면 ASCII 소문자 slug를 사용한다.
- 맞춤본은 반드시 디렉터리 단위로 관리한다.

## Index and Log

### index.md

- 위키의 주요 페이지를 분류별 링크와 한 줄 설명으로 정리한다.
- 새 페이지를 만들거나 중요한 구조 변경이 있으면 함께 갱신한다.

### log.md

- append-only 파일로 유지한다.
- 각 항목은 아래 형식을 따른다.

```md
## [2026-05-10] ingest | 프로젝트 foo 소개 추가
## [2026-05-10] output | 2026-05-10-openai 맞춤 이력서 생성
## [2026-05-10] lint | stories 고아 페이지 점검
```
