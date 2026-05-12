# Story Bank

이 페이지는 면접 답변과 포트폴리오 케이스 스터디에 재사용할 이야기 단위만 모은다. 단순 프로젝트 설명은 `wiki/projects/`에 두고, 여기에는 갈등, 판단, 행동, 결과가 있는 이야기만 둔다.

## STAR Stories

### TypeScript v3 to v5 Migration

- Related page: `wiki/experiences/eigene-korea.md`
- Situation: 어드민 서비스가 TypeScript v3에 머물러 최신 라이브러리 적용 시 충돌이 발생했고 strict 모드가 꺼져 있었다.
- Task: 타입 안정성을 높이면서 기존 서비스 빌드와 운영 흐름을 깨지 않게 마이그레이션해야 했다.
- Action: `noImplicitAny`, `strictNullChecks`, 외부 라이브러리 호환성 점검, `strict: true` 순으로 단계 전환하고 50개 이상의 `any`를 명시 타입으로 바꿨다.
- Result: TypeScript v5 전환과 strict 기반 타입 안정성을 확보했고, 빌드 시간이 평균 246.22초에서 199.51초로 줄었다.
- Metric or proof: 빌드 시간 약 19% 단축, 블로그 링크 2개
- Best used for: 타입 안정성, 기술 부채 개선, 운영 코드 개선
- Avoid using when: JD가 순수 UI/그래픽 중심이고 타입 안정성 강조가 약할 때

### i18n Missing Key Automation

- Related page: `wiki/experiences/eigene-korea.md`
- Situation: 다국어 서비스에서 특정 언어 번역 키가 누락되면 운영 환경에 키 문자열이 그대로 노출될 수 있었다.
- Task: 개발자가 수동으로 파일을 확인하지 않아도 PR 단계에서 누락을 발견해야 했다.
- Action: 한국어 JSON을 기준으로 영/중/일 키 차이를 계산하고 누락 목록을 언어별로 출력하는 Node.js 스크립트를 만든 뒤 CI 실패 조건으로 연결했다.
- Result: 번역 누락이 QA나 운영 단계가 아니라 PR 단계에서 차단되는 구조를 만들었다.
- Metric or proof: CI fail flow, raw source
- Best used for: 품질 자동화, 운영 리스크 차단
- Avoid using when: 정량 성과만 요구하는 문서에서는 보조 사례로 사용

### Hardcoded Center Data to API State

- Related page: `wiki/experiences/eigene-korea.md`
- Situation: 30개 이상의 센터 정보가 프론트엔드 코드에 하드코딩되어 새 센터가 추가될 때마다 코드 수정과 배포가 필요했다.
- Task: 백엔드 데이터를 단일 출처로 두고 프론트엔드가 자동 반영되도록 구조를 바꿔야 했다.
- Action: 센터 목록을 API 기반 동적 로딩으로 전환하고, Recoil atom을 raw 데이터 저장소로 두며 selector를 화면별 가공 레이어로 나눴다. LocalStorage effect로 새로고침 이후 재호출도 줄였다.
- Result: 38개 파일의 하드코딩 참조를 제거했고, 새 센터가 코드 수정 없이 반영되는 구조가 됐다.
- Metric or proof: 38개 파일 리팩토링
- Best used for: 상태관리 설계, 운영 데이터 구조화
- Avoid using when: Recoil 경험보다 최신 상태관리만 강조해야 하는 JD

### Zustand for Real-time Desktop State

- Related page: `wiki/projects/geobugirin.md`
- Situation: Electron 기반 자세 교정 앱은 카메라, 자세, 알림 상태가 동시에 바뀌고 MediaPipe 분석으로 빈번한 업데이트가 발생했다.
- Task: 상태가 빠르게 바뀌어도 위젯과 메인 윈도우가 부드럽게 동작해야 했다.
- Action: Redux와 Context보다 단순한 Zustand를 선택하고 카메라, 자세, 알림 설정을 도메인별 store로 분리했다. persist와 localStorage 동기화, 선택적 구독을 적용했다.
- Result: 도메인별 독립 수정이 가능해졌고 실시간 상태 업데이트의 렌더링 부담을 줄였다.
- Metric or proof: 프로젝트 구조도, 포트폴리오 case study
- Best used for: 상태관리 기술 판단, Electron, 실시간 UI
- Avoid using when: 서버 상태 관리나 백엔드 설계를 묻는 질문

### Always-on-top Posture UX

- Related page: `wiki/projects/geobugirin.md`
- Situation: 자세 교정 앱은 자세 이상을 즉시 알려야 하지만 팝업 알림이 잦으면 작업 흐름을 방해한다.
- Task: 사용자가 작업을 계속하면서도 자세 이상을 인지할 수 있는 구조가 필요했다.
- Action: 인터럽트 팝업 중심이 아니라 always-on-top 위젯으로 상시 피드백을 제공하고, 일정 시간 이상 자세가 무너진 경우에만 시스템 알림이 발생하도록 했다.
- Result: 작업 흐름을 유지하면서 자세 교정을 유도하는 UX를 만들었다.
- Metric or proof: 포트폴리오 화면, 거부기린 대상 수상
- Best used for: 사용자 중심 UX 판단, 제품 엔지니어링
- Avoid using when: 순수 성능/인프라 중심 JD

### Bundle Size Reduction

- Related page: `wiki/projects/geobugirin.md`
- Situation: 초기 번들 크기가 1.79MB로 커서 첫 진입 시 모든 리소스를 한 번에 로드했다.
- Task: 사용자가 기다리는 시간을 줄이기 위해 초기 경로에 필요한 코드만 먼저 로드해야 했다.
- Action: React.lazy와 Vite manualChunks를 적용해 주요 기능을 사용 시점에 로드하고 라이브러리/기능 단위로 chunk를 나눴다.
- Result: 초기 번들 크기가 0.63MB로 줄어 약 65% 감소했다.
- Metric or proof: 1.79MB to 0.63MB
- Best used for: 프론트엔드 성능 최적화
- Avoid using when: 번들 크기 외 사용자 성과 지표가 반드시 필요한 문서

### Design System API

- Related page: `wiki/projects/daepiro-design-system.md`
- Situation: 제품 요구에 따라 레이아웃 변형이 자주 생겼고 매번 구현 비용이 반복됐다.
- Task: 변형을 감당할 수 있는 컴포넌트 API와 배포 가능한 라이브러리 구조가 필요했다.
- Action: Compound Component와 Context 기반 API로 조합 방식을 열고, Connect/Recipe 아키텍처로 스타일/로직/구조를 분리했다. tsup, Vanilla Extract, Vitest, Storybook Test Runner, GitHub Actions를 묶어 빌드와 검증을 자동화했다.
- Result: 요구사항 대응 시간이 1-2시간에서 5-10분으로 줄었고, 컴포넌트별 20개 이상 케이스와 80% 이상 커버리지를 유지했다.
- Metric or proof: 90% 대응 시간 단축, 80%+ coverage
- Best used for: 디자인 시스템, 프론트엔드 플랫폼, 팀 생산성
- Avoid using when: 서비스 운영 지표 중심 JD

### Multi-step Form State

- Related page: `wiki/projects/susanghan.md`
- Situation: 지원서 작성형 서비스에서 뒤로가기나 새로고침 시 상태가 유실되면 작성 흐름이 끊길 수 있었다.
- Task: 사용자가 브라우저 기본 동작을 해도 단계와 입력 흐름을 유지해야 했다.
- Action: `@use-funnel/browser`로 단계 상태를 URL과 동기화하고 Zod로 단계별 검증을 적용했다.
- Result: 상태 유실 위험을 줄였고 약 100명 대상 운영에서 62명에게 직관적/작성하기 편하다는 정성 피드백을 받았다.
- Metric or proof: 62명 정성 피드백
- Best used for: 폼 UX, 제품 흐름 설계
- Avoid using when: 정량 전환율만 요구하는 문서

## Story Inventory

### Problem Solving

- TypeScript v3 to v5 Migration
- Hardcoded Center Data to API State
- Bundle Size Reduction

### Collaboration

- Always-on-top Posture UX
- Design System API

### Leadership or Ownership

- Design System API
- Zustand for Real-time Desktop State

### Technical Judgment

- Zustand for Real-time Desktop State
- i18n Missing Key Automation
- Multi-step Form State

### Failure or Recovery

- TypeScript v3 to v5 Migration
- Multi-step Form State

## Story Quality Checklist

- 상황이 한 문장으로 이해되는가
- 내가 맡은 역할이 분명한가
- 선택지와 판단 근거가 있는가
- 행동이 구체적인가
- 결과가 사실 또는 수치로 닫히는가
- 이력서 bullet, 포트폴리오 본문, 면접 답변으로 각각 변환 가능한가
