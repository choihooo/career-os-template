# General Resume v2

## Positioning

사용자 흐름을 해치지 않으면서 운영 가능한 구조를 만드는 프론트엔드 엔지니어입니다. React와 TypeScript를 중심으로 타입 안정성, 상태관리, 성능 최적화, 컴포넌트 API 설계를 다뤄 왔고, 기능 구현보다 “왜 이 구조가 유지보수와 사용자 경험에 유리한가”를 기준으로 판단합니다.

## Core Impact

- TypeScript v3 기반 어드민을 v5와 strict 설정으로 단계 전환하고 50개 이상의 `any`를 명시 타입으로 바꿔, 빌드 시간을 약 19% 줄였습니다.
- React.lazy와 Vite manualChunks로 Electron 앱 초기 번들 크기를 1.79MB에서 0.63MB로 줄여 약 65% 감소시켰습니다.
- Compound Component와 Context 기반 API로 반복되는 레이아웃 변형 요구를 표준화해, 대응 시간을 1-2시간에서 5-10분으로 줄였습니다.
- 30개 이상 센터 정보를 API 기반 동적 로딩으로 전환하고 38개 파일의 하드코딩 참조를 제거해, 새 센터가 코드 수정 없이 반영되는 구조를 만들었습니다.

## Focused Experience

### 아이겐코리아, Frontend Engineer Intern

- Period: 2025.03.04 - 2025.06.30
- Focus: 운영 어드민 안정화, 타입 안정성, 데이터 구조 개선, 검증 자동화

- 노후 TypeScript 버전과 느슨한 타입 설정을 단계적으로 전환해 운영 코드의 타입 안정성을 높였습니다.
- Recoil atom/selector로 API 기반 센터 데이터를 저장/가공하는 책임을 나누고, LocalStorage effect로 불필요한 재호출을 줄였습니다.
- 번역 누락이 운영 환경에 도달하지 않도록 한국어 기준 키 비교 스크립트를 만들고 CI 실패 조건으로 연결했습니다.

## Signature Projects

### 거부기린: 실시간 자세 교정 데스크톱 앱

- Focus: Electron, 실시간 상태관리, 데스크톱 UX, 번들 최적화

- 자세 교정 앱에서 중요한 문제를 “정확히 감지하는 것”뿐 아니라 “사용자의 작업 흐름을 끊지 않고 피드백하는 것”으로 정의했습니다.
- always-on-top 위젯과 조건 기반 알림을 조합해 상시 피드백과 최소 개입 사이의 균형을 잡았습니다.
- 초당 30회 이상 발생할 수 있는 자세 상태 업데이트를 처리하기 위해 Zustand를 도메인별 store로 나눴습니다.
- 초기 번들 65% 감소로 첫 진입 체감 성능을 개선했습니다.

### 대피로 디자인 시스템: 반복 요구를 흡수하는 컴포넌트 API

- Focus: React component library, design system, build pipeline, automated testing

- 반복되는 UI 변형을 매번 구현하는 대신, Compound Component와 Context 기반 API로 조합 가능한 구조를 설계했습니다.
- Connect/Recipe 아키텍처로 스타일, 로직, 구조의 변경 영향 범위를 줄였습니다.
- ESM/CJS 듀얼 빌드, 타입 정의 자동 생성, Vitest, Storybook Test Runner, GitHub Actions를 묶어 배포와 검증 흐름을 표준화했습니다.

### 수상한 녀석들: 작성 흐름이 끊기지 않는 폼 UX

- Focus: 인증 UX, 멀티스텝 폼, URL 상태 동기화

- 라우트 진입 후 인증을 확인해 화면이 튀는 문제를 진입 전 인증 검사로 바꿨습니다.
- 뒤로가기와 새로고침에서도 작성 상태가 유지되도록 단계 상태를 URL과 동기화하고 Zod로 단계별 검증을 적용했습니다.
- 약 100명 대상 운영에서 62명에게 사용 흐름이 직관적이고 작성하기 편하다는 정성 피드백을 확보했습니다.

## Skills and Tools

- Core: React, TypeScript, Next.js, Electron
- State: Zustand, Recoil, TanStack Query, URL state
- Product UX: authentication flow, multi-step form, notification UX, dashboard visualization
- Platform: Storybook, Vitest, tsup, Vanilla Extract, ESM/CJS build, GitHub Actions
- Avoided claims: 대규모 트래픽 운영, 매출 직접 기여, 백엔드/AI 모델 주도
