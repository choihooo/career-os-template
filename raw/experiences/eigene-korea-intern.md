# 아이겐코리아 프론트엔드 인턴 원천 메모

## Source

- Primary extracted source: `resume/index.html`, `portfolio/index.html`
- Organization: 아이겐코리아
- Role: Frontend Engineer 인턴
- Period: 2025.03.04 - 2025.06.30
- Team: 개발실, 풀스택 1명, 백엔드 2명, 프론트엔드 1명
- Organization context: 빅데이터 기반 개인화 추천 및 마케팅 솔루션 제공 회사

## Facts

- 프론트엔드 인턴으로 개발실에 합류했다.
- 유일한 프론트엔드 담당자로서 서비스 기능 데모 페이지 개발, 클라이언트사 QA 및 이슈 대응, 어드민 페이지 안정성 향상을 맡았다.
- 어드민 TypeScript 버전을 v3에서 v5로 마이그레이션했다.
- strict 모드 전환을 위해 `noImplicitAny`, `strictNullChecks`, 외부 라이브러리 호환성 점검, `strict: true` 순서로 단계적 전환을 진행했다.
- 50개 이상의 `any` 타입을 명시적 타입으로 전환했다.
- 빌드 속도가 평균 246.22초에서 199.51초로 약 19% 단축됐다.
- 다국어 번역 키 누락을 한국어 JSON 기준으로 비교하는 자동 검증 스크립트를 만들고 CI에 연결했다.
- 누락 키가 있으면 언어별 목록을 출력하고 `exit code 1`로 PR 단계에서 차단하도록 했다.
- 바운스사 어드민 센터 정보 30개 이상이 하드코딩되어 있던 구조를 API 기반 동적 로딩으로 전환했다.
- 38개 파일의 하드코딩 참조를 제거하고 Recoil atom/selector와 LocalStorage effect를 사용해 전역 상태와 캐싱 구조를 설계했다.
- 목표 달성률, 전년 대비 증감률(YoY), 센터별/전체 통계를 추가하고 Recharts 기반 복합 차트와 엑셀 다운로드 연동을 구현했다.

## Evidence Links

- Homepage: https://eigene.ai/
- TypeScript migration blog 1: https://hochoi.tistory.com/23
- TypeScript migration blog 2: https://hochoi.tistory.com/25

## Missing or Verify

- 아이겐코리아 업무별 실제 운영 반영 범위
- i18n 자동화로 차단한 실제 누락 건수
- 센터 API 전환 후 운영/배포 지표
