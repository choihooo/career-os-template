# 수상한 녀석들 프로젝트 원천 메모

## Source

- Primary extracted source: `resume/index.html`
- Project: 수상한 녀석들
- Period: 2025.07 - 2025.09
- GitHub: https://github.com/choihooo/susanghan-fe

## Facts

- 광고 공모전 출품작 분석 AI 서비스다.
- Next.js, TypeScript, Zod, MSW, Tailwind를 사용했다.
- 라우트 진입 후 인증을 확인해 화면이 튀는 문제를 AuthGuard와 `useAuth` 기반 진입 전 선검증으로 바꿨다.
- 미인증 시 로그인 모달과 리다이렉트 흐름으로 이탈을 줄이는 UX를 설계했다.
- 멀티스텝 폼에서 뒤로가기/새로고침 시 상태가 유실되는 문제를 `@use-funnel/browser` URL 동기화와 Zod 단계별 검증으로 해결했다.
- 홈 섹션 진입 트리거 기반 헤더 테마 자동 전환과 디바운스된 `useIsMobile`로 리사이즈 처리 비용을 줄였다.
- 지원서 폼 상태를 `useSubmitStore`로 중앙 관리하되 DCA/YCC 단위로 분리해 불필요한 리렌더링을 줄였다.
- 약 100여 명 대상 운영에서 62명으로부터 사용 흐름이 직관적이고 작성하기 편하다는 정성 피드백을 확보했다.

## Missing or Verify

- 62명 피드백 원문 또는 설문 형태
- 서비스 운영 기간과 실제 제출 완료율
- AI 분석 기능에서 맡은 범위
