# General Portfolio v1

## Profile

React와 TypeScript를 기반으로 제품 UI, 운영 어드민, 데스크톱 앱, 디자인 시스템을 개발해 왔습니다. 제 포트폴리오는 화려한 화면보다 사용자가 막히는 흐름, 팀이 반복해서 겪는 유지보수 비용, 운영 단계에서 드러나는 안정성 문제를 어떻게 줄였는지에 초점을 둡니다.

## Featured Projects

### 1. 아이겐코리아 어드민 개선

- Role: Frontend Engineer Intern
- Period: 2025.03.04 - 2025.06.30
- Keywords: TypeScript migration, i18n automation, Recoil, Recharts
- Why featured: 실제 조직의 운영 어드민에서 타입 안정성, 데이터 구조, 검증 자동화를 개선한 경험

### 2. 거부기린

- Role: Frontend Lead
- Period: 2025.10.04 - 2025.12.07
- Keywords: Electron, Zustand, MediaPipe Vision, always-on-top, bundle optimization
- Why featured: 실시간 자세 분석과 데스크톱 UX, 상태관리, 성능 최적화를 함께 다룬 프로젝트

### 3. 대피로 디자인 시스템

- Role: Frontend Library Developer
- Period: 2025.08.12 - 진행중
- Keywords: Compound Component, Vanilla Extract, tsup, Storybook, Vitest
- Why featured: 반복되는 UI 변형 요구를 컴포넌트 API와 검증 자동화로 줄인 사례

## Case Studies

### Case Study 1. 하드코딩된 운영 데이터를 API 기반 상태 구조로 전환

- Context: 아이겐코리아 어드민에 30개 이상의 센터 정보가 하드코딩되어 있었다.
- Problem: 새 센터가 추가될 때마다 프론트엔드 코드 수정과 재배포가 필요했고, 백엔드 데이터와 프론트엔드 코드가 어긋날 위험이 있었다.
- My Role: 센터 목록을 API 기반 동적 로딩으로 전환하고 Recoil 기반 상태 구조를 설계했다.
- What I Did: atom을 서버 응답 raw 데이터 저장소로 두고 selector를 화면별 가공 레이어로 분리했다. 38개 파일의 하드코딩 참조를 제거하고 LocalStorage effect로 새로고침 이후 중복 호출을 줄였다.
- Result: 새 센터가 코드 수정 없이 반영되는 구조를 만들었다.
- Proof: `wiki/experiences/eigene-korea.md`
- Tools or Skills: React, TypeScript, Recoil, LocalStorage

### Case Study 2. 자세 교정 앱의 실시간 상태와 알림 UX 설계

- Context: 거부기린은 웹캠 자세 분석 결과를 데스크톱 위젯과 알림으로 전달하는 Electron 앱이다.
- Problem: 자세 상태는 자주 바뀌지만, 알림이 잦으면 작업 흐름을 방해한다.
- My Role: 프론트엔드 리드로 상태관리 구조와 위젯 UX를 설계했다.
- What I Did: 카메라, 자세, 알림 설정을 Zustand 도메인 store로 분리했고, always-on-top 위젯과 조건 기반 시스템 알림을 조합했다.
- Result: 작업을 멈추지 않고 자세 이상을 인지하는 UX를 구현했다. 초기 번들도 1.79MB에서 0.63MB로 줄였다.
- Proof: GitHub, 다운로드 페이지, 수상 기사
- Tools or Skills: Electron, React, TypeScript, Zustand, Vite, MediaPipe Vision

### Case Study 3. 반복되는 UI 변형을 디자인 시스템 API로 흡수

- Context: 대피로 서비스에서 레이아웃 변형 요구가 자주 생겼다.
- Problem: 매번 구현 비용이 발생하고 컴포넌트 변경 영향이 커졌다.
- My Role: 컴포넌트 API, 빌드 파이프라인, 테스트 자동화를 설계했다.
- What I Did: Compound Component와 Context 기반 API로 조합 가능한 컴포넌트를 만들고, ESM/CJS 듀얼 빌드와 Storybook Test Runner 검증을 구성했다.
- Result: 요구사항 대응 시간이 1-2시간에서 5-10분으로 줄었다.
- Proof: GitHub, 블로그
- Tools or Skills: React, TypeScript, Vanilla Extract, tsup, Vitest, Storybook

## Awards and Activities

- 한국대학생IT경영학회 32기 밋업 프로젝트 대상, 거부기린 프론트엔드 리드
- 직행 기업 연계 프로젝트 우수상, 프론트엔드 리드
- SW중심대학 2025 해커톤 SUMTECH 장려상
- KT&G 상상 유니브 왓에버 아이디어톤 대상
- 부산 해양 데이터 해커톤 장려상
- 2021 대학생 하계 논문 학술대회 금상, 제1저자
