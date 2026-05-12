# 거부기린

## Identity

- Project: 거부기린
- Period: 2025.10.04 - 2025.12.07
- Links: https://github.com/kusitms-bugi/FE, https://choihooo.github.io/bugi-download/, https://howu.vercel.app/blog/bugi-electron
- Related raw source: `raw/projects/geobugirin.md`
- Related award: 한국대학생IT경영학회 32기 밋업 프로젝트 대상

## One-line Summary

Electron 기반 멀티 윈도우 데스크톱 자세 교정 앱으로, 웹캠 자세 분석을 always-on-top 위젯과 조건 기반 알림으로 연결했다.

## Context

- Problem: 장시간 작업 중 자세가 무너져도 사용자가 즉시 인지하기 어렵고, 팝업 알림은 작업 흐름을 끊을 수 있었다.
- Users or stakeholders: 장시간 PC를 사용하는 사용자, 팀 프로젝트 심사자
- Constraints: 영상 데이터는 서버 전송 없이 디바이스 내에서 처리해야 했고, 자세 상태가 자주 바뀌어도 UI가 부드럽게 유지되어야 했다.

## My Role

- Role: 프론트엔드 리드
- Ownership: Electron/React UI, 자세 상태 흐름, Zustand store 구조, 번들 최적화, 인증 진입 흐름
- Collaborators: 기획 2명, 디자이너 2명, 프론트엔드 2명, 백엔드 1명
- Decisions I made: Zustand 선택, 도메인별 store 분리, always-on-top 위젯 중심 UX, 코드 스플리팅 적용

## Work Done

- Workstream: 실시간 상태관리
  - Action: 카메라, 자세, 알림 설정을 Zustand 도메인 store로 분리하고 persist/localStorage 동기화를 적용했다.
  - Reason: MediaPipe 기반 자세 분석이 초당 30회 이상 상태를 갱신할 수 있어 선택적 구독과 낮은 결합도가 필요했다.
  - Tool or method: Zustand, localStorage event, selective subscription
  - Tradeoff: Redux처럼 엄격한 구조보다 단순성과 구현 속도를 우선했다.
- Workstream: 데스크톱 UX
  - Action: always-on-top 위젯과 지속 조건 기반 시스템 알림을 구현했다.
  - Reason: 자세 교정은 즉시 인지가 필요하지만 잦은 팝업은 작업 몰입을 방해한다.
  - Tool or method: Electron multi-window, system notification
  - Tradeoff: 위젯이 항상 보이는 만큼 화면 점유를 최소화해야 했다.
- Workstream: 성능 최적화
  - Action: React.lazy와 Vite manualChunks로 초기 로딩 코드를 분리했다.
  - Reason: 초기 번들 1.79MB가 첫 진입 대기 시간을 만들었다.
  - Tool or method: Vite, React lazy loading
  - Tradeoff: chunk 분리 기준을 잘못 잡으면 이후 화면 전환이 느려질 수 있어 초기 경로 중심으로 분리했다.

## Result

- Metric: 초기 번들 1.79MB에서 0.63MB로 약 65% 감소
- Qualitative outcome: 사용자가 작업 흐름을 유지하면서 자세 이상을 인지하고 교정할 수 있는 데스크톱 경험 구현
- Evidence: 다운로드 페이지, GitHub, 블로그, 포트폴리오 이미지
- Follow-up: 실제 사용자 수, 자세 판정 정확도, 알림 효과 지표 확보 필요

## Reusable Output Material

### Resume Bullets

- 웹캠 기반 자세 추론을 always-on-top 위젯과 조건 기반 시스템 알림으로 연결해, 작업 흐름을 끊지 않는 실시간 자세 교정 UX를 구현했다.
- React.lazy와 Vite manualChunks로 초기 번들 크기를 1.79MB에서 0.63MB로 줄여 약 65% 감소시켰다.
- Zustand store를 카메라, 자세, 알림 도메인으로 분리하고 persist와 선택적 구독을 적용해 빈번한 자세 상태 업데이트의 렌더링 부담을 줄였다.

### Portfolio Case Study

- Hook: 자세 교정 앱에서 중요한 것은 감지 정확도뿐 아니라 사용자가 작업을 멈추지 않고 피드백을 받을 수 있는 구조였다.
- Problem: 팝업 중심 알림은 교정에는 빠르지만 작업 흐름을 끊고 피로도를 높인다.
- Approach: always-on-top 위젯과 조건 기반 알림을 조합하고, 상태관리와 번들 최적화를 함께 설계했다.
- Result: 초기 번들 65% 감소, 실시간 자세 피드백 UX 구현, 프로젝트 대상 수상
- Proof: GitHub, 다운로드 페이지, 수상 기사

### Interview Stories

- Zustand를 선택한 판단 기준
- always-on-top 위젯으로 UX 방향을 바꾼 이유
- 번들 최적화에서 초기 경로와 지연 로딩 기준을 나눈 과정

## Gaps

- Missing metric: 실제 사용자 수, 자세 판정 정확도
- Missing link: 최종 서비스 운영 지표
- Missing image: 위젯 상호작용 GIF
- Unclear role boundary: 자세 판단 로직 구현 범위와 공동 프론트엔드 담당자와의 분담
