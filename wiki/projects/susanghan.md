# 수상한 녀석들

## Identity

- Project: 수상한 녀석들
- Period: 2025.07 - 2025.09
- Link: https://github.com/choihooo/susanghan-fe
- Related raw source: `raw/projects/susanghan.md`
- Related experience: 사이드 프로젝트

## One-line Summary

광고 공모전 출품작 분석 AI 서비스에서 인증, 멀티스텝 폼, 브랜딩 전환, 폼 상태 구조를 설계했다.

## Context

- Problem: 인증 확인 타이밍, 멀티스텝 폼 상태 유실, 섹션별 브랜딩 전환, 커지는 폼 상태로 인한 리렌더링 문제가 있었다.
- Users or stakeholders: 광고 공모전 출품자와 운영팀
- Constraints: 사용자는 지원서 작성 흐름에서 뒤로가기, 새로고침, 모바일 리사이즈 같은 상황을 자주 만날 수 있었다.

## My Role

- Role: 프론트엔드 개발
- Ownership: 인증 UX, 멀티스텝 폼 상태 유지, 헤더 테마 전환, 지원서 상태 구조
- Collaborators: 프로젝트 팀
- Decisions I made: 진입 전 인증 검사, URL 동기화 기반 단계형 폼, Zod 단계별 검증, 상태 단위 분리

## Work Done

- Workstream: 인증 UX
  - Action: AuthGuard와 `useAuth`로 라우트 진입 전 인증을 확인하고 미인증 사용자를 로그인 모달/리다이렉트로 연결했다.
  - Reason: 화면 진입 후 인증을 확인하면 페이지가 튀는 문제가 있었다.
  - Tool or method: Next.js, custom hook
  - Tradeoff: 라우팅 흐름이 복잡해지지만 사용자에게 보이는 깜빡임이 줄어든다.
- Workstream: 단계형 폼
  - Action: `@use-funnel/browser`로 단계 상태를 URL과 동기화하고 Zod로 단계별 검증을 적용했다.
  - Reason: 뒤로가기나 새로고침에서 작성 상태가 사라지면 제출 전환에 악영향을 준다.
  - Tool or method: URL state, Zod
  - Tradeoff: URL 상태 설계와 검증 스키마 관리 비용이 생긴다.
- Workstream: 폼 상태 최적화
  - Action: 지원서 상태를 `useSubmitStore`로 중앙 관리하되 DCA/YCC 단위로 나눴다.
  - Reason: 폼 상태가 커질수록 불필요한 리렌더링이 늘어났다.
  - Tool or method: Zustand-style store
  - Tradeoff: 상태 단위가 많아지면 구조 규칙을 문서화해야 한다.

## Result

- Metric: 약 100명 대상 운영, 62명에게 직관적/작성하기 편하다는 정성 피드백 확보
- Qualitative outcome: 지원서 작성 흐름에서 상태 유실과 화면 튐을 줄이고, 섹션별 브랜딩 경험을 안정화했다.
- Evidence: GitHub, raw source
- Follow-up: 제출 완료율, 이탈률, 피드백 원문 확보 필요

## Reusable Output Material

### Resume Bullets

- AuthGuard와 `useAuth` 기반 진입 전 인증 검사로 화면 깜빡임을 줄이고, 미인증 사용자를 로그인 모달과 리다이렉트 흐름으로 연결했다.
- `@use-funnel/browser`와 Zod 단계별 검증으로 뒤로가기/새로고침에도 상태가 유지되는 멀티스텝 폼 흐름을 구현했다.
- 약 100명 대상 운영에서 62명에게 사용 흐름이 직관적이고 작성하기 편하다는 정성 피드백을 확보했다.

### Portfolio Case Study

- Hook: 작성형 서비스에서는 기능보다 흐름이 끊기지 않는 것이 전환 경험의 핵심이었다.
- Problem: 인증, 뒤로가기, 새로고침, 리사이즈가 모두 사용 흐름을 깨뜨릴 수 있었다.
- Approach: 진입 전 인증, URL 동기화 폼, 단계별 검증, 상태 단위 분리로 흐름을 안정화했다.
- Result: 62명 정성 피드백으로 사용 흐름의 직관성을 확인했다.
- Proof: GitHub, 운영 피드백

### Interview Stories

- 멀티스텝 폼 상태를 URL과 동기화한 이유
- 인증 확인 타이밍을 라우트 진입 전으로 옮긴 판단
- 정성 피드백을 UX 개선 근거로 해석한 방식

## Gaps

- Missing metric: 제출 완료율, 이탈률
- Missing link: 배포 서비스
- Missing image: 폼 플로우 화면
- Unclear role boundary: AI 분석 기능 구현 범위
