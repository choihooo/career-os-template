# Positioning

이 페이지는 산출물의 톤과 선택 기준을 정한다. 개별 사실을 길게 복사하지 말고, 어떤 사실을 어떤 메시지로 묶을지 정리한다.

## Main Narrative

- 핵심 내러티브: 사용자 경험을 해치지 않으면서 운영 가능한 구조를 만드는 React/TypeScript 프론트엔드 엔지니어
- 이 내러티브가 설득력 있는 이유: TypeScript 마이그레이션, i18n CI, API 기반 상태 전환, Zustand store 분리, 번들 최적화, 디자인 시스템 설계처럼 사용 흐름과 유지보수성을 함께 다룬 사례가 반복된다.
- 이 내러티브가 약해지는 경우: 대규모 사용자 지표, 매출 임팩트, 장기 운영 지표가 필요한 JD에서는 현재 증거가 부족하다.

## Target Roles

- Role 1: Frontend Engineer
  - 필요한 증거: React/TypeScript 실무 경험, 상태관리, 성능 최적화, 운영 품질 개선
  - 강조할 프로젝트: 아이겐코리아, 거부기린, 수상한 녀석들
  - 강조할 문장 톤: 문제를 발견하고 코드 구조와 UX 흐름으로 해결한 구체적 사례 중심
- Role 2: Frontend Platform or Design System Engineer
  - 필요한 증거: 컴포넌트 API 설계, 빌드/테스트/배포 파이프라인, 문서화, 호환성
  - 강조할 프로젝트: 대피로 디자인 시스템, 아이겐코리아 i18n 자동화
  - 강조할 문장 톤: 반복 비용을 줄이는 구조화와 검증 자동화 중심
- Role 3: Product Engineer
  - 필요한 증거: 사용자 흐름 개선, 정성 피드백, 문제-판단-결과 설명
  - 강조할 프로젝트: 거부기린, 수상한 녀석들
  - 강조할 문장 톤: 기술 선택이 사용자 경험에 어떻게 연결됐는지 설명

## Repeated Strengths

- Strength: 운영 안정성 개선
  - Definition: 장애나 운영 리스크가 사용자에게 도달하기 전에 타입, CI, 데이터 구조로 차단한다.
  - Evidence pages: `wiki/experiences/eigene-korea.md`
  - Resume angle: TypeScript v5 전환, i18n 누락 검증 CI, API 기반 데이터 전환
  - Portfolio angle: 기술 부채를 단계적으로 낮추고 배포 전 검증 지점을 만든 사례
  - Interview story: TypeScript 마이그레이션, i18n 자동화
- Strength: 상태관리와 데이터 흐름 설계
  - Definition: 변경이 잦은 UI 상태를 도메인별로 나누고 필요한 곳에만 전달한다.
  - Evidence pages: `wiki/projects/geobugirin.md`, `wiki/experiences/eigene-korea.md`
  - Resume angle: Zustand 도메인 store, Recoil atom/selector, URL 동기화 폼
  - Portfolio angle: 기술 선택 기준과 tradeoff 설명
  - Interview story: Zustand 선택, 센터 API 전환
- Strength: 사용자 흐름 중심 UX 개선
  - Definition: 인증, 알림, 폼, 로딩처럼 사용자가 실제로 막히는 지점을 먼저 줄인다.
  - Evidence pages: `wiki/projects/geobugirin.md`, `wiki/projects/susanghan.md`
  - Resume angle: always-on-top 위젯, 진입 전 인증 검사, 멀티스텝 폼 상태 유지
  - Portfolio angle: 문제 상황과 UX 선택의 이유를 중심으로 설명
  - Interview story: 거부기린 알림 UX, 수상한 녀석들 폼 상태 유지
- Strength: 반복 개발 비용 감소
  - Definition: 자주 바뀌는 요구를 컴포넌트 API, 테스트, 빌드 파이프라인으로 흡수한다.
  - Evidence pages: `wiki/projects/daepiro-design-system.md`
  - Resume angle: 요구사항 대응 시간 90% 단축, ESM/CJS 듀얼 빌드, 테스트 커버리지 80%+
  - Portfolio angle: 디자인 시스템이 왜 필요한지 API 설계 기준으로 설명
  - Interview story: Compound Component 설계

## Differentiators

- 차별점 1:
  - 평범한 표현: React와 TypeScript를 사용할 수 있습니다.
  - 더 구체적인 표현: TypeScript 마이그레이션, 상태관리 구조화, 빌드/테스트 자동화로 운영 가능한 프론트엔드 코드를 만든다.
  - 근거: 아이겐코리아, 거부기린, 대피로
- 차별점 2:
  - 평범한 표현: 사용자 경험을 개선했습니다.
  - 더 구체적인 표현: 인증 타이밍, 알림 방식, 폼 상태 유지, 초기 로딩처럼 사용자가 직접 체감하는 흐름을 기술 구조로 개선했다.
  - 근거: 거부기린, 수상한 녀석들
- 차별점 3:
  - 평범한 표현: 협업을 잘합니다.
  - 더 구체적인 표현: 반복되는 요구를 API와 컴포넌트 구조로 흡수해 팀의 구현 비용을 줄인다.
  - 근거: 대피로 디자인 시스템

## Claims to Avoid

- 아직 근거가 부족한 주장: 대규모 트래픽 최적화, 매출 성장 기여, 플랫폼 전체 리딩
- 너무 넓거나 추상적인 주장: 풀스택 전반 역량, AI 서비스 전반 설계, 비즈니스 전략 수립
- 회사별 맞춤에서만 써야 하는 주장: 재난/헬스케어 도메인 적합성, 디자인 시스템 전문성, 운영 어드민 전문성
