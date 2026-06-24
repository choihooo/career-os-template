# Career OS Template

채용 지원 자료를 `raw/`, `wiki/`, `outputs/`로 나눠 관리하고, 근거 기반 이력서를 생성하는 resume-only Career OS 템플릿이다.

본 레포는 실제 운영 구조만 포함한다. 데모 데이터와 예제 산출물은 별도 `career-os-template-samples` 레포에서 관리한다.

## 빠른 시작

1. `index.md`에서 현재 구조와 읽기 순서를 확인한다.
2. `raw/profile/profile.md`, `raw/profile/links.md`, `raw/profile/preferences.md`를 채운다.
3. 원본 이미지와 증빙 파일은 `raw/assets/`에 보관한다.
4. 새 자료는 `cos-register-source`로 `raw/`에 저장한다.
5. 저장된 원천은 `cos-ingest`로 `wiki/` 지식, claim, proof, story, bullet 후보로 승격한다.
6. 범용 이력서는 `cos-build-resume`로 `outputs/general/source/resume.md`에 생성한다.
7. JD가 생기면 `cos-apply-resume`로 `outputs/custom/YYYY-MM-DD-company-role/` 패키지를 만든다.
8. HTML/PDF가 필요할 때만 `cos-render-resume`으로 `final/`에 렌더한다.
9. 제출 전 `cos-lint`와 `docs/checklists/custom-output-quality-checklist.md`로 구조, 근거, 과장을 점검한다.

## 가장 많이 쓰는 요청

### 새 자료 저장

```md
아래 자료를 cos-register-source 기준으로 raw에 저장해줘. 분류가 애매하면 raw/inbox에 두고, index와 log까지 갱신해줘.

[자료 붙여넣기]
```

### 위키 승격

```md
이 raw 자료를 cos-ingest 기준으로 wiki에 반영해줘. claim/proof, sentence bank, story bank, index, log까지 필요한 범위만 갱신해줘.
```

### 범용 이력서 생성

```md
현재 wiki 기준으로 outputs/general/source/resume.md를 cos-build-resume 기준으로 갱신해줘. claim/proof를 확인하고 unsupported claim은 제외해줘.
```

### JD 기반 맞춤 이력서

```md
이 JD 기준으로 cos-apply-resume을 실행해줘. outputs/custom/YYYY-MM-DD-company-role/source에 jd, brief, resume을 만들고, 근거가 부족한 부분은 brief에 gap으로 남겨줘.

[JD 링크 또는 원문]
```

## Repository Structure

```text
career-os-template/
├── AGENTS.md
├── README.md
├── index.md
├── log.md
├── raw/
│   ├── profile/
│   ├── experiences/
│   ├── projects/
│   ├── activities/
│   ├── awards/
│   ├── applications/
│   ├── evidence/
│   ├── assets/
│   └── inbox/
├── wiki/
│   ├── overview/
│   ├── themes/
│   ├── projects/
│   ├── experiences/
│   ├── activities/
│   ├── awards/
│   ├── skills/
│   ├── stories/
│   ├── sentence-bank/
│   ├── claims-ledger.md
│   ├── proof-map.md
│   └── output-briefs/
├── outputs/
│   ├── general/
│   │   ├── source/
│   │   └── final/
│   └── custom/
│       └── YYYY-MM-DD-company-role/
│           ├── source/
│           ├── research/
│           └── final/
├── templates/resume/
├── docs/
├── examples/
└── skills/
```

## Folder Roles

- `raw/`: 원천 자료를 보존하는 Source layer. 사실 원형, 링크, 증빙, JD 원문을 저장한다.
- `wiki/`: 정규화된 Knowledge layer. 경험, 프로젝트, 활동, claim/proof, story, bullet 후보를 관리한다.
- `outputs/`: 제출용 Output layer. 현재 범위는 이력서만 포함한다.
- `templates/resume/`: markdown 이력서를 HTML/PDF로 렌더링하기 위한 공용 템플릿이다.
- `docs/`: 공개 안내 문서와 체크리스트를 둔다.
- `examples/`: 사용자가 복붙해서 입력 형식을 맞출 수 있는 예시 모음이다.
- `skills/`: Codex가 반복 워크플로를 수행할 때 따르는 `cos-*` 지시서다.

## Standard Outputs

범용 이력서:

- `outputs/general/source/resume.md`
- optional `outputs/general/final/resume.html`
- optional `outputs/general/final/resume.pdf`

회사별 맞춤 이력서:

- `outputs/custom/YYYY-MM-DD-company-role/source/jd.md`
- `outputs/custom/YYYY-MM-DD-company-role/source/brief.md`
- `outputs/custom/YYYY-MM-DD-company-role/source/resume.md`
- optional `outputs/custom/YYYY-MM-DD-company-role/research/company.md`
- optional `outputs/custom/YYYY-MM-DD-company-role/research/signals.md`
- optional `outputs/custom/YYYY-MM-DD-company-role/final/resume.html`
- optional `outputs/custom/YYYY-MM-DD-company-role/final/resume.pdf`

## Rules

- 기본 언어는 한국어다.
- `source/`가 source of truth다.
- 근거 없는 수치, 역할, 매출/트래픽 임팩트는 만들지 않는다.
- 강한 claim은 `wiki/claims-ledger.md`와 `wiki/proof-map.md`로 추적한다.
- 부족한 정보는 `Gaps` 또는 `brief.md`에 남긴다.
- 새 사실은 output에 직접 만들지 않고 `raw/`와 `wiki/`로 역반영한다.
- 공개용 개인 저장소에는 실제 프로필 사진, 내부 자료, 비공개 증빙 이미지를 커밋하지 않는다.

## Web Preview

- Docs landing: `https://choihooo.github.io/career-os-template/`
- Card news: `https://choihooo.github.io/career-os-template/card-news/career-os-template/`
