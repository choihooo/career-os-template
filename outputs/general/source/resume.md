# General Resume v1

## About Me

사용자 맥락과 팀의 효율을 함께 고려해 제품 UI, 상태 흐름, 검증 구조를 개선하는 React/TypeScript 엔지니어 샘플입니다. 실제 사용자는 이 파일을 자기 `wiki/` 지식 기준으로 다시 생성해야 합니다.

## Work Experience

### Frontend Engineer Intern @ Sample Company

- Period: 2025.03 - 2025.06
- Link: https://company.example
- Summary: B2B SaaS 운영 화면의 타입 안정성, 입력 검증, 관리자 업무 흐름을 개선했습니다.

#### 어드민 TypeScript 마이그레이션

- Tags: TypeScript, Zod, React, CI
- Summary: 노후화된 어드민 코드베이스를 최신 타입 체계와 검증 흐름에 맞춰 단계적으로 정리했습니다.
- 암묵적 any와 느슨한 응답 타입을 명시 타입과 검증 스키마로 전환했습니다.
- 입력 검증 스키마와 화면 상태 타입을 맞춰 QA 재현 이슈가 사용자 단계로 넘어가기 전에 차단했습니다.

#### 다국어 키 누락 감지 자동화

- Tags: Node.js, i18n, GitHub Actions
- Summary: 다국어 리소스 누락이 운영 화면에 노출되기 전에 PR 단계에서 발견되도록 자동화했습니다.
- 기준 언어 JSON과 대상 언어 JSON의 key set을 비교해 누락된 번역 키를 자동 추출하는 CI 검사를 구현했습니다.
  - PR 단계에서 누락 목록을 출력하고 실패 처리해 운영 배포 전 누락을 발견하도록 했습니다.
  - 언어별 JSON 구조 차이를 비교 기준으로 고정해 신규 화면 추가 때 같은 검사를 재사용할 수 있게 했습니다.
- Result: 운영 화면의 번역 key 노출 가능성 감소, PR 단계 누락 확인 흐름 자동화

## Projects

### Sample Dashboard

- Period: 2025.01 - 2025.02
- Link: https://github.com/your-id/project
- Summary: 운영자가 같은 조건을 다시 재현하고 공유할 수 있도록 필터와 서버 상태를 분리한 대시보드 프로젝트입니다.

#### URL 기반 필터와 서버 상태 분리

- Tags: React, TanStack Query, URL State
- Summary: 필터 조건, 서버 요청, 화면 표시 상태를 분리해 같은 리포트 조건을 링크로 재현할 수 있게 했습니다.
- URL query와 서버 상태를 분리해 특정 필터 조건을 공유 가능한 링크로 만드는 상태 구조를 구현했습니다.
  - 필터 초기화, 빈 결과, 로딩 중 상태를 구분해 현재 조건과 결과 상태를 명확히 보여줬습니다.
  - 차트와 표가 같은 조건을 참조하도록 query key와 화면 상태의 책임을 나눴습니다.
- Result: 반복 리포트 확인 조건 재현 가능, 운영자 공유 비용 감소

#### 리포트 확인 화면 통합

- Tags: Recharts, Table UX, Panel
- Summary: 차트, 표, 상세 패널이 같은 조건을 참조하도록 데이터 흐름과 화면 배치를 정리했습니다.
- 운영자가 반복하던 리포트 확인 흐름을 한 화면 안에서 처리할 수 있게 만들었습니다.
- 차트 선택, 표 row 선택, 상세 패널 열림 상태가 서로 충돌하지 않도록 상태 범위를 나눴습니다.

## Awards & Activities

### 한국대학생IT경영학회 큐시즘 프론트엔드 개발파트

- Period: 2021.08 - 2025.12
- 헬스케어, 세금계산서 검증, 접근성 보조 도구, 자세 교정 서비스 등 여러 팀 프로젝트 개발에 참여했습니다.
- 프론트엔드 구현뿐 아니라 발표, 팀 협업 흐름, 프로젝트별 역할 정리에도 참여했습니다.
- 프로젝트별 역할과 증빙은 `wiki/activities/`와 `wiki/projects/`에서 관리합니다.

## Notes

- 이 파일은 템플릿 예시다. 제출 전에 `cos-build-resume`로 실제 자료 기반 문서로 교체한다.
