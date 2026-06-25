# General Resume Brief

범용 이력서 v1/v2를 만들 때의 조립 기준이다. 이 파일은 최종 제출물이 아니라 출력 지시서다.

## Resume v1

### Intent

- 넓은 역할에 대응 가능한 안정적인 기본 이력서
- 과한 포지셔닝보다 사실, 역할, 성과를 선명하게 배치

### Reader Should Learn

- 어떤 역할을 해왔는가
- 어떤 문제를 주로 해결했는가
- 어떤 결과를 만들었는가
- 다음 역할에서 바로 활용 가능한 강점은 무엇인가

### Section Order

1. About Me
2. Work Experience
3. Projects
4. Awards & Activities

### Selection Rules

- 근거 수준이 높은 성과를 우선한다.
- 너무 회사 특화된 표현은 줄인다.
- 모든 bullet은 `wiki/sentence-bank/resume-bullets.md` 또는 개별 wiki 페이지를 근거로 한다.
- `Skills`, `Education`, 또는 다른 새 섹션이 필요하면 shared template-design change로 분리한다.
- Work Experience와 Projects는 같은 content shape을 사용한다.

## Resume v2

### Intent

- 더 선명한 포지셔닝을 가진 공격적인 버전
- 목표 역할이 분명할 때 사용

### Reader Should Learn

- 이 후보자가 남들과 다르게 강한 지점
- 반복적으로 증명된 문제 해결 패턴
- 이력서 안에서 바로 이해되는 대표 사례

### Section Order

1. About Me
2. Work Experience
3. Projects
4. Awards & Activities

### Selection Rules

- `wiki/themes/positioning.md`의 Main Narrative와 맞는 항목만 남긴다.
- 약한 경험을 많이 넣기보다 강한 경험을 압축한다.
- 직무 전환이나 포지션 전환이 있다면 Summary에서 먼저 해석한다.
- `Skills`, `Education`, 또는 다른 새 섹션이 필요하면 shared template-design change로 분리한다.
- JD나 목표 역할과 직접 연결되는 경험/프로젝트 contribution block을 우선 배치한다.

## Content Shape

렌더링 템플릿은 Work Experience와 Projects가 같은 형식으로 작성된다고 가정한다.

### Work Experience item

- 기간과 optional link
- 회사/역할명
- 1문장 소개
- 2개 이상의 contribution block

각 contribution block은 아래 순서를 따른다.

1. 기여 제목
2. 기술/도메인 태그 3-5개
3. 환경/문제/필요성이 드러나는 1-2줄 기여 요약
4. 무엇을 구현했는지 말하는 큰 구현 bullet
5. 큰 구현 bullet 아래의 어떻게 구현했는지 말하는 하위 구현 detail bullet
6. `Result:` 라인

기여 요약은 구현 방법을 반복하지 않고 “어떤 업무/서비스 환경에서 어떤 문제가 실제로 있었고, 왜 재발 방지나 개선이 필요했는지”를 설명한다. 필요하면 두 줄까지 허용한다. 큰 구현 bullet은 “무엇을 구현했는지”, 하위 구현 detail bullet은 “그 구현을 위해 구체적으로 어떻게 했는지”를 설명한다.

기본 기능 구현처럼 강한 문제 해결 claim이 없는 경우에는 과장하지 않는다. 요약은 "구현해야 했던 상황"을 쓰고, 큰 구현 bullet은 아래 둘 중 하나로 작성한다.

- 기술적 선택이 있으면 `A vs B` 중 무엇을 선택했고 왜 선택했는지 쓴다.
- 기술적 선택이 없으면 기본 구현 내용을 한 줄로 쓴다.

```md
#### 관리자 상세 조회 화면 구현

- Tags: React, TypeScript, API, UI State
- Summary: 운영자가 목록에서 항목을 선택한 뒤 상세 정보를 확인해야 하는 화면이 필요했습니다.
- 목록 선택, 상세 API 연동, 상세 패널 렌더링까지 이어지는 기본 조회 흐름을 구현했습니다.
  - API 응답 타입에 맞춰 기본 정보, 상태값, 메타 정보를 섹션별로 표시했습니다.
  - 로딩, 조회 실패, 데이터 없음 상태를 분리했습니다.
  - 값이 없는 필드는 fallback 문구로 표시했습니다.
- Result: 운영자가 목록 선택부터 상세 확인까지 한 화면에서 처리할 수 있는 기본 조회 기능 구축
```

```md
#### 필터 상태 관리 구현

- Tags: React, URL State, TanStack Query
- Summary: 운영자가 같은 조건으로 목록을 다시 확인하거나 공유해야 하는 화면이 필요했습니다.
- 화면 내부 state로만 관리하는 방식과 URL query에 반영하는 방식 중, 재현과 공유가 가능한 URL query 방식을 선택했습니다.
  - 필터 값을 URL query로 동기화했습니다.
  - 서버 요청 query key와 화면 입력 상태를 분리했습니다.
  - 초기화, 빈 결과, 로딩 상태를 조건별로 분리했습니다.
- Result: 같은 필터 조건을 링크로 재현할 수 있는 목록 조회 흐름 구축
```

```md
#### 피크타임 동시 조회 문제를 3계층 캐싱으로 개선

- Tags: Spring, Redis, Caffeine, Grafana
- Summary: 피크타임에 다수 사용자가 동시에 조회하는 환경에서 DB 커넥션 풀이 고갈되며 타임아웃이 발생했습니다.
- Caffeine 로컬 캐시, Redis 분산 캐시, pre-warming 배치를 조합한 3계층 캐싱 구조를 설계했습니다.
  - 캐시 키에 version 필드를 포함해 데이터 변경 시 즉시 무효화되도록 했습니다.
  - TTL jitter로 cache stampede를 줄이고, 기간 단위 분할 캐싱으로 hot key 집중을 완화했습니다.
  - hit rate, Redis RTT, eviction을 Grafana로 추적하고 pre-warm 실패 시 DB fallback을 보장했습니다.
- Result: 캐시 히트율 N%, 응답 N초 -> Nms, 피크타임 커넥션 고갈 해소
```

### Project item

- 기간과 optional link
- 프로젝트명
- 1문장 소개
- 2개 이상의 contribution block

프로젝트도 단일 bullet 묶음으로 끝내지 않는다. 경력처럼 기능, 문제 해결, 검증, 품질 개선 같은 기여 단위로 나눈다.

### Awards & Activities item

- 기간
- 활동/수상/검증명
- 2-4개 bullet

수상과 활동은 기본적으로 하나의 `Awards & Activities` 섹션에 합친다. 단순 참가보다 수상, 선정, 발표, 외부 검증, 운영 기여, 멘토링, 기술 글쓰기처럼 claim으로 연결 가능한 항목을 우선한다.

## Quality Bar

- 각 섹션이 서로 다른 정보를 전달해야 한다.
- Summary가 bullet의 반복 요약이 되면 줄인다.
- 모든 강한 표현은 근거 페이지로 역추적 가능해야 한다.
- placeholder가 남아 있으면 산출물로 보지 않는다.
- Work Experience와 Projects가 서로 다른 형식으로 작성되면 산출물로 보지 않는다.
