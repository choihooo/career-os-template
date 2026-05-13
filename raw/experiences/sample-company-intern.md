# 모멘텀랩스 Product Frontend Intern Raw Memo

## Organization

- Name: 모멘텀랩스
- Role: Product Frontend Engineer Intern
- Period: 2025.03 - 2025.06
- Team: Product Engineering
- Links: https://momentum-labs.example

## Context

모멘텀랩스는 중소 브랜드가 주문, 정산, CS 상태를 한 화면에서 관리하는 B2B SaaS를 만드는 가상 회사다. 정유진은 제품 엔지니어링 팀 인턴으로 어드민 화면의 폼 검증, API 응답 타입, QA 재현 흐름을 정리했다.

## Work Scope

- React/TypeScript 기반 파트너 어드민 화면 개선
- API 응답 데이터와 화면 상태 흐름 정리
- QA에서 반복 발견되는 입력 검증 문제 개선
- 검증 실패 메시지와 사용자 입력 흐름의 연결 개선

## Achievements

### Type Safety Improvement

- 문제: 파트너 등록 폼에서 계약 시작일, 담당자 이메일, 정산 계좌 정보의 타입이 느슨해 QA에서 런타임 오류가 반복 발견됐다.
- 내 역할: 폼 스키마와 API 응답 타입을 정리하고 검증 실패 메시지를 화면 입력 흐름에 맞게 연결했다.
- 한 일: Zod 스키마, 명시 타입, 에러 메시지 매핑, 제출 버튼 disabled 조건을 추가했다.
- 결과: QA 재현 이슈 5건 중 4건이 입력 단계에서 차단됐다.
- 수치: 5건 중 4건
- 증빙: 가상 페르소나 자료라 실제 PR 링크 없음. 실제 사용 시 PR, 이슈, QA 재현 문서로 교체한다.

### QA Reproduction Note

- 문제: QA 이슈가 "저장 안 됨" 수준으로만 전달되어 개발자가 같은 상태를 재현하는 데 시간이 걸렸다.
- 내 역할: 입력값, API 응답, 화면 상태, 기대 메시지를 한 번에 기록하는 재현 템플릿을 만들었다.
- 결과: 폼 검증 이슈를 필드 단위로 분리해 논의할 수 있게 됐다.

## Gaps

- 실제 회사명, 링크, PR, 수치 근거는 사용자가 자기 자료로 교체해야 한다.
