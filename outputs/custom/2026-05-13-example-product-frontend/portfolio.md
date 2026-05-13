# 정유진 Frontend Portfolio

## Positioning

이 포트폴리오는 Example Product JD가 요구하는 업무용 UI, 상태 설계, 입력 검증, 운영자 대시보드 경험을 보여주기 위해 구성했다. 사례는 기능 구현 목록이 아니라 문제, 기술 판단, 결과, 화면 증빙이 함께 보이도록 정리한다.

## Cover

- Candidate: 정유진
- Role: Product Frontend Engineer
- Projects:
  - OpsPulse Dashboard
  - ReviewFlow Admin
  - FormGuard System
- Visual assets:
  - generated person profile image
  - dashboard overview
  - dashboard filter/report detail
  - review queue
  - review detail panel
  - form validation screen
  - form error mapping
  - QA reproduction checklist

## Case Study 1. OpsPulse Dashboard

### Problem

브랜드 운영자는 광고비, 주문 수, CS 문의 수를 CSV로 따로 내려받아 주간 리포트를 만들었다. 필터 조건을 공유하기 어렵고, 같은 조건으로 다시 확인하는 과정도 반복적이었다.

### Decision

서버에서 받아오는 데이터 상태와 사용자가 조작하는 필터 상태를 분리했다. 필터 조건은 URL query에 동기화해 다른 사람에게 같은 화면 상태를 공유할 수 있게 했다.

### Action

- TanStack Query로 서버 상태, 로딩 상태, 재요청 흐름을 관리했다.
- URL query에 필터 조건을 동기화해 새로고침과 링크 공유 후에도 같은 조건이 유지되게 했다.
- 기간, 브랜드, 채널 조건을 query key에 포함해 조건 변경 시 필요한 데이터만 다시 요청하도록 구성했다.
- Recharts로 주요 지표와 추세를 시각화했다.
- 로딩, 빈 상태, 에러 상태를 분리해 운영자가 데이터 상태를 오해하지 않도록 했다.
- 테이블과 차트가 동일한 필터 상태를 기준으로 렌더링되도록 구성했다.

### Result

운영자로부터 주간 리포트 작성 시간이 2시간에서 30분으로 줄었다는 피드백을 받았다. 필터 조건 공유와 재현도 쉬워졌다는 정성 피드백이 있었다.

### Interview Expansion

- 왜 URL query를 필터 상태의 기준으로 삼았는가
- query key에 어떤 조건을 넣고 어떤 조건은 화면 상태로만 유지했는가
- 차트와 테이블의 수치 불일치 가능성을 어떻게 줄였는가

## Case Study 2. ReviewFlow Admin

### Problem

검토 담당자가 신청 상태, 누락 서류, 담당자 메모를 여러 화면에서 확인했다. 필터 조건을 팀원에게 전달하려면 스크린샷이나 구두 설명에 의존해야 했다.

### Decision

상태별 탭, URL query 필터, 상세 패널, 액션 버튼 상태를 분리했다. 같은 조건의 검토 큐를 링크로 공유하고 화면 이동 없이 핵심 정보를 확인하도록 정보 구조를 재배치했다.

### Action

- 검토 상태별 탭과 리스트 필터를 URL query로 동기화했다.
- 상세 패널에서 누락 서류, 담당자 메모, 처리 액션을 한 번에 확인하도록 배치했다.
- 액션 버튼의 loading, disabled, error 상태를 명시해 중복 처리와 잘못된 제출을 줄였다.
- 승인 실패, 권한 없음, 이미 처리됨 상태를 구분해 운영자가 다음 행동을 판단할 수 있게 메시지를 분리했다.
- QA 재현 조건을 URL query와 선택 행 기준으로 남기도록 체크리스트를 작성했다.

### Result

검토 담당자가 같은 조건의 큐를 팀원에게 링크로 전달할 수 있게 됐다. 화면 이동 없이 누락 서류와 처리 상태를 확인할 수 있게 됐다는 정성 피드백이 있었다.

### Interview Expansion

- 리스트와 상세 패널을 분리한 이유
- 액션 버튼 disabled 조건을 나눈 기준
- 운영자 피드백을 화면 정보 구조로 바꾼 과정

## Case Study 3. FormGuard System

### Problem

폼마다 입력 상태와 에러 메시지 표현이 달라 QA 피드백이 반복됐다. 사용자가 어떤 입력을 잘못했는지 화면에서 바로 알기 어려웠다.

### Decision

입력 단계에서 오류를 차단하도록 폼 스키마와 API 응답 타입을 정리했다. 검증 실패는 명시적인 에러 메시지로 매핑하고 컴포넌트 상태별 UI 규칙을 분리했다.

### Action

- Zod 스키마를 추가해 입력 데이터의 구조와 검증 기준을 명시했다.
- API 응답 타입을 정리해 화면 상태와 서버 응답 간 불일치를 줄였다.
- label, helper text, error text, disabled state의 우선순위를 정의했다.
- 서버 에러는 폼 하단, 필드 에러는 입력 필드 하단에 배치해 원인 위치를 분리했다.
- 입력값, URL query, API 응답, 기대 메시지를 함께 남기는 QA 재현 체크리스트를 작성했다.
- 키보드 접근과 focus ring 동작을 점검했다.

### Result

QA 재현 이슈 5건 중 4건이 사전 검증 단계에서 차단됐다. 신규 폼 화면에서 상태별 UI 리뷰 기준도 명확해졌다.

### Interview Expansion

- Zod 스키마와 UI 메시지 매핑을 분리한 이유
- 필드 에러와 서버 에러의 위치를 다르게 둔 이유
- 폼 화면이 늘어날 때 상태 규칙을 재사용한 방식

## JD Connection

- Dashboard UI: OpsPulse에서 운영자가 지표, 필터, 추세를 한 화면에서 비교하도록 설계했다.
- API State: TanStack Query와 URL query를 분리해 서버 상태와 화면 조건을 재현 가능하게 만들었다.
- Admin Workflow: ReviewFlow에서 검토 큐, 상세 패널, 액션 버튼 상태를 나눴다.
- Form Quality: FormGuard에서 입력 검증, 에러 메시지 우선순위, QA 재현성을 정리했다.
