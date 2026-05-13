# Sample Form System Project Raw Memo

## Project

- Name: Sample Form System
- Period: 2024.11 - 2024.12
- Team: 2명
- Role: Frontend Contributor
- Links: https://github.com/example/sample-form-system

## Context

- 어떤 문제를 풀었나: 폼마다 입력 상태와 에러 메시지 표현이 달라 QA 피드백이 반복됐다.
- 사용자는 누구였나: 폼을 작성하는 외부 사용자와 내부 QA 담당자
- 제약 조건: 기존 화면을 한 번에 갈아엎을 수 없어서 새 폼부터 점진 적용해야 했다.

## My Work

- label, helper text, error text, disabled state의 우선순위를 정의했다.
- Zod 스키마와 UI 에러 메시지 매핑 규칙을 분리했다.
- 공통 Input, Select, DateField 컴포넌트를 작성했다.
- 키보드 접근과 focus ring 동작을 점검했다.

## Result

- 정성 결과: 신규 폼 화면에서 상태별 UI 리뷰 기준이 명확해졌다.
- 정성 결과: QA가 재현 경로를 입력 필드 단위로 남길 수 있게 됐다.
- 증빙 링크: 샘플 raw라 실제 링크 없음
- 아직 근거가 부족한 부분: 재사용률, QA 피드백 감소율
