# Resume Bullets

이 페이지는 최종 이력서에 바로 옮길 수 있는 bullet 후보를 모은다. 각 문장은 반드시 근거 페이지와 연결되어야 한다.

## Reusable Bullets

### Impact Bullets

- TypeScript v3 기반 어드민을 v5와 strict 설정으로 단계 전환하고 50개 이상의 `any`를 명시 타입으로 바꿔, 빌드 시간을 약 19% 줄였다.
  - Source: `wiki/experiences/eigene-korea.md`
  - Strength: 운영 안정성 개선
  - Target role: Frontend Engineer
  - Evidence level: high
  - Output fit: resume-v1 | resume-v2 | portfolio-v1 | custom-only
- React.lazy와 Vite manualChunks로 초기 번들 크기를 1.79MB에서 0.63MB로 줄여 약 65% 감소시켰다.
  - Source: `wiki/projects/geobugirin.md`
  - Strength: 성능 최적화
  - Target role: Frontend Engineer
  - Evidence level: high
  - Output fit: resume-v1 | resume-v2 | portfolio-v1 | custom-only
- Compound Component와 Context 기반 API로 반복되는 레이아웃 변형 요구를 표준화해, 대응 시간을 1-2시간에서 5-10분으로 줄였다.
  - Source: `wiki/projects/daepiro-design-system.md`
  - Strength: 반복 개발 비용 감소
  - Target role: Frontend Platform Engineer
  - Evidence level: high
  - Output fit: resume-v2 | portfolio-v2 | custom-only
- 30개 이상 센터 정보를 API 기반 동적 로딩으로 전환하고 38개 파일의 하드코딩 참조를 제거해, 새 센터가 코드 수정 없이 반영되는 구조를 만들었다.
  - Source: `wiki/experiences/eigene-korea.md`
  - Strength: 데이터 흐름 개선
  - Target role: Frontend Engineer
  - Evidence level: high
  - Output fit: resume-v1 | portfolio-v1 | custom-only
- 약 100명 대상 운영에서 62명에게 사용 흐름이 직관적이고 작성하기 편하다는 정성 피드백을 확보했다.
  - Source: `wiki/projects/susanghan.md`
  - Strength: 사용자 흐름 개선
  - Target role: Product Engineer
  - Evidence level: medium
  - Output fit: resume-v2 | portfolio-v2 | custom-only

### Product or Business Bullets

- 웹캠 기반 자세 추론을 always-on-top 위젯과 조건 기반 시스템 알림으로 연결해, 작업 흐름을 끊지 않는 실시간 자세 교정 UX를 구현했다.
  - Source: `wiki/projects/geobugirin.md`
  - Strength: 사용자 흐름 중심 UX
  - Target role: Product Engineer | Frontend Engineer
  - Evidence level: high
  - Output fit: resume-v1 | portfolio-v1 | portfolio-v2 | custom-only
- AuthGuard와 `useAuth` 기반 진입 전 인증 검사로 화면 깜빡임을 줄이고, 미인증 사용자를 로그인 모달과 리다이렉트 흐름으로 연결했다.
  - Source: `wiki/projects/susanghan.md`
  - Strength: 인증 UX 개선
  - Target role: Frontend Engineer
  - Evidence level: medium
  - Output fit: resume-v1 | custom-only
- `@use-funnel/browser`와 Zod 단계별 검증으로 뒤로가기/새로고침에도 상태가 유지되는 멀티스텝 폼 흐름을 구현했다.
  - Source: `wiki/projects/susanghan.md`
  - Strength: 폼 UX 개선
  - Target role: Product Engineer | Frontend Engineer
  - Evidence level: medium
  - Output fit: resume-v2 | portfolio-v2 | custom-only
- 목표 달성률과 YoY 지표를 센터별/전체 통계에 추가하고 Recharts 복합 차트와 엑셀 다운로드를 연동해 성과 분석 흐름을 보강했다.
  - Source: `wiki/experiences/eigene-korea.md`
  - Strength: 데이터 시각화
  - Target role: Frontend Engineer
  - Evidence level: medium
  - Output fit: resume-v1 | custom-only

### Engineering or Technical Bullets

- 한국어 번역 파일을 기준으로 영/중/일 누락 키를 탐지하는 CI 검증을 구축해, 번역 누락이 PR 단계에서 차단되도록 했다.
  - Source: `wiki/experiences/eigene-korea.md`
  - Strength: 자동화
  - Target role: Frontend Engineer
  - Evidence level: medium
  - Output fit: resume-v1 | portfolio-v1 | custom-only
- Zustand store를 카메라, 자세, 알림 도메인으로 분리하고 persist와 선택적 구독을 적용해 빈번한 자세 상태 업데이트의 렌더링 부담을 줄였다.
  - Source: `wiki/projects/geobugirin.md`
  - Strength: 상태관리 설계
  - Target role: Frontend Engineer
  - Evidence level: high
  - Output fit: resume-v1 | resume-v2 | portfolio-v1 | portfolio-v2
- ESM/CJS 듀얼 빌드와 타입 정의 자동 생성을 구성해 Next.js, Vite, Webpack 환경에서 사용할 수 있는 React 컴포넌트 라이브러리 배포 구조를 만들었다.
  - Source: `wiki/projects/daepiro-design-system.md`
  - Strength: 라이브러리 배포
  - Target role: Frontend Platform Engineer
  - Evidence level: high
  - Output fit: resume-v2 | portfolio-v2 | custom-only
- Vitest와 Storybook Test Runner 검증을 CI에 연결해 컴포넌트별 20개 이상 케이스와 80% 이상 커버리지를 유지했다.
  - Source: `wiki/projects/daepiro-design-system.md`
  - Strength: 검증 자동화
  - Target role: Frontend Platform Engineer
  - Evidence level: high
  - Output fit: resume-v2 | custom-only
- TanStack Query 커스텀 훅으로 API 접근을 모듈화하고 캐시 무효화/재검증 전략을 적용해 화면 전환 중 데이터 동기화 흐름을 안정화했다.
  - Source: `wiki/projects/geobugirin.md`
  - Strength: 데이터 동기화
  - Target role: Frontend Engineer
  - Evidence level: medium
  - Output fit: resume-v1 | custom-only
- Recoil atom을 서버 응답 raw 데이터의 단일 출처로 두고 selector를 계산 레이어로 분리해 센터 데이터 조회와 가공 책임을 나눴다.
  - Source: `wiki/experiences/eigene-korea.md`
  - Strength: 상태관리 설계
  - Target role: Frontend Engineer
  - Evidence level: medium
  - Output fit: portfolio-v1 | custom-only

### Collaboration Bullets

- 유일한 프론트엔드 담당자로 개발실에 합류해 서비스 데모 페이지 개발, 클라이언트 QA 대응, 어드민 안정화 작업을 병행했다.
  - Source: `wiki/experiences/eigene-korea.md`
  - Strength: 오너십
  - Target role: Frontend Engineer
  - Evidence level: medium
  - Output fit: resume-v1 | custom-only
- 기획, 디자인, 백엔드와 협업하는 7인 팀에서 거부기린 프론트엔드 리드로 참여해 데스크톱 앱 UX와 상태 흐름을 설계했다.
  - Source: `wiki/projects/geobugirin.md`
  - Strength: 팀 프로젝트 리딩
  - Target role: Frontend Engineer
  - Evidence level: medium
  - Output fit: resume-v2 | portfolio-v1 | custom-only
- 백엔드 팀과 PoC를 수행해 긴급차량 주행 알림 서비스 아이디어의 구현 가능성을 검증하고 KT&G 아이디어톤 대상을 받았다.
  - Source: `wiki/awards/awards-2021-2025.md`
  - Strength: 협업과 검증
  - Target role: Product Engineer
  - Evidence level: medium
  - Output fit: custom-only

### Leadership or Ownership Bullets

- 한국대학생IT경영학회 32기 밋업 프로젝트에서 거부기린 프론트엔드 리드로 참여해 자세 판단 로직과 사용자 피드백 흐름을 구현하고 대상을 받았다.
  - Source: `wiki/awards/awards-2021-2025.md`
  - Strength: 프로젝트 오너십
  - Target role: Frontend Engineer
  - Evidence level: high
  - Output fit: resume-v1 | portfolio-v1 | custom-only
- 대피로 디자인 시스템에서 컴포넌트 API, 빌드 파이프라인, 테스트 자동화를 함께 설계해 제품팀의 반복 구현 비용을 줄였다.
  - Source: `wiki/projects/daepiro-design-system.md`
  - Strength: 구조화
  - Target role: Frontend Platform Engineer
  - Evidence level: high
  - Output fit: resume-v2 | portfolio-v2 | custom-only
- 2021 대학생 하계 논문 학술대회에서 제1저자로 거리 계산 알고리즘을 설계하고 구현해 금상을 받았다.
  - Source: `wiki/awards/awards-2021-2025.md`
  - Strength: 문제 해결
  - Target role: Frontend Engineer
  - Evidence level: high
  - Output fit: resume-v1 | custom-only

## Rewrite Rules

- 책임 나열보다 결과를 먼저 쓴다.
- 수치가 없으면 범위를 과장하지 않는다.
- "기여", "개선", "고도화"만으로 끝내지 않는다.
- 회사별 JD 표현을 그대로 넣기 전에 실제 경험과 맞는지 확인한다.
- 같은 동사로 bullet을 연속 시작하지 않는다.
