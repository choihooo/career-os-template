# General Resume v1

## Summary

React와 TypeScript 기반으로 제품 UI, 운영 어드민, 데스크톱 앱, 디자인 시스템을 개발해 온 프론트엔드 엔지니어입니다. 사용자가 직접 겪는 흐름과 팀이 유지보수해야 하는 코드 구조를 함께 보고, 타입 안정성, 상태관리, 성능, 자동화로 문제를 줄이는 방식에 강점이 있습니다.

## Experience Highlights

### Frontend Engineer Intern, 아이겐코리아

- Period: 2025.03.04 - 2025.06.30
- Team: 개발실, 풀스택 1명, 백엔드 2명, 프론트엔드 1명

- TypeScript v3 기반 어드민을 v5와 strict 설정으로 단계 전환하고 50개 이상의 `any`를 명시 타입으로 바꿔, 빌드 시간을 약 19% 줄였습니다.
- 30개 이상 센터 정보를 API 기반 동적 로딩으로 전환하고 38개 파일의 하드코딩 참조를 제거해, 새 센터가 코드 수정 없이 반영되는 구조를 만들었습니다.
- 한국어 번역 파일을 기준으로 영/중/일 누락 키를 탐지하는 CI 검증을 구축해, 번역 누락이 PR 단계에서 차단되도록 했습니다.
- 목표 달성률과 YoY 지표를 센터별/전체 통계에 추가하고 Recharts 복합 차트와 엑셀 다운로드를 연동해 성과 분석 흐름을 보강했습니다.

## Projects

### 거부기린

- Electron 기반 멀티 윈도우 자세 교정 앱
- Tech: Electron, React, TypeScript, Zustand, MediaPipe Vision, TanStack Query

- 웹캠 기반 자세 추론을 always-on-top 위젯과 조건 기반 시스템 알림으로 연결해, 작업 흐름을 끊지 않는 실시간 자세 교정 UX를 구현했습니다.
- Zustand store를 카메라, 자세, 알림 도메인으로 분리하고 persist와 선택적 구독을 적용해 빈번한 자세 상태 업데이트의 렌더링 부담을 줄였습니다.
- React.lazy와 Vite manualChunks로 초기 번들 크기를 1.79MB에서 0.63MB로 줄여 약 65% 감소시켰습니다.
- 한국대학생IT경영학회 32기 밋업 프로젝트에서 프론트엔드 리드로 참여해 대상을 받았습니다.

### 대피로 디자인 시스템

- React 컴포넌트 라이브러리 및 디자인 시스템
- Tech: React, TypeScript, Vanilla Extract, tsup, Storybook, Vitest

- Compound Component와 Context 기반 API로 반복되는 레이아웃 변형 요구를 표준화해, 대응 시간을 1-2시간에서 5-10분으로 줄였습니다.
- ESM/CJS 듀얼 빌드와 타입 정의 자동 생성을 구성해 Next.js, Vite, Webpack 환경에서 사용할 수 있는 배포 구조를 만들었습니다.
- Vitest와 Storybook Test Runner 검증을 CI에 연결해 컴포넌트별 20개 이상 케이스와 80% 이상 커버리지를 유지했습니다.

### 수상한 녀석들

- 광고 공모전 출품작 분석 AI 서비스
- Tech: Next.js, TypeScript, Zod, MSW, Tailwind

- AuthGuard와 `useAuth` 기반 진입 전 인증 검사로 화면 깜빡임을 줄이고, 미인증 사용자를 로그인 모달과 리다이렉트 흐름으로 연결했습니다.
- `@use-funnel/browser`와 Zod 단계별 검증으로 뒤로가기/새로고침에도 상태가 유지되는 멀티스텝 폼 흐름을 구현했습니다.
- 약 100명 대상 운영에서 62명에게 사용 흐름이 직관적이고 작성하기 편하다는 정성 피드백을 확보했습니다.

## Awards and Activities

- 2025.12 한국대학생IT경영학회 32기 밋업 프로젝트 대상, 거부기린 프론트엔드 리드
- 2025.10 SW중심대학 2025 해커톤 SUMTECH 장려상
- 2025.09 직행 기업 연계 프로젝트 우수상, 프론트엔드 리드
- 2024.12 KT&G 상상 유니브 왓에버 아이디어톤 대상
- 2024.10 부산 해양 데이터 해커톤 장려상
- 2021.11 대학생 하계 논문 학술대회 금상, 제1저자

## Skills

- Frontend: React, Next.js, TypeScript, JavaScript, Electron
- State and Data: Zustand, Recoil, TanStack Query, React Router Loader, Zod
- UI and Styling: Tailwind CSS, Vanilla Extract, Recharts, Storybook
- Tooling: Vite, tsup, Vitest, Storybook Test Runner, Biome, GitHub Actions, AWS CodePipeline
- Strengths: 타입 안정성 개선, 상태관리 설계, 성능 최적화, UX 흐름 개선, 검증 자동화
