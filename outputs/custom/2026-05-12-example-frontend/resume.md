# Tailored Resume

## Summary

React와 TypeScript 기반으로 사용자 흐름과 유지보수성을 함께 개선해 온 프론트엔드 엔지니어입니다. 운영 어드민에서는 TypeScript 마이그레이션과 i18n 검증 자동화로 안정성을 높였고, 데스크톱 앱과 제품 프로젝트에서는 상태관리, 인증, 폼, 알림 UX를 사용자가 덜 막히는 구조로 바꿨습니다.

## Experience

### Frontend Engineer Intern, 아이겐코리아

- TypeScript v3 기반 어드민을 v5와 strict 설정으로 단계 전환하고 50개 이상의 `any`를 명시 타입으로 바꿔, 빌드 시간을 약 19% 줄였습니다.
- 30개 이상 센터 정보를 API 기반 동적 로딩으로 전환하고 38개 파일의 하드코딩 참조를 제거해, 새 센터가 코드 수정 없이 반영되는 구조를 만들었습니다.
- 한국어 번역 파일을 기준으로 영/중/일 누락 키를 탐지하는 CI 검증을 구축해, 번역 누락이 PR 단계에서 차단되도록 했습니다.

## Projects

### 거부기린

- Zustand store를 카메라, 자세, 알림 도메인으로 분리하고 persist와 선택적 구독을 적용해 빈번한 자세 상태 업데이트의 렌더링 부담을 줄였습니다.
- 웹캠 기반 자세 추론을 always-on-top 위젯과 조건 기반 시스템 알림으로 연결해, 작업 흐름을 끊지 않는 실시간 자세 교정 UX를 구현했습니다.
- React.lazy와 Vite manualChunks로 초기 번들 크기를 1.79MB에서 0.63MB로 줄여 약 65% 감소시켰습니다.

### 대피로 디자인 시스템

- Compound Component와 Context 기반 API로 반복되는 레이아웃 변형 요구를 표준화해, 대응 시간을 1-2시간에서 5-10분으로 줄였습니다.
- ESM/CJS 듀얼 빌드와 타입 정의 자동 생성을 구성해 Next.js, Vite, Webpack 환경에서 사용할 수 있는 React 컴포넌트 라이브러리 배포 구조를 만들었습니다.
- Vitest와 Storybook Test Runner 검증을 CI에 연결해 컴포넌트별 20개 이상 케이스와 80% 이상 커버리지를 유지했습니다.

### 수상한 녀석들

- AuthGuard와 `useAuth` 기반 진입 전 인증 검사로 화면 깜빡임을 줄이고, 미인증 사용자를 로그인 모달과 리다이렉트 흐름으로 연결했습니다.
- `@use-funnel/browser`와 Zod 단계별 검증으로 뒤로가기/새로고침에도 상태가 유지되는 멀티스텝 폼 흐름을 구현했습니다.

## Skills

- React, Next.js, TypeScript, Electron
- Zustand, Recoil, TanStack Query, React Router Loader
- Storybook, Vitest, Vite, tsup, Vanilla Extract, GitHub Actions
