# 대피로 디자인 시스템 프로젝트 원천 메모

## Source

- Primary extracted source: `resume/index.html`
- Project: 대피로 디자인 시스템
- Period: 2025.08.12 - 진행중
- Links:
  - GitHub: https://github.com/Team-NumberOne/daepiro-design-system
  - Blog: https://howu.vercel.app/blog/daepiro-design-system-ux-ui-components

## Facts

- 대피로는 사용자 맞춤형 안전 재난 알림을 제공하는 서비스다.
- 디자인 시스템 라이브러리 개발을 맡았다.
- 레이아웃 변형 요구가 잦아 매번 구현 비용이 발생하던 문제를 Compound Component와 Context 기반 API로 표준화했다.
- 요구사항 대응 시간을 1-2시간에서 5-10분으로 줄여 약 90% 단축했다.
- 컴포넌트 구현이 스타일, 로직, 구조에 얽혀 변경 영향이 커지던 문제를 Connect/Recipe 아키텍처로 분리했다.
- Vitest 단위 테스트와 Storybook Test Runner 기반 자동 검증을 구성했다.
- 컴포넌트별 20개 이상 케이스와 80% 이상 커버리지를 유지했다.
- ESM/CJS 듀얼 빌드와 TypeScript 타입 정의 자동 생성으로 Next.js, Vite, Webpack 환경 호환성을 확보했다.
- Vanilla Extract, tsup, Biome, GitHub Actions 기반 린트/테스트/빌드/배포 파이프라인을 구성했다.

## Missing or Verify

- 실제 패키지 배포 URL 또는 npm registry 주소
- 사용 중인 서비스/팀 수
- 컴포넌트 목록과 대표 API 예시
