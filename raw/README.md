# Raw Layer

`raw/`는 원천 자료를 보존하는 Source layer다. 사실 원형, 링크, 증빙, JD 원문은 가능한 한 이곳에 먼저 저장한다.

## Taxonomy

- `profile/`: 기본 프로필, 링크, 선호/회피 포지셔닝
- `experiences/`: 회사, 조직, 역할, 책임, 성과 메모
- `projects/`: 만든 제품, 프로젝트, 레포, 기술 결정
- `activities/`: 교육, 커뮤니티, 프로그램, 발표, 멘토링
- `awards/`: 수상, 선정, 장학, 인증, 자격
- `applications/`: JD 원문, 리크루터 노트, 지원 대상 원천
- `evidence/`: GitHub 분석, 피드백, 수치 근거, 스크린샷/인증서 설명
- `assets/`: 이미지, PDF, 원본 증빙 파일
- `inbox/`: 아직 분류가 애매한 임시 메모

## Rules

- 원천 자료는 덮어쓰기보다 추가를 우선한다.
- raw markdown은 가능하면 `type`, `id`, `status`, `evidence_strength`, `created_at`, `updated_at`, `related`를 가진다.
- 증빙이 약하면 `status: needs-proof` 또는 `evidence_strength: low`로 표시한다.
- 이력서에 바로 넣을 문장은 `wiki/claims-ledger.md`와 `wiki/proof-map.md`를 거쳐 승격한다.
