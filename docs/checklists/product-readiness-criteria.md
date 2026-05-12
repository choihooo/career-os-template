# Product Readiness Criteria

이 문서는 커리어 위키가 개인 사용, 내부 베타, 외부 배포 단계에서 어느 정도 준비됐는지 판단하는 기준이다. 점수는 느낌이 아니라 아래 조건을 통과한 정도로만 말한다.

## Readiness Levels

### 개인 사용 100%

혼자 반복해서 사용할 수 있는 상태다. 새 경험을 넣고, 범용 산출물을 만들고, 실제 JD에 맞춘 패키지를 생성할 수 있어야 한다.

필수 조건:

- 주요 경험이 `raw/`에 원천 자료로 저장되어 있다.
- 주요 경험이 `wiki/experiences/`, `wiki/projects/`, `wiki/awards/`, `wiki/skills/`에 정규화되어 있다.
- `wiki/overview/career-overview.md`와 `wiki/themes/positioning.md`에 목표 역할, 강점, 피해야 할 주장이 정리되어 있다.
- `wiki/sentence-bank/resume-bullets.md`에 실전 bullet이 20개 이상 있다.
- `wiki/stories/story-bank.md`에 STAR 스토리가 5개 이상 있다.
- `outputs/general/resume-general-v1.md`, `resume-general-v2.md`, `portfolio-general-v1.md`, `portfolio-general-v2.md`가 placeholder 없이 완성되어 있다.
- 실제 회사 JD 2개 이상으로 custom package를 생성해봤고, 결과가 서로 다르게 맞춤화된다.
- 생성된 custom package가 `jd.md`, `analysis.md`, `strategy.md`, `resume.md`, `portfolio.md`를 모두 포함한다.
- 근거가 부족한 수치나 역할은 생성하지 않고 `Gaps` 또는 `analysis.md`에 남긴다.

100%가 아닌 경우:

- 범용 산출물이 비어 있거나 placeholder가 남아 있다.
- HTML 산출물을 봐야만 이력서/포트폴리오를 만들 수 있다.
- JD를 넣어도 모든 회사에 비슷한 문서가 나온다.
- 강한 주장이 source page로 역추적되지 않는다.

### 내부 베타 100%

다른 사람이 README와 examples만 보고 직접 써볼 수 있는 상태다. 운영자가 옆에서 설명하지 않아도 입력, 생성, 검수 흐름이 닫혀 있어야 한다.

필수 조건:

- `README.md` 첫 화면에서 제품 목적과 사용 흐름을 이해할 수 있다.
- `examples/`에 프로젝트, 경력, 수상, JD, 요청 프롬프트 예시가 있다.
- `docs/checklists/`에 개인 준비도, 베타 준비도, custom output 품질 기준이 있다.
- `outputs/custom/` 아래에 샘플 custom package가 있다.
- markdown 산출물, HTML 템플릿, PDF export의 역할 차이가 설명되어 있다.
- 실패 조건이 설명되어 있다.
  - JD가 너무 짧은 경우
  - 링크 접근이 안 되는 경우
  - 근거가 부족한 수치가 있는 경우
  - 사용자의 역할 범위가 불명확한 경우
- 최소 1명의 베타 사용자가 README만 보고 새 경험 입력과 custom package 생성을 시도했다.
- 베타 사용자가 막힌 지점이 README, examples, checklist 중 하나에 반영됐다.

100%가 아닌 경우:

- 사용자가 어떤 형식으로 경험을 입력해야 하는지 모른다.
- 결과물이 어디에 생기는지 헷갈린다.
- 실패했을 때 무엇이 부족한지 알 수 없다.
- 샘플 결과물이 없어 기대 품질을 알 수 없다.

### 외부 배포 100%

저장소를 모르는 사용자도 안정적으로 사용할 수 있는 제품 상태다. 내부 베타보다 훨씬 높은 재현성과 안내가 필요하다.

필수 조건:

- 온보딩 문서가 초보자 기준으로 검증되어 있다.
- 예시 입력에서 예시 결과까지 재현 가능한 end-to-end walkthrough가 있다.
- 3명 이상이 각자 다른 경력/JD로 사용해봤고, 실패 사례가 문서에 반영됐다.
- JD 링크 접근 실패, 빈 입력, 모호한 경력, 상충 수치 등 예외 케이스 처리 기준이 문서화되어 있다.
- 개인정보와 민감 정보 처리 원칙이 있다.
- 산출물 export 방식이 명확하다.
- 버전 관리와 변경 로그가 사용자가 이해할 수 있는 수준으로 정리되어 있다.

현재 저장소는 외부 배포 100%를 목표로 하지 않는다. 우선순위는 개인 사용 100%와 내부 베타 100%다.

## Scoring Guide

점수는 아래 방식으로 말한다.

| Level | Meaning |
|---|---|
| 0-30% | 구조나 아이디어만 있고 반복 사용은 어렵다. |
| 31-60% | 일부 흐름은 가능하지만 입력, 생성, 검수 중 하나가 끊긴다. |
| 61-80% | 개인 사용은 가능하나 예외 처리와 온보딩이 부족하다. |
| 81-95% | 대부분의 흐름이 닫혀 있고 실제 검증만 남았다. |
| 96-100% | 실제 JD 또는 사용자 테스트를 통과했고, 실패 조건까지 문서화되어 있다. |

## Current Gate Status

### 개인 사용

현재 상태: 90-95%

통과한 항목:

- HTML 산출물의 주요 경험을 `raw/`와 `wiki/`로 역반영했다.
- 포지셔닝, bullet bank, story bank가 있다.
- 범용 산출물 4개가 placeholder 없이 작성되어 있다.
- 샘플 custom package가 있다.

남은 gate:

- 실제 회사 JD 2개 이상으로 custom package를 생성하고 결과를 비교해야 한다.
- 생성 결과가 JD별로 다르게 강조/제외되는지 확인해야 한다.

### 내부 베타

현재 상태: 80-85%

통과한 항목:

- README 온보딩이 있다.
- examples와 request prompts가 있다.
- readiness checklist와 output quality checklist가 있다.
- 샘플 custom package가 있다.

남은 gate:

- 실제 다른 사용자가 README만 보고 사용해봐야 한다.
- 막힌 지점을 문서에 반영해야 한다.

## Decision Rule

100%라고 말하려면 아래 중 하나를 통과해야 한다.

- 개인 사용 100%: 실제 회사 JD 2개 이상으로 custom package를 만들고, 각 결과물이 JD별로 다르게 맞춤화됐음을 확인했다.
- 내부 베타 100%: 최소 1명의 다른 사용자가 README와 examples만 보고 새 경험 입력부터 custom package 생성까지 완료했다.

이 두 조건을 통과하기 전에는 100%가 아니라 90-95%, 80-85%처럼 검증 전 점수로 말한다.
