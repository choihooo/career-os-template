# 아이겐코리아 프론트엔드 인턴

## Identity

- Organization: 아이겐코리아
- Role: Frontend Engineer 인턴
- Period: 2025.03.04 - 2025.06.30
- Team: 개발실, 풀스택 1명, 백엔드 2명, 프론트엔드 1명
- Employment type: 인턴
- Related raw source: `raw/experiences/eigene-korea-intern.md`

## Context

- Organization or product: 빅데이터 기반 개인화 추천 및 마케팅 솔루션 회사
- Team mission: 어드민과 데모 페이지의 기능 안정성, 운영 효율, 클라이언트 대응 속도 개선
- Business or user problem: 하드코딩된 운영 데이터, 노후 TypeScript 버전, 다국어 키 누락, 지표 부족으로 인해 유지보수와 운영 안정성에 병목이 있었다.

## Responsibilities

- Primary responsibility: 프론트엔드 인턴으로 어드민 안정화, 기능 개발, QA 대응 수행
- Secondary responsibilities: 서비스 데모 페이지 개발, 클라이언트 요청 기반 이슈 대응, 차트/엑셀 기능 개선
- Scope: 유일한 프론트엔드 담당자로 일부 업무를 직접 설계하고 구현

## Achievements

### TypeScript v3 to v5 Migration

- What happened: 노후 TypeScript 버전과 비활성화된 strict 설정으로 최신 라이브러리 충돌과 타입 안정성 문제가 있었다.
- My role: 단계별 마이그레이션 전략을 세우고 `any` 타입 50개 이상을 명시적 타입으로 전환했다.
- Metric: 빌드 평균 246.22초에서 199.51초로 약 19% 단축
- Evidence: https://hochoi.tistory.com/23, https://hochoi.tistory.com/25
- Related projects: 어드민 TypeScript 마이그레이션
- Resume bullet candidate: TypeScript v3 기반 어드민을 v5와 strict 설정으로 단계 전환하고 50개 이상의 `any`를 명시 타입으로 바꿔, 빌드 시간을 약 19% 줄였다.
- Portfolio relevance: 기술 부채를 한번에 뒤집지 않고 단계적으로 낮춘 사례

### i18n Validation Automation

- What happened: 일부 언어의 번역 키가 누락되어 운영 환경에 키 문자열이 노출될 위험이 있었다.
- My role: 한국어 JSON을 기준으로 언어별 키 차이를 계산하는 Node.js 검증 스크립트를 구현하고 CI에 연결했다.
- Metric: 정량 운영 지표는 미확보
- Evidence: `raw/experiences/eigene-korea-intern.md`
- Related projects: 어드민 i18n 검증 자동화
- Resume bullet candidate: 한국어 번역 파일을 기준으로 영/중/일 누락 키를 탐지하는 CI 검증을 구축해, 번역 누락이 PR 단계에서 차단되도록 했다.
- Portfolio relevance: 품질 검증을 개발 프로세스에 넣은 자동화 사례

### Bounce Admin Center API Migration

- What happened: 30개 이상의 센터 정보가 프론트엔드에 하드코딩되어 새 센터 추가 때마다 코드 수정과 배포가 필요했다.
- My role: API 기반 동적 로딩으로 전환하고 Recoil atom/selector, LocalStorage effect 기반 상태 구조를 설계했다.
- Metric: 38개 파일의 하드코딩 참조 제거
- Evidence: `raw/experiences/eigene-korea-intern.md`
- Related projects: 바운스사 센터 데이터 API 전환
- Resume bullet candidate: 30개 이상 센터 정보를 API 기반 동적 로딩으로 전환하고 38개 파일의 하드코딩 참조를 제거해, 새 센터가 코드 수정 없이 반영되는 구조를 만들었다.
- Portfolio relevance: 운영 데이터의 단일 출처와 상태관리 설계 사례

### Metric Visualization

- What happened: 실적 현황판에 목표 달성률과 전년 대비 증감률이 없어 성과 분석이 제한적이었다.
- My role: 센터별/전체 통계, Recharts 복합 차트, 엑셀 다운로드 연동을 구현했다.
- Metric: 정량 사용 지표는 미확보
- Evidence: `raw/experiences/eigene-korea-intern.md`
- Resume bullet candidate: 목표 달성률과 YoY 지표를 센터별/전체 통계에 추가하고 Recharts 복합 차트와 엑셀 다운로드를 연동해 성과 분석 흐름을 보강했다.
- Portfolio relevance: 비즈니스 지표를 UI와 데이터 가공 로직으로 연결한 사례

## Skills Used

- TypeScript
  - Context: v3 to v5 마이그레이션, strict 전환, 타입 안정성 강화
  - Strength level: high
  - Evidence: 빌드 시간 19% 단축, 50개 이상 any 전환
- React
  - Context: 어드민 기능 개발과 상태 연동
  - Strength level: medium
  - Evidence: Recoil 구조, Recharts 차트
- Automation
  - Context: i18n 누락 검증 CI
  - Strength level: medium
  - Evidence: PR 단계 차단 흐름

## Output Notes

- Best for resume: TypeScript 마이그레이션, 센터 API 전환, i18n 자동화
- Best for portfolio: API 전환/Recoil 설계, i18n CI 자동화, TypeScript 단계 전환
- Best for interview: 혼자 프론트엔드 책임 범위를 잡고 기술 부채를 낮춘 경험
- Claims to avoid: 대규모 트래픽 운영 경험, 매출 기여, 조직 리딩
