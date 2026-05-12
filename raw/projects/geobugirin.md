# 거부기린 프로젝트 원천 메모

## Source

- Primary extracted source: `resume/index.html`, `portfolio/index.html`
- Project: 거부기린
- Period: 2025.10.04 - 2025.12.07
- Team: 기획 2명, 디자이너 2명, 프론트엔드 2명, 백엔드 1명
- Links:
  - GitHub: https://github.com/kusitms-bugi/FE
  - Download: https://choihooo.github.io/bugi-download/
  - Blog: https://howu.vercel.app/blog/bugi-electron
  - Service: https://www.bugi.co.kr/
  - Project blog: https://blog.bugi.co.kr/
  - Design system: https://design.bugi.co.kr/

## Facts

- Electron 기반 멀티 윈도우 데스크톱 자세 교정 앱이다.
- 웹캠으로 사용자의 자세를 실시간 분석하고, 위젯과 알림으로 즉시 피드백을 제공한다.
- 영상 데이터가 서버로 넘어가지 않고 디바이스 안에서 자세 판정되는 구조를 핵심으로 삼았다.
- MediaPipe Vision을 사용해 브라우저 환경에서 자세 키포인트를 추출했다.
- always-on-top 위젯과 조건 기반 시스템 알림으로 작업 흐름을 덜 방해하는 교정 UX를 구현했다.
- 초당 30회 이상 발생할 수 있는 자세 상태 업데이트를 처리하기 위해 Zustand를 선택했다.
- 카메라, 자세, 알림 설정을 도메인별 store로 분리했다.
- persist와 localStorage 동기화, 선택적 구독을 적용해 불필요한 리렌더링을 줄였다.
- React.lazy와 Vite manualChunks로 코드 스플리팅을 적용했다.
- 초기 번들 크기를 1.79MB에서 0.63MB로 줄여 약 65% 감소했다.
- React Router Loader 기반 진입 전 인증 검사와 리다이렉트로 로그인 여부 확인 시 화면 깜빡임을 줄였다.
- TanStack Query 커스텀 훅으로 API 접근을 모듈화하고 캐시 무효화/재검증 전략을 적용했다.
- 한국대학생IT경영학회 32기 밋업 프로젝트에서 대상을 받았다.

## Missing or Verify

- 실제 사용자 수, 다운로드 수, 세션 수
- 자세 판정 정확도 또는 성능 측정 지표
- 수상 증빙 링크와 프로젝트 심사 기준
