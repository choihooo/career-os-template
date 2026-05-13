# 정유진

React와 TypeScript로 운영자 대시보드, 검토 큐, 폼 입력 흐름을 개선하는 제품 프론트엔드 엔지니어

- Email: yujin.jung@career.example
- GitHub: https://github.com/yujin-jung-career
- Portfolio: https://yujin-jung-career.example
- Target: Frontend Engineer at Example Product

## Summary

React와 TypeScript 기반으로 B2B SaaS의 어드민, 대시보드, 폼 입력 흐름을 개선해 온 제품 프론트엔드 엔지니어입니다. TanStack Query로 서버 상태를 분리하고 URL query로 필터 상태를 재현 가능하게 만든 경험이 있으며, Zod 스키마와 명시 타입을 적용해 QA 단계에서 반복되던 입력 오류를 사전에 차단했습니다. 운영자가 반복하는 리포트, 검토, 승인 흐름을 줄이는 UI 구조와 유지보수 가능한 상태 설계에 강점이 있습니다.

## Skills

- Frontend: React, TypeScript, HTML, CSS, component architecture
- State and Data: TanStack Query, URL query state, API response typing, loading/error/empty states
- Validation: Zod, form schema, error message mapping, typed submit flow
- Visualization: Recharts, dashboard metrics, report-oriented layout
- Collaboration: Git, issue-based QA reproduction, product requirement breakdown, documentation

## Experience

### 모멘텀랩스 | Product Frontend Engineer Intern

2025.03 - 2025.06

- 파트너 어드민의 계약 등록, 정산 계좌, 담당자 정보 입력 화면에서 API 응답 타입과 화면 상태 흐름을 정리했다.
- 계약 시작일, 담당자 이메일, 정산 계좌 정보의 런타임 오류를 Zod 스키마와 명시 타입으로 입력 단계에서 검증하도록 개선했다.
- 에러 메시지 매핑과 제출 버튼 disabled 조건을 추가해 QA 재현 이슈 5건 중 4건을 사전 검증 단계에서 차단했다.
- 입력값, API 응답, 화면 상태, 기대 메시지를 함께 남기는 QA 재현 템플릿을 만들어 폼 검증 이슈를 필드 단위로 논의할 수 있게 했다.
- 파트너 목록 테이블의 로딩, 빈 상태, 권한 없음, 서버 에러 상태를 구분해 운영자가 현재 처리 가능 여부를 바로 알 수 있게 했다.
- 반복되는 필터 초기화, 저장 전 확인, 제출 실패 토스트 문구를 정리해 QA 피드백을 화면 상태별로 분류했다.

### 플로우키트 | Frontend Engineer Part-time

2024.09 - 2025.02

- 운영자가 신청서 상태와 누락 서류를 빠르게 검토하도록 어드민 검토 큐 화면을 구현했다.
- 상태별 탭, URL query 필터, 상세 패널, 액션 버튼 상태를 분리해 같은 조건의 검토 큐를 링크로 공유할 수 있게 했다.
- default, focus, error, disabled 상태 규칙을 정리해 신규 폼 화면의 UI 리뷰 기준을 명확히 했다.
- 검토 상세 패널에서 신청자 정보, 누락 서류, 담당자 메모, 처리 액션을 한 번에 확인하도록 정보 구조를 재배치했다.
- 액션 버튼의 loading, disabled, error 상태를 명시해 중복 승인과 실패 후 재시도 흐름을 분리했다.
- QA가 남긴 재현 조건을 URL query와 선택 행 기준으로 다시 확인할 수 있게 테스트 체크리스트를 작성했다.

## Projects

### OpsPulse Dashboard | Frontend Lead

2025.07 - 2025.08

- 광고비, 주문 수, CS 문의 수를 CSV로 따로 내려받아 만들던 주간 리포트를 한 화면에서 확인할 수 있는 대시보드로 구현했다.
- TanStack Query로 서버 상태를 분리하고, 필터 상태를 URL query와 동기화해 조건 공유와 재현을 쉽게 만들었다.
- Recharts로 주요 지표와 추세를 시각화하고 로딩, 빈 상태, 에러 상태를 분리했다.
- 필터 조건을 query key에 반영해 기간, 채널, 브랜드 조건 변경 시 필요한 데이터만 다시 요청하도록 구성했다.
- 테이블과 차트가 같은 필터 상태를 바라보게 만들어 리포트 화면의 수치 불일치 가능성을 줄였다.
- 운영자로부터 주간 리포트 작성 시간이 2시간에서 30분으로 줄었다는 피드백을 받았다.

### ReviewFlow Admin | Frontend Owner

2025.01 - 2025.02

- 신청서 상태, 누락 서류, 담당자 메모를 한 화면에서 확인하는 운영자 검토 큐를 만들었다.
- 리스트 필터와 상세 패널의 책임을 분리하고 액션 버튼의 loading, disabled, error 상태를 명시했다.
- 운영자가 화면 이동 없이 누락 서류와 처리 상태를 확인할 수 있게 정보 구조를 재배치했다.
- 검토 상태 탭과 URL query를 연결해 "누락 서류 + 담당자 지정" 같은 조건을 팀원에게 그대로 전달할 수 있게 했다.
- 승인 실패, 권한 없음, 이미 처리됨 상태를 구분해 운영자가 다음 행동을 판단할 수 있게 메시지를 나눴다.

### FormGuard System | Frontend Contributor

2024.11 - 2024.12

- label, helper text, error text, disabled state의 우선순위를 정의하고 Input, Select, DateField 컴포넌트를 정리했다.
- Zod 스키마와 UI 에러 메시지 매핑 규칙을 분리해 입력 검증과 표시 책임을 명확히 했다.
- 키보드 접근과 focus ring 동작을 점검해 폼 입력 흐름의 기본 사용성을 보강했다.
- 제출 버튼 활성 조건, 서버 에러 표시 위치, 필드별 helper text 우선순위를 문서화했다.
- 신규 폼 화면에서 QA가 입력 필드 단위로 재현 경로를 남길 수 있도록 상태 이름과 메시지 규칙을 맞췄다.

## Education

한빛대학교 컴퓨터공학

2021.03 - 2026.02 졸업 예정

영문학과 부전공, 성균관사이버대학교

2023.03 - 2025.02

## Certification

- SQLD, 한국데이터산업진흥원, 2025.04

## Awards

### SaaS Ops Prototype Challenge 우수상

2025.09

- OpsPulse Dashboard의 운영 지표 대시보드 프로토타입으로 30개 팀 중 3위를 기록했다.
- 필터 재현성, 차트 기반 리포트 흐름, 실제 운영자 문제와 연결된 UX 설명을 맡았다.

### 한빛대학교 SW 캡스톤 쇼케이스 장려상

2024.12

- 팀 프로젝트에서 프론트엔드 화면 구조와 폼 검증 파트를 담당했다.
- 테이블 필터, 상세 패널, 제출 전 검증 흐름을 React 컴포넌트로 구현했다.

### Product Builders UI Challenge 입선

2024.10

- 운영자용 테이블 필터와 빈 상태 UX 개선안을 제출했다.
- 검색 조건 저장과 링크 공유 흐름을 화면 플로우로 설계했다.

## External Experience

### 한빛대학교 웹서비스 개발 동아리 H-Builder | 프론트엔드 운영진

2024.03 - 2024.12

- React 기초 스터디와 TypeScript 전환 실습 세션을 운영하며 주니어 학회원 12명의 과제 리뷰를 진행했다.
- 공통 과제로 어드민 테이블, 검색 필터, 폼 검증 화면을 설계해 실무형 UI 패턴을 반복 연습했다.
- GitHub Issues와 Pull Request 템플릿을 도입해 요구사항, 구현 내용, QA 체크리스트를 함께 남기도록 운영했다.

### Campus Product Lab | 프론트엔드 멘토

2025.03 - 2025.05

- 6주 제품 프로토타입 프로그램에서 3개 팀의 화면 구조, 상태 관리, 폼 UX 리뷰를 담당했다.
- Figma 시안을 React 컴포넌트 단위로 나누고 빈 상태, 로딩 상태, 에러 상태를 먼저 정의하도록 가이드했다.
- 최종 데모 전 Playwright screenshot check로 주요 화면의 레이아웃 깨짐을 점검했다.
