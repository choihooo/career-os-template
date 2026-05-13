# 플로우키트 Frontend Part-time Raw Memo

## Organization

- Name: 플로우키트
- Role: Frontend Engineer Part-time
- Period: 2024.09 - 2025.02
- Team: Growth Product
- Links: https://flowkit.example

## Context

플로우키트는 내부 운영팀이 신청서 검토, 누락 서류 확인, 승인 처리를 하는 워크플로 도구를 만드는 가상 SaaS 팀이다. 정유진은 파트타임 프론트엔드 엔지니어로 운영자 검토 큐와 폼 컴포넌트 상태 규칙을 정리했다.

## Work Scope

- 운영자가 매일 확인하는 신청서 검토 화면 개선
- 테이블 필터, 검토 상태, 상세 패널의 상태 흐름 정리
- 반복되는 폼 컴포넌트와 검증 메시지를 공통 패턴으로 정리
- 운영자 피드백을 반영한 정보 구조 조정

## Achievements

### Review Queue Workflow

- 문제: 검토 담당자가 신청 상태, 누락 서류, 담당자 메모를 여러 화면에서 확인했다.
- 내 역할: 리스트, 필터, 상세 패널의 화면 상태를 설계하고 React 컴포넌트로 구현했다.
- 한 일: 검토 상태별 탭, URL query 필터, 상세 패널, 액션 버튼 상태를 분리했다.
- 결과: 같은 조건의 검토 큐를 팀원에게 링크로 전달할 수 있게 됐다.
- 결과: 화면 이동 없이 누락 서류와 처리 상태를 확인할 수 있게 됐다는 정성 피드백을 받았다.
- 수치: 가상 페르소나 자료라 실제 수치 없음. 실제 사용 시 검토 시간, 클릭 수, QA 이슈 수로 교체한다.

### Form Component Rules

- 문제: 폼 화면마다 label, helper text, error state, disabled state 표현이 달라 QA 피드백이 반복됐다.
- 내 역할: 입력 컴포넌트의 상태별 UI 규칙을 정리하고 재사용 컴포넌트로 분리했다.
- 한 일: default, focus, error, disabled 상태의 스타일과 메시지 우선순위를 정의했다.
- 결과: 신규 폼 화면의 UI 리뷰 기준을 명확히 만들었다.

## Gaps

- 실제 회사명, 링크, PR, 화면 캡처, 측정 수치는 사용자가 자기 자료로 교체해야 한다.
