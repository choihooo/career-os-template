# OpsPulse Dashboard Project Raw Memo

## Project

- Name: OpsPulse Dashboard
- Period: 2025.07 - 2025.08
- Team: 4명
- Role: Frontend Lead
- Links: https://github.com/yujin-jung-career/opspulse-dashboard

## Context

- 어떤 문제를 풀었나: 운영자가 광고비, 주문 수, CS 문의 수를 CSV로 따로 내려받아 주간 리포트를 만들던 흐름을 한 화면으로 모았다.
- 사용자는 누구였나: 브랜드 운영 담당자와 그로스 매니저
- 제약 조건: 짧은 개발 기간, API 스펙 변경 가능성, 모바일보다 데스크톱 우선 사용

## My Work

- TanStack Query로 서버 상태를 분리했다.
- 필터 상태를 URL query와 동기화했다.
- Recharts로 주요 지표와 추세를 시각화했다.
- 로딩, 빈 상태, 에러 상태를 분리해 운영자가 데이터 상태를 오해하지 않도록 했다.
- 리포트 공유를 위해 필터 조건을 링크에 남기는 흐름을 설계했다.

## Result

- 수치: 주간 리포트 작성 시간이 2시간에서 30분으로 감소했다는 운영자 피드백
- 정성 결과: 필터 공유와 재현이 쉬워졌다는 피드백
- 증빙 링크: 가상 페르소나 자료라 실제 링크 없음
- 아직 근거가 부족한 부분: 실제 사용 로그와 before/after 측정 자료
