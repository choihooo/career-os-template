# Sample SaaS Part-time Frontend Raw Memo

## Organization

- Name: Sample SaaS Lab
- Role: Frontend Engineer Part-time
- Period: 2024.09 - 2025.02
- Team: Growth Product
- Links: https://example.com/sample-saas

## Work Scope

- 운영자가 매일 확인하는 신청서 검토 화면 개선
- 테이블 필터, 검토 상태, 상세 패널의 상태 흐름 정리
- 반복되는 폼 컴포넌트와 검증 메시지를 공통 패턴으로 정리

## Achievements

### Review Queue Workflow

- 문제: 검토 담당자가 신청 상태, 누락 서류, 담당자 메모를 여러 화면에서 확인했다.
- 내 역할: 리스트, 필터, 상세 패널의 화면 상태를 설계하고 React 컴포넌트로 구현했다.
- 한 일: 검토 상태별 탭, URL query 필터, 상세 패널, 액션 버튼 상태를 분리했다.
- 결과: 검토 담당자가 같은 조건을 팀원에게 링크로 전달할 수 있게 됐다.
- 수치: 샘플 raw라 실제 수치 없음. 실제 사용 시 검토 시간, 클릭 수, QA 이슈 수로 교체한다.

### Form Component Rules

- 문제: 폼 화면마다 label, helper text, error state, disabled state 표현이 달라 QA 피드백이 반복됐다.
- 내 역할: 입력 컴포넌트의 상태별 UI 규칙을 정리하고 재사용 컴포넌트로 분리했다.
- 한 일: default, focus, error, disabled 상태의 스타일과 메시지 우선순위를 정의했다.
- 결과: 신규 폼 화면의 UI 리뷰 기준을 명확히 만들었다.

## Gaps

- 실제 회사명, 링크, PR, 화면 캡처, 측정 수치는 사용자가 자기 자료로 교체해야 한다.
