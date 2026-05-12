# 대피로 디자인 시스템

## Identity

- Project: 대피로 디자인 시스템
- Period: 2025.08.12 - 진행중
- Link: https://github.com/Team-NumberOne/daepiro-design-system
- Related raw source: `raw/projects/daepiro-design-system.md`
- Related experience: 사이드 프로젝트

## One-line Summary

재난 알림 서비스 대피로에서 반복되는 UI 변형 요구를 줄이기 위해 Compound Component 기반 디자인 시스템 라이브러리를 구축했다.

## Context

- Problem: 레이아웃 변형 요구가 잦아 매번 구현 비용이 발생했고, 컴포넌트 변경 영향이 스타일, 로직, 구조에 얽혀 있었다.
- Users or stakeholders: 대피로 제품 개발팀, 디자인 시스템 사용자
- Constraints: Next.js, Vite, Webpack 등 여러 런타임/번들러 환경에서 바로 사용할 수 있어야 했다.

## My Role

- Role: 프론트엔드 라이브러리 개발
- Ownership: 컴포넌트 API, 빌드 파이프라인, 테스트 자동화, Storybook 문서화
- Collaborators: 대피로 팀
- Decisions I made: Compound Component + Context API, Connect/Recipe 아키텍처, ESM/CJS 듀얼 빌드

## Work Done

- Workstream: 컴포넌트 API 설계
  - Action: 레이아웃 변형을 Compound Component와 Context 기반 API로 표준화했다.
  - Reason: props 조합이 늘어날수록 구현과 변경 비용이 커졌기 때문이다.
  - Tool or method: React Context, Compound Component
  - Tradeoff: 사용자가 구조를 명시적으로 조합해야 하지만 변형 확장성은 좋아진다.
- Workstream: 스타일/구조 분리
  - Action: Connect/Recipe 아키텍처로 스타일, 로직, 구조 관심사를 나눴다.
  - Reason: 변경 영향 범위를 줄이고 컴포넌트 유지보수성을 높이기 위해서다.
  - Tool or method: Vanilla Extract, recipe pattern
  - Tradeoff: 초기 설계 비용이 커지지만 반복 변경 비용이 줄어든다.
- Workstream: 배포 안정화
  - Action: tsup 기반 ESM/CJS 듀얼 빌드, 타입 정의 자동 생성, GitHub Actions 파이프라인을 구성했다.
  - Reason: 소비 프로젝트 환경이 달라도 즉시 사용할 수 있어야 했다.
  - Tool or method: tsup, TypeScript, Biome, Vitest, Storybook Test Runner
  - Tradeoff: 빌드 설정 복잡도가 늘어난다.

## Result

- Metric: 요구사항 대응 시간 1-2시간에서 5-10분으로 약 90% 단축
- Metric: 컴포넌트별 20개 이상 케이스, 테스트 커버리지 80% 이상 유지
- Qualitative outcome: 변경 영향이 작은 컴포넌트 구조와 자동 검증 가능한 배포 흐름 확보
- Evidence: GitHub, 기술 블로그
- Follow-up: 실제 패키지 사용처와 배포 URL 확보 필요

## Reusable Output Material

### Resume Bullets

- Compound Component와 Context 기반 API로 반복되는 레이아웃 변형 요구를 표준화해, 대응 시간을 1-2시간에서 5-10분으로 줄였다.
- ESM/CJS 듀얼 빌드와 타입 정의 자동 생성을 구성해 Next.js, Vite, Webpack 환경에서 사용할 수 있는 React 컴포넌트 라이브러리 배포 구조를 만들었다.
- Vitest와 Storybook Test Runner 검증을 CI에 연결해 컴포넌트별 20개 이상 케이스와 80% 이상 커버리지를 유지했다.

### Portfolio Case Study

- Hook: 디자인 시스템은 예쁜 컴포넌트 모음보다 변화 요구를 감당하는 API 설계가 중요했다.
- Problem: 변형이 생길 때마다 구현 비용이 반복되고 변경 영향이 커졌다.
- Approach: 조합 가능한 컴포넌트 API, 스타일 recipe, 듀얼 빌드와 테스트 자동화로 구조화했다.
- Result: 요구사항 대응 시간 90% 단축, 자동 검증 가능한 라이브러리 배포 흐름 확보
- Proof: GitHub, 블로그, 테스트/스토리북 자료

### Interview Stories

- Compound Component를 선택한 이유
- 라이브러리 배포 호환성을 ESM/CJS로 맞춘 경험
- 테스트와 Storybook을 문서가 아니라 검증 도구로 사용한 경험

## Gaps

- Missing metric: 실제 패키지 다운로드/사용 수
- Missing link: npm 또는 패키지 배포 URL
- Missing image: Storybook 캡처, 대표 컴포넌트 API
- Unclear role boundary: 팀 내 디자인/제품 의사결정 범위
