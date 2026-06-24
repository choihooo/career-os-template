# Product Readiness Criteria

이 문서는 Career OS Template을 복사한 사용자가 개인 사용, 내부 베타, 외부 배포 단계에서 어느 정도 준비됐는지 판단하는 기준이다. 점수는 느낌이 아니라 아래 조건을 통과한 정도로만 말한다.

## Readiness Levels

### 개인 사용 100%

혼자 반복해서 사용할 수 있는 상태다. 새 경험을 넣고, 범용 산출물을 만들고, 실제 JD에 맞춘 패키지를 생성할 수 있어야 한다.

필수 조건:

- 주요 경험이 `raw/`에 원천 자료로 저장되어 있다.
- 주요 경험이 `wiki/experiences/`, `wiki/projects/`, `wiki/activities/`, `wiki/awards/`, `wiki/skills/`에 정규화되어 있다.
- 강한 claim이 `wiki/claims-ledger.md`와 `wiki/proof-map.md`에 연결되어 있다.
- `wiki/overview/career-overview.md`와 `wiki/themes/positioning.md`에 목표 역할, 강점, 피해야 할 주장이 정리되어 있다.
- `wiki/sentence-bank/resume-bullets.md`에 실전 bullet이 20개 이상 있다.
- `wiki/stories/story-bank.md`에 STAR 스토리가 5개 이상 있다.
- `outputs/general/source/resume.md`가 자기 자료 기반으로 완성되어 있다.
- 필요하면 `outputs/general/final/resume.html`, `resume.pdf`를 생성할 수 있다.
- 실제 회사 JD 2개 이상으로 custom package를 생성해봤고, 결과가 서로 다르게 맞춤화된다.
- 생성된 custom package가 `source/jd.md`, `source/brief.md`, `source/resume.md`를 모두 포함한다.
- 근거가 부족한 수치나 역할은 생성하지 않고 `Gaps` 또는 `brief.md`에 남긴다.

100%가 아닌 경우:

- 데모 후보/회사 내용이 운영 레포에 남아 있다.
- 범용 산출물이 비어 있거나 placeholder가 남아 있다.
- JD를 넣어도 모든 회사에 비슷한 문서가 나온다.
- 강한 주장이 source page로 역추적되지 않는다.

### 내부 베타 100%

다른 사람이 README와 examples만 보고 직접 써볼 수 있는 상태다.

필수 조건:

- `README.md` 첫 화면에서 제품 목적과 사용 흐름을 이해할 수 있다.
- `examples/`에 프로젝트, 경력, 수상, JD, 요청 프롬프트 예시가 있다.
- `docs/checklists/`에 개인 준비도, 베타 준비도, custom output 품질 기준이 있다.
- 데모 데이터와 walkthrough는 별도 `career-os-template-samples` 레포에서 관리한다.
- markdown 산출물, HTML 템플릿, PDF export의 역할 차이가 설명되어 있다.
- 실패 조건이 설명되어 있다.
  - JD가 너무 짧은 경우
  - 링크 접근이 안 되는 경우
  - 근거가 부족한 수치가 있는 경우
  - 사용자의 역할 범위가 불명확한 경우
- 최소 1명의 베타 사용자가 README만 보고 새 경험 입력과 custom package 생성을 시도했다.
- 베타 사용자가 막힌 지점이 README, examples, checklist 중 하나에 반영됐다.

### 외부 배포 100%

저장소를 모르는 사용자도 안정적으로 사용할 수 있는 제품 상태다.

필수 조건:

- 온보딩 문서가 초보자 기준으로 검증되어 있다.
- 예시 입력에서 예시 결과까지 재현 가능한 end-to-end walkthrough가 있다.
- 3명 이상이 각자 다른 경력/JD로 사용해봤고, 실패 사례가 문서에 반영됐다.
- JD 링크 접근 실패, 빈 입력, 모호한 경력, 상충 수치 등 예외 케이스 처리 기준이 문서화되어 있다.
- 개인정보와 민감 정보 처리 원칙이 있다.
- 산출물 export 방식이 명확하다.
- 버전 관리와 변경 로그가 사용자가 이해할 수 있는 수준으로 정리되어 있다.

## Scoring Guide

| Level | Meaning |
|---|---|
| 0-30% | 구조나 아이디어만 있고 반복 사용은 어렵다. |
| 31-60% | 일부 흐름은 가능하지만 입력, 생성, 검수 중 하나가 끊긴다. |
| 61-80% | 개인 사용은 가능하나 예외 처리와 온보딩이 부족하다. |
| 81-95% | 대부분의 흐름이 닫혀 있고 실제 검증만 남았다. |
| 96-100% | 실제 JD 또는 사용자 테스트를 통과했고, 실패 조건까지 문서화되어 있다. |

## Template Gate

이 템플릿을 복사한 직후에는 100% 상태가 아니다. 실제 자료를 `raw/`와 `wiki/`에 등록하고, 최소 1개의 실제 JD로 `cos-apply-resume`을 실행한 뒤부터 개인 사용 준비도를 평가한다.
