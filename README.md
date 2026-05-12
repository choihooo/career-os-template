# Career OS Template

채용 지원 자료를 `raw/`, `wiki/`, `outputs/`로 나눠 관리하고, JD별 맞춤 이력서/포트폴리오 패키지를 만드는 템플릿이다.

이 브랜치는 개인 정보가 제거된 시작점이다. 먼저 샘플을 읽고, 자기 자료를 `raw/`에 넣은 뒤, 스킬 워크플로로 위키와 산출물을 갱신한다.

## 빠른 시작

처음 쓰는 순서는 아래가 가장 안전하다.

1. `index.md`에서 현재 구조와 샘플 파일을 확인한다.
2. `raw/bios/profile.md`에 기본정보와 링크를 먼저 채운다.
3. 프로필 사진 원본은 `raw/assets/`에 보관하고, 렌더링용 이미지는 `resume/assets/`, `portfolio/assets/`에 둔다.
4. `examples/` 중 하나에 맞춰 프로젝트, 경력, 수상 자료를 준비한다.
5. `career-ingest`로 `raw/`와 `wiki/`를 먼저 채운다.
6. `career-build-general`로 `outputs/general/`의 범용 이력서/포트폴리오를 만든다.
7. 실제 JD가 생기면 `career-apply-pipeline`으로 회사별 패키지를 만든다.
8. 제출용 HTML/PDF가 필요할 때만 `career-build-rendered-resume` 또는 `career-build-rendered-portfolio`를 쓴다.
9. 제출 전 `docs/checklists/custom-output-quality-checklist.md`와 `career-lint`로 누락, 과장, 중복을 확인한다.

## 가장 많이 쓰는 요청

### 새 경험 추가

```md
아래 자료를 career-ingest 기준으로 반영해줘. raw에 원천을 저장하고, 관련 wiki 페이지와 sentence bank/story bank/index/log까지 갱신해줘.

[자료 붙여넣기]
```

### 범용 이력서/포트폴리오 생성

```md
현재 위키 기준으로 outputs/general의 resume-general-v1, resume-general-v2, portfolio-general-v1, portfolio-general-v2를 갱신해줘. 최종 저장 전에 career-output-polish 기준으로 다듬어줘.
```

### JD 기반 맞춤 패키지 생성

```md
이 JD 기준으로 career-apply-pipeline을 실행해줘. 회사별 맞춤 패키지를 만들고, 필요하면 HTML/PDF 렌더링까지 이어서 처리해줘.

[JD 링크 또는 원문]
```

## Repository Structure

```text
career-os-template/
├── AGENTS.md
├── README.md
├── index.md
├── log.md
├── examples/
├── docs/checklists/
├── raw/
├── wiki/
├── outputs/
├── resume/
├── portfolio/
└── skills/
```

## Layers

- `raw/`: 원천 자료. 사실 원형, 링크, 메모를 보존한다.
- `wiki/`: 정규화된 경력 지식. 경험, 프로젝트, 수상, 기술, 스토리, 문장 뱅크를 관리한다.
- `outputs/`: 제출 가능한 산출물. 범용본은 `outputs/general/`, 회사별 맞춤본은 `outputs/custom/YYYY-MM-DD-company/`에 둔다.
- `resume/`, `portfolio/`: markdown 산출물을 HTML/PDF로 렌더링하기 위한 정적 템플릿이다.
- `skills/`: Codex가 반복 워크플로를 실행할 때 읽는 스킬 지시서다.

## Template Files

- `examples/`: 사용자가 붙여 넣을 입력 형식
- `raw/bios/profile.md`: 이름, 연락처, 링크, 학력, 선호 직무 같은 기본정보 원천
- `raw/assets/`: 프로필 사진과 프로젝트 이미지의 원본 보관 위치
- `wiki/templates/`: 새 위키 페이지 작성 구조
- `wiki/output-briefs/`: 범용 이력서/포트폴리오 조립 기준
- `outputs/custom/2026-01-01-example-frontend/`: 샘플 JD 패키지
- `resume/assets/`, `portfolio/assets/`: 이력서/포트폴리오 렌더링에 직접 쓰는 에셋 위치
- `resume/index.html`, `portfolio/index.html`: 개인정보 없는 렌더링 스타터

## Profile and Assets

기본정보와 이미지는 아래 원칙으로 관리한다.

```text
raw/bios/profile.md              # 기본정보 원천
raw/assets/profile-photo.jpg     # 원본 프로필 사진
raw/assets/profile-photo-square.png

resume/assets/profile.png        # 이력서 렌더링용
portfolio/assets/profile.png     # 포트폴리오 렌더링용
portfolio/assets/project-*.png   # 프로젝트 이미지
```

- `raw/`에는 원본을 둔다.
- `resume/assets/`, `portfolio/assets/`에는 렌더링에 맞게 가공한 사본을 둔다.
- 공개 템플릿에는 실제 프로필 사진, 내부 자료, 비공개 증빙 이미지를 커밋하지 않는다.

## Rules

- 기본 언어는 한국어다.
- 근거 없는 수치, 역할, 매출/트래픽 임팩트는 만들지 않는다.
- 부족한 정보는 `Gaps` 또는 `analysis.md`에 남긴다.
- 같은 내용을 여러 산출물에 직접 복붙하지 않는다. 먼저 `wiki/`를 갱신하고 산출물을 다시 만든다.
- 제출 전에는 `career-output-polish`로 과장된 표현과 AI식 문장을 줄인다.

## Before Publishing Your Copy

- 샘플 후보명, 샘플 회사명, 샘플 링크를 실제 정보로 바꿨는지 확인한다.
- 공개 레포로 만들기 전 `rg -n "email|phone|linkedin|github|@|실명|주민|주소"` 등으로 민감 정보를 확인한다.
- PDF, 프로필 사진, 회사 내부 자료, 비공개 링크는 커밋하지 않는다.
