# Career Wiki

채용 지원용 커리어 위키 저장소다. 원천 자료를 쌓고, 그것을 재사용 가능한 경력 지식으로 정리한 뒤, 범용 이력서/포트폴리오와 회사별 맞춤 지원 패키지를 만드는 흐름을 전제로 한다.

## Core Idea

이 저장소는 문서를 보관하는 폴더가 아니라, 지원 문서를 조립하기 위한 컴파일러에 가깝다.

- `raw/`: 사실과 증거를 보관하는 원천 자료 계층
- `wiki/`: LLM이 관리하는 정규화 지식 계층
- `outputs/`: 실제 제출 가능한 산출물 계층

원칙은 단순하다.

- raw는 가능한 한 원형을 보존한다.
- wiki는 재사용 가능한 지식으로 정리한다.
- outputs는 특정 목적에 맞는 최종 문서만 둔다.

## Repository Structure

```text
carrer-wiki/
├── AGENTS.md
├── README.md
├── index.md
├── log.md
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
│   ├── projects/
│   ├── sentence-bank/
│   ├── skills/
│   ├── stories/
│   └── themes/
├── outputs/
│   ├── custom/
│   └── general/
└── skills/
    ├── career-build-custom-package/
    ├── career-build-general/
    ├── career-company-research/
    ├── career-ingest/
    ├── career-lint/
    └── career-output-polish/
```

## Main Files

- [`AGENTS.md`](AGENTS.md): 이 저장소에서 LLM이 따라야 할 운영 규칙
- [`index.md`](index.md): 위키 카탈로그
- [`log.md`](log.md): append-only 작업 로그
- [`wiki/overview/career-overview.md`](wiki/overview/career-overview.md): 현재 커리어 포지셔닝과 우선 ingest 대상
- [`wiki/themes/positioning.md`](wiki/themes/positioning.md): 목표 역할과 강점 정리
- [`wiki/stories/story-bank.md`](wiki/stories/story-bank.md): STAR 스토리 모음
- [`wiki/sentence-bank/resume-bullets.md`](wiki/sentence-bank/resume-bullets.md): 재사용 가능한 이력서 bullet

## Output Layout

### General

범용 산출물은 `outputs/general/` 아래에 둔다.

- `resume-general-v1.md`
- `resume-general-v2.md`
- `portfolio-general-v1.md`
- `portfolio-general-v2.md`

### Custom

회사별 맞춤 산출물은 `outputs/custom/YYYY-MM-DD-company/` 아래에 둔다.

기본 파일:

- `jd.md`
- `analysis.md`
- `strategy.md`
- `resume.md`
- `portfolio.md`

조사 자료가 있으면 함께 둔다.

- `company-research.md`
- `culture-signals.md`
- `interview-signals.md`
- `fit-hypotheses.md`

## Workflow

### 1. Ingest raw sources

입력 예시:

- 수상경력
- 자기소개 문장 조각
- 프로젝트 링크와 소개
- 경력 사실
- 성과 수치와 근거

사용 스킬:

- `career-ingest`

수행 내용:

1. 새 자료를 `raw/`에 저장
2. 관련 `wiki/` 페이지 확인
3. 사실, 역할, 수치, 증거 추출
4. 관련 `wiki/` 페이지 갱신
5. 필요하면 `story-bank`와 `resume-bullets` 갱신
6. `index.md`, `log.md` 갱신

### 2. Build the reusable wiki

이 단계는 별도 최종 문서를 만들기보다 위키 자체를 키우는 단계다.

주요 목적:

- 프로젝트 설명을 재사용 가능하게 정리
- 경력 포지셔닝 명확화
- STAR 에피소드 축적
- 이력서 bullet 문장 축적

핵심 파일:

- `wiki/overview/`
- `wiki/themes/`
- `wiki/stories/`
- `wiki/sentence-bank/`

### 3. Build general resume and portfolio

범용본이 필요하면:

- `career-build-general`

읽는 순서:

1. `career-overview.md`
2. `positioning.md`
3. `story-bank.md`
4. `resume-bullets.md`
5. 관련 프로젝트/경험 페이지

산출:

- `outputs/general/resume-general-v1.md`
- `outputs/general/resume-general-v2.md`
- `outputs/general/portfolio-general-v1.md`
- `outputs/general/portfolio-general-v2.md`

### 4. Research a target company

JD 링크나 회사명을 주면:

- `career-company-research`

수행 내용:

1. `outputs/custom/YYYY-MM-DD-company/` 생성
2. JD 저장 또는 요약
3. 공식 자료 우선으로 회사 조사
4. 신년사, 인재상, 리더 메시지, 문화 신호 정리
5. 후기류는 보조 신호로만 분리 기록

산출:

- `jd.md`
- `company-research.md`
- `culture-signals.md`
- `interview-signals.md`
- `fit-hypotheses.md`

### 5. Build a custom package

회사별 맞춤 지원 문서가 필요하면:

- `career-build-custom-package`

수행 내용:

1. `jd.md` 기반 요구사항 정리
2. `analysis.md` 작성
3. `strategy.md` 작성
4. `resume.md` 작성
5. `portfolio.md` 작성
6. 좋은 문장이나 framing이 생기면 다시 `wiki/`에 역반영

### 6. Polish final outputs

최종 제출 전에는 항상:

- `career-output-polish`

이 스킬은 아래 reference를 읽고 AI식 문장 패턴을 줄인다.

- [`skills/career-output-polish/references/ai-writing-tropes.md`](skills/career-output-polish/references/ai-writing-tropes.md)

교정 대상:

- `outputs/general/*.md`
- `outputs/custom/*/resume.md`
- `outputs/custom/*/portfolio.md`

목표:

- 과장된 표현 줄이기
- 반복 리듬 줄이기
- 블로그 같은 톤 제거
- 더 사람 같은 문장으로 정리

### 7. Lint the wiki

정기 점검이 필요하면:

- `career-lint`

기본 점검 항목:

- `index.md`에 안 걸린 고아 페이지
- 중복 프로젝트 설명
- 상충되는 수치나 사실
- raw에는 있는데 sentence bank나 story bank에는 없는 강한 성과
- 현재 포지셔닝과 어긋나는 오래된 산출물

## Recommended End-to-End Order

가장 일반적인 흐름은 아래 순서다.

1. 원천 자료 받기
2. `career-ingest`
3. 필요하면 범용본 갱신: `career-build-general`
4. JD 링크 받기
5. 회사 조사: `career-company-research`
6. 회사별 패키지 생성: `career-build-custom-package`
7. 최종 문장 교정: `career-output-polish`
8. 주기 점검: `career-lint`

## Quick Prompts

이 저장소를 쓸 때 사용자 요청은 대략 이렇게 들어오면 된다.

### Ingest

```text
이 프로젝트 소개랑 링크 raw에 넣고 ingest 해줘.
```

### Build general resume

```text
지금 위키 기준으로 범용 이력서 v1, v2 업데이트해줘.
```

### Company research

```text
이 JD 링크 기준으로 회사 조사해줘. 신년사, 인재상, 인터뷰 신호까지 정리해줘.
```

### Custom package

```text
이 회사용으로 맞춤 이력서랑 포폴 패키지 만들어줘.
```

### Lint

```text
지금 위키 lint 돌려서 문제점만 먼저 정리해줘.
```

## Notes

- 기본 운영 언어는 한국어다.
- 회사별 폴더 이름은 가능하면 ASCII 소문자 slug를 쓴다.
- raw와 wiki와 outputs를 직접 섞지 않는다.
- 같은 내용을 여러 산출물에 직접 반복 수정하지 말고, 먼저 wiki를 갱신한 뒤 재생성하는 쪽을 우선한다.
