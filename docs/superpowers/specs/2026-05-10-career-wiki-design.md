# Career Wiki Design

## Goal

채용 지원을 위한 커리어 위키를 구축한다. 이 위키는 수상경력, 자기소개 조각, 프로젝트 소개, 경력 사실, 링크 등 원천 자료를 구조화된 지식으로 정리하고, 이를 바탕으로 범용 이력서/포트폴리오와 회사별 맞춤 지원 패키지를 빠르게 생성하고 유지하는 것을 목표로 한다.

## Non-Goals

- 퍼블릭 블로그나 대외 공개용 사이트를 직접 운영하는 시스템으로 확장하지 않는다.
- 원천 자료를 자동으로 완벽하게 정규화하는 복잡한 파이프라인부터 만들지 않는다.
- 초기 버전에서 외부 검색 엔진, 벡터 DB, RAG 인프라를 도입하지 않는다.

## User Intent

사용자는 커리어 관련 원천 자료를 축적하고, 이를 기반으로 다음 산출물을 관리하고자 한다.

- 범용 이력서: `v1`, `v2`
- 범용 포트폴리오: `v1`, `v2`
- 특정 회사 맞춤 지원 패키지: `날짜-회사` 단위
- 회사별 패키지에 포함되는 작업물: JD 분석, 강조 포인트, 제외 포인트, 맞춤 전략 메모, 최종 이력서, 최종 포트폴리오

기본 운영 언어는 한국어이며, 영어 산출물은 필요 시 파생 생성한다.

## Architecture

위키는 세 개의 계층으로 구성한다.

### 1. Raw Sources

`raw/`는 원천 자료 계층이다. 사실과 증거를 보관하며, LLM이 참조하지만 의미를 재정리하는 주된 공간은 아니다.

이 계층에 들어갈 수 있는 자료:

- 수상경력 기록
- 자기소개 문장 조각
- 프로젝트 링크와 소개
- 경력 요약 메모
- 성과 지표와 근거
- 제출용 문서의 초안 조각

원칙:

- 가능한 한 사실 원형에 가깝게 유지한다.
- 중복 정리보다 보존을 우선한다.
- 수정이 필요하면 원본을 덮어쓰기보다 새 자료를 추가한다.

### 2. Compiled Wiki

`wiki/`는 LLM이 유지하는 정규화 계층이다. 원천 자료를 바탕으로 재사용 가능한 경력 지식 페이지를 관리한다.

주요 페이지 유형:

- 경험 페이지: 회사, 역할, 기간, 책임, 성과
- 프로젝트 페이지: 문제, 기여, 기술 선택, 결과, 수치, 링크
- 수상/활동 페이지: 맥락, 의미, 증거, 활용 포인트
- 기술 페이지: 숙련도, 사용 맥락, 대표 사례
- 스토리 페이지: STAR/CAR 기반 에피소드, 리더십, 문제 해결, 협업, 임팩트
- 문장 뱅크: 이력서 bullet, 자기소개 문장, 포트폴리오 설명 문안
- 테마 페이지: 강점, 포지셔닝, 커리어 내러티브, 일관된 메시지

이 계층은 직접 제출하지 않고, 산출물을 만들기 위한 중간 컴파일 결과물로 본다.

### 3. Outputs

`outputs/`는 제출 가능한 문서를 저장하는 계층이다.

구성:

- 범용본
  - `outputs/general/resume-general-v1.md`
  - `outputs/general/resume-general-v2.md`
  - `outputs/general/portfolio-general-v1.md`
  - `outputs/general/portfolio-general-v2.md`
- 맞춤본
  - `outputs/custom/YYYY-MM-DD-company/`

회사별 폴더에는 다음 파일을 둔다.

- `jd.md`: JD 원문 또는 요약
- `analysis.md`: JD 분석
- `strategy.md`: 강조 포인트, 제외 포인트, 포지셔닝 메모
- `resume.md`: 맞춤 이력서
- `portfolio.md`: 맞춤 포트폴리오

## Directory Structure

```text
carrer-wiki/
├── AGENTS.md
├── index.md
├── log.md
├── raw/
│   ├── awards/
│   ├── bios/
│   ├── experiences/
│   ├── projects/
│   └── links/
├── wiki/
│   ├── overview/
│   ├── experiences/
│   ├── projects/
│   ├── awards/
│   ├── skills/
│   ├── stories/
│   ├── themes/
│   └── sentence-bank/
├── outputs/
│   ├── general/
│   └── custom/
└── docs/
    └── superpowers/
        └── specs/
```

## Naming Conventions

### Raw Sources

- 한국어 파일명 사용 가능
- 필요하면 접두사로 날짜 추가: `2026-05-10-프로젝트-a.md`
- 링크 기록은 원문 출처가 드러나도록 저장

### Wiki Pages

- 페이지별 역할이 드러나는 슬러그 사용
- 예시:
  - `wiki/projects/project-foo.md`
  - `wiki/stories/story-launch-recovery.md`
  - `wiki/themes/positioning-product-engineer.md`

### Outputs

- 범용본은 고정 이름과 버전 유지
- 맞춤본은 `YYYY-MM-DD-company` 디렉터리 사용
- 회사명은 나중에 쉘/스크립트에서 다루기 쉽도록 ASCII 소문자 slug를 권장

## Primary Workflows

### Ingest

새 원천 자료가 들어오면 다음 순서로 처리한다.

1. `raw/` 적절한 하위 폴더에 저장
2. 핵심 사실, 수치, 증거, 재사용 가능한 문장을 추출
3. 관련 `wiki/` 페이지 생성 또는 업데이트
4. 필요하면 `sentence-bank`와 `stories` 업데이트
5. `index.md` 갱신
6. `log.md`에 ingest 기록 추가

### Build General Outputs

범용 이력서/포트폴리오를 갱신할 때:

1. `wiki/themes`, `wiki/stories`, `wiki/sentence-bank` 우선 검토
2. 전달하려는 포지셔닝을 기준으로 문장을 선택
3. `outputs/general/`의 해당 버전 파일 갱신
4. 갱신 이유를 `log.md`에 기록

### Build Company-Specific Package

특정 회사 대응 시:

1. `outputs/custom/YYYY-MM-DD-company/` 생성
2. JD 원문 또는 요약을 `jd.md`에 저장
3. `analysis.md`에서 핵심 요구사항, 우선순위, 키워드 추출
4. `strategy.md`에서 강조 포인트와 제외 포인트를 정리
5. 범용 산출물과 `wiki/` 페이지를 기반으로 `resume.md`, `portfolio.md` 생성
6. 회사 맞춤 과정에서 발견한 새로운 강점/문장이 있으면 `wiki/`에 역반영
7. `log.md`에 작업 기록 추가

### Query

질문 응답은 우선 `index.md`를 보고 관련 페이지를 찾은 뒤 `wiki/`를 읽고 합성한다. 가치 있는 분석 결과는 새 페이지나 산출물로 저장할 수 있다.

### Lint

정기 점검 시 다음을 확인한다.

- 고아 페이지
- 중복된 프로젝트 설명
- 상충되는 수치/사실
- JD 대응에서 반복적으로 쓰이는데 별도 페이지가 없는 강점
- 업데이트된 원천 자료가 있는데 반영되지 않은 스토리/문장

## AGENTS.md Responsibilities

`AGENTS.md`는 이 저장소에서 LLM이 따라야 할 운영 규칙을 정의한다.

포함되어야 할 내용:

- 위키의 계층 구조와 각 계층의 책임
- ingest, query, lint, output generation 절차
- 파일명 규칙
- 사실과 해석을 섞지 않는 원칙
- 회사별 맞춤본 생성 시 필수 파일
- `index.md`, `log.md` 유지 규칙

## Indexing and Logging

### index.md

위키의 모든 주요 페이지를 분류별로 링크와 한 줄 설명과 함께 정리한다. 초기에는 사람이 보기 쉬운 카탈로그 역할과 LLM의 탐색 시작점 역할을 동시에 맡긴다.

### log.md

append-only 로그로 유지한다. 각 항목은 아래 형식을 권장한다.

```md
## [2026-05-10] ingest | 프로젝트 foo 소개 추가
## [2026-05-10] output | 2026-05-10-openai 맞춤 이력서 생성
## [2026-05-10] lint | stories 고아 페이지 점검
```

## Design Principles

- 원천 자료는 증거 저장소로 본다.
- 위키는 재사용 가능한 경력 지식 계층으로 본다.
- 산출물은 제출 목적에 맞게 조립된 최종 문서로 본다.
- 같은 내용을 여러 산출물에 직접 복붙하지 않고 위키를 갱신한 뒤 재생성한다.
- 기본 언어는 한국어로 통일한다.
- 복잡한 검색 인프라는 늦게 도입한다. 초기에는 `index.md` 중심 탐색으로 충분하다.

## Risks and Mitigations

### Risk: 자료가 산발적으로 쌓여 중복이 늘어남

Mitigation:

- ingest 시 항상 기존 `wiki/` 페이지를 먼저 확인한다.
- 프로젝트/스토리/문장 뱅크를 분리해 중복 역할을 줄인다.

### Risk: 회사별 맞춤본이 많아지면서 관리가 어려워짐

Mitigation:

- 회사별 작업은 반드시 디렉터리 단위로 묶는다.
- 산출물만 저장하지 않고 분석과 전략을 함께 저장한다.

### Risk: 사실과 해석이 뒤섞여 신뢰도가 떨어짐

Mitigation:

- `raw/`는 원천 자료, `wiki/`는 해석, `outputs/`는 표현물이라는 경계를 유지한다.
- 수치와 근거는 가능하면 `wiki/`에서 원천 자료 링크와 연결한다.

## Success Criteria

- 원천 자료를 넣으면 관련 경력 지식 페이지가 누적적으로 풍부해진다.
- 범용 이력서/포트폴리오 `v1`, `v2`를 안정적으로 유지할 수 있다.
- 특정 회사 대응 시 `YYYY-MM-DD-company` 단위의 패키지를 일관된 구조로 생성할 수 있다.
- 같은 프로젝트/성과를 여러 문서에서 수작업으로 반복 편집하는 양이 줄어든다.

## Next Step

이 설계를 바탕으로 다음 단계에서는 구현 계획을 작성한다. 구현 범위는 초기 스캐폴딩, `AGENTS.md` 초안, `index.md`/`log.md` 템플릿, 핵심 디렉터리 생성까지를 우선 대상으로 삼는다.
