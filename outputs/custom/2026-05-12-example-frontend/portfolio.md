# Tailored Portfolio

## Narrative

이 JD는 React/TypeScript 개발 역량만이 아니라 상태관리, 성능, 코드 품질, 사용자 흐름, 디자인 시스템 경험을 함께 요구한다. 따라서 포트폴리오는 화면 구현보다 구조를 바꿔 반복 비용과 사용자 불편을 줄인 사례를 앞에 둔다.

## Case Study 1. 아이겐코리아 어드민 안정화

- Problem: TypeScript v3, 하드코딩된 센터 데이터, 다국어 키 누락 가능성이 운영 안정성을 낮추고 있었다.
- Decision: 한 번에 큰 리팩토링을 하기보다 타입 설정, 데이터 출처, CI 검증 지점을 나눠 단계적으로 개선했다.
- Action: TypeScript v5 전환, 50개 이상 `any` 명시 타입화, 38개 파일 하드코딩 제거, i18n 누락 검증 CI 구축
- Result: 빌드 시간 약 19% 단축, 새 센터가 코드 수정 없이 반영되는 구조 확보, 번역 누락을 PR 단계에서 차단

## Case Study 2. 거부기린 실시간 상태관리와 UX

- Problem: 자세 상태는 자주 바뀌지만, 잦은 알림은 사용자의 작업 흐름을 방해한다.
- Decision: Zustand를 도메인별 store로 나누고, always-on-top 위젯을 중심 피드백 채널로 선택했다.
- Action: 카메라/자세/알림 store 분리, persist와 선택적 구독 적용, 조건 기반 시스템 알림 구현, React.lazy와 manualChunks 적용
- Result: 작업 흐름을 유지하는 자세 교정 UX 구현, 초기 번들 65% 감소, 프로젝트 대상 수상

## Case Study 3. 대피로 디자인 시스템

- Problem: UI 변형 요구가 반복되어 구현 시간이 계속 발생했다.
- Decision: 컴포넌트 수를 늘리기보다 조합 가능한 API와 검증 가능한 배포 흐름을 만든다.
- Action: Compound Component + Context API, Connect/Recipe 구조, ESM/CJS 듀얼 빌드, Vitest/Storybook Test Runner CI
- Result: 요구사항 대응 시간 90% 단축, 컴포넌트별 20개 이상 케이스와 80% 이상 커버리지 유지

## Proof

- TypeScript migration blogs: https://hochoi.tistory.com/23, https://hochoi.tistory.com/25
- Geobugirin GitHub: https://github.com/kusitms-bugi/FE
- Daepiro design system GitHub: https://github.com/Team-NumberOne/daepiro-design-system
- Susanghan GitHub: https://github.com/choihooo/susanghan-fe
