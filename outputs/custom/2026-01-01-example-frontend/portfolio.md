# Example Frontend Tailored Portfolio

## Narrative

이 JD는 React/TypeScript 구현뿐 아니라 사용자 흐름과 상태관리 판단을 본다. 따라서 샘플 포트폴리오는 대시보드 필터 흐름과 폼 검증 사례를 앞에 둔다.

## Case Study 1. Sample Dashboard

- Problem: 운영자가 여러 파일을 오가며 주간 리포트를 만들었다.
- Decision: 서버 상태와 필터 상태를 분리하고, 필터 조건은 URL에 동기화했다.
- Action: TanStack Query, URL query, Recharts를 사용했다.
- Result: 리포트 작성 시간이 줄었다는 피드백을 받았다.
- Proof: 실제 사용자는 링크와 스크린샷으로 교체한다.

## Case Study 2. Sample Company Form Validation

- Problem: 폼 데이터 오류가 QA 단계에서 반복 발견됐다.
- Decision: 입력 단계에서 오류를 차단하도록 스키마와 타입을 정리했다.
- Action: Zod 스키마와 명시 타입을 적용했다.
- Result: QA 재현 이슈 5건 중 4건을 입력 단계에서 차단했다.

## Gaps

- 샘플 수치와 링크는 실제 근거로 교체해야 한다.
