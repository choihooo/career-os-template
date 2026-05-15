# Career OS Template

채용 지원 자료를 `raw/`, `wiki/`, `outputs/`로 나눠 관리하고, JD별 맞춤 이력서/포트폴리오 패키지를 만드는 템플릿이다.

이 브랜치는 개인 정보가 제거된 시작점이다. 먼저 샘플을 읽고, 자기 자료를 `raw/`에 넣은 뒤, 스킬 워크플로로 위키와 산출물을 갱신한다.

## 빠른 시작

처음 쓰는 순서는 아래가 가장 안전하다.

1. `index.md`에서 현재 구조와 샘플 파일을 확인한다.
2. `raw/bios/profile.md`에 기본정보와 링크를 먼저 채운다.
3. 프로필 사진 원본은 `raw/assets/`에 보관하고, 공용 렌더링 템플릿 자산은 `templates/resume/assets/`, `templates/portfolio/assets/`에 둔다.
4. `examples/` 중 하나에 맞춰 프로젝트, 경력, 수상 자료를 준비한다.
5. `career-ingest`로 `raw/`와 `wiki/`를 먼저 채운다.
6. `career-build-general`로 `outputs/general/source/`의 범용 이력서/포트폴리오를 만든다.
7. 제출용 HTML/PDF가 필요할 때만 `outputs/general/final/`에 렌더한다.
8. 실제 JD가 생기면 `career-apply-pipeline`으로 `outputs/custom/YYYY-MM-DD-company/` 패키지를 만든다.
9. 제출 전 `docs/checklists/custom-output-quality-checklist.md`와 `career-lint`로 누락, 과장, 중복을 확인한다.

## 가장 많이 쓰는 요청

### 새 경험 추가

```md
아래 자료를 career-ingest 기준으로 반영해줘. raw에 원천을 저장하고, 관련 wiki 페이지와 sentence bank/story bank/index/log까지 갱신해줘.

[자료 붙여넣기]
```

### 범용 이력서/포트폴리오 생성

```md
현재 위키 기준으로 outputs/general/source/resume.md와 outputs/general/source/portfolio.md를 갱신해줘. 최종 저장 전에 career-output-polish 기준으로 다듬어줘.
```

### JD 기반 맞춤 패키지 생성

```md
이 JD 기준으로 career-apply-pipeline을 실행해줘. outputs/custom/YYYY-MM-DD-company/source에 jd, brief, resume, portfolio를 만들고, 필요하면 research와 final HTML/PDF 렌더링까지 이어서 처리해줘.

[JD 링크 또는 원문]
```

## Repository Structure

```text
career-os-template/
├── AGENTS.md
├── README.md
├── index.md
├── log.md
├── samples/
├── examples/
├── docs/checklists/
├── raw/
├── wiki/
├── outputs/
│   ├── general/
│   │   ├── source/
│   │   └── final/
│   └── custom/
│       └── YYYY-MM-DD-company/
│           ├── source/
│           ├── research/
│           └── final/
├── templates/
│   ├── resume/
│   ├── portfolio/
│   └── card-news/
└── skills/
```

## Folder Roles

- `raw/`: 사용자의 원천 자료를 저장하는 입력 계층이다. 초안 메모, 경력 사실, JD 원문, 이미지 원본을 모은다.
- `wiki/`: 원천 자료를 정규화한 지식 계층이다. 직접 제출하지 않고, 산출물 조립의 기반으로 쓴다.
- `outputs/general/source/`: 범용 이력서와 포트폴리오 markdown 원본을 저장한다.
- `outputs/general/final/`: 범용 이력서와 포트폴리오의 HTML/PDF 렌더 결과를 저장한다.
- `outputs/custom/YYYY-MM-DD-company/source/`: 회사별 맞춤 패키지용 JD, brief, resume, portfolio 원본을 저장한다.
- `outputs/custom/YYYY-MM-DD-company/research/`: 회사 조사, 문화 신호, 인터뷰 신호 같은 참고 문서를 저장한다.
- `outputs/custom/YYYY-MM-DD-company/final/`: 회사별 맞춤 이력서와 포트폴리오의 HTML/PDF 렌더 결과를 저장한다.
- `samples/`: 템플릿 설명용 샘플 입력, 샘플 위키, 샘플 맞춤 패키지를 모아 둔 데모 계층이다.
- `templates/`: markdown 산출물을 HTML/PDF로 렌더링하기 위한 공용 정적 템플릿을 둔다.
- `docs/`: GitHub Pages로 공개할 정적 문서와 카드뉴스 배포 결과물을 둔다.
- `examples/`: 사용자가 복붙해서 입력 형식을 맞출 수 있는 예시 모음이다.
- `skills/`: Codex가 반복 워크플로를 수행할 때 따르는 스킬 지시서다.

## Layers

- `raw/`: 원천 자료. 사실 원형, 링크, 메모를 보존한다.
- `wiki/`: 정규화된 경력 지식. 경험, 프로젝트, 수상, 기술, 스토리, 문장 뱅크를 관리한다.
- `outputs/`: 제출 가능한 산출물과 그 직전 원본. 수정은 `source/`에서, 제출과 검수는 `final/`에서 한다.
- `templates/`: markdown 산출물을 HTML/PDF/카드뉴스로 렌더링하기 위한 공용 정적 템플릿이다.
- `skills/`: Codex가 반복 워크플로를 실행할 때 읽는 스킬 지시서다.

## Template Files

- `docs/index.html`, `docs/styles.css`: Career OS 카드뉴스를 보여주는 GitHub Pages 랜딩 페이지
- `docs/guide.html`, `docs/directory.html`, `docs/prompts.html`, `docs/checklist.html`: GitHub Pages용 안내 페이지
- `templates/card-news/career-os-template/exports/`: Career OS 템플릿 소개 카드뉴스 PNG export 원본
- `docs/card-news/career-os-template/exports/`: 공개 배포용 카드뉴스 PNG export
- `samples/README.md`: 샘플 자료의 범위와 사용 원칙
- `examples/`: 사용자가 붙여 넣을 입력 형식
- `raw/bios/profile.md`: 이름, 연락처, 링크, 학력, 선호 직무 같은 기본정보 원천
- `raw/assets/`: 프로필 사진과 프로젝트 이미지의 원본 보관 위치
- `wiki/templates/`: 새 위키 페이지 작성 구조
- `wiki/output-briefs/`: 범용 이력서/포트폴리오 조립 기준
- `templates/resume/index.html`, `templates/portfolio/index.html`: 공용 렌더링 템플릿
- `outputs/general/source/`: 범용 markdown 원본 저장 위치
- `outputs/general/final/`: 범용 HTML/PDF 렌더 결과 저장 위치
- `samples/custom-packages/`: 샘플 회사별 패키지와 rendered 결과 예시

## Web Preview

- Docs landing: `https://choihooo.github.io/career-os-template/`
- Card news: `https://choihooo.github.io/career-os-template/card-news/career-os-template/`

## Profile and Assets

기본정보와 이미지는 아래 원칙으로 관리한다.

```text
raw/bios/profile.md                         # 기본정보 원천
raw/assets/profile-photo.png               # 권장 원본 프로필 사진
raw/assets/profile-photo.jpg               # 허용 원본 프로필 사진
raw/assets/profile-photo.jpeg
raw/assets/profile-photo-square.png

templates/resume/assets/                   # 공용 resume 템플릿 자산
templates/portfolio/assets/                # 공용 portfolio 템플릿 자산
outputs/.../final/assets/                  # 지원건별 렌더 결과 자산
```

- `raw/`에는 원본을 둔다.
- 샘플 입력, 샘플 위키, 샘플 맞춤 패키지는 `samples/` 아래에 모아 둔다.
- `source/`는 사람이 직접 수정하는 markdown 원본이며 source of truth다.
- `final/`은 실제 검수, 공유, 제출에 사용하는 렌더링 결과물이다.
- `templates/`에는 공용 HTML/CSS 템플릿만 둔다.
- 프로필 사진 원본 권장 파일명은 `raw/assets/profile-photo.png`다.
- 렌더링 스킬은 `profile-photo.png`, `profile-photo.jpg`, `profile-photo.jpeg`, `profile-photo-square.png`를 허용한다.
- 공개용 개인 저장소에는 실제 프로필 사진, 내부 자료, 비공개 증빙 이미지를 커밋하지 않는다.

## Rules

- 기본 언어는 한국어다.
- 근거 없는 수치, 역할, 매출/트래픽 임팩트는 만들지 않는다.
- 부족한 정보는 `Gaps` 또는 `brief.md`에 남긴다.
- 같은 내용을 여러 산출물에 직접 복붙하지 않는다. 먼저 `wiki/`를 갱신하고 산출물을 다시 만든다.
- 제출 전에는 `career-output-polish`로 과장된 표현과 AI식 문장을 줄인다.
- 샘플 파일과 샘플 rendered 산출물은 템플릿 설명용으로 유지할 수 있지만, 실제 개인 자료와 혼동되지 않게 파일명, 경로, 설명을 분리한다.

## Before Publishing Your Copy

- 샘플 후보명, 샘플 회사명, 샘플 링크를 실제 정보로 바꿨는지 확인한다.
- 공개 레포로 만들기 전 `rg -n "email|phone|linkedin|github|@|실명|주민|주소"` 등으로 민감 정보를 확인한다.
- 샘플 PDF와 샘플 이미지를 유지할 수는 있지만, 실제 개인 PDF, 실제 프로필 사진, 회사 내부 자료, 비공개 링크는 커밋하지 않는다.
