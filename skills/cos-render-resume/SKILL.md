---
name: cos-render-resume
description: Use when rendering a resume markdown source into HTML or PDF under outputs/.../final using the shared resume template.
---

# COS Render Resume

## Layer Movement

`outputs/**/source/resume.md` -> `outputs/**/final/resume.html|pdf`.

## When to use

이미 작성된 resume markdown을 제출/검수용 HTML 또는 PDF로 렌더링할 때 사용한다.

## Inputs

- `outputs/general/source/resume.md`
- 또는 `outputs/custom/*/source/resume.md`
- `templates/resume/index.html`
- `templates/resume/styles.css`
- 필요한 로컬 이미지 자산

## Read first

1. `AGENTS.md`
2. `index.md`
3. `log.md`
4. `outputs/README.md`
5. 대상 `source/resume.md`
6. `templates/resume/index.html`
7. `templates/resume/styles.css`

## Template immutability

`templates/resume/index.html` and `templates/resume/styles.css` are canonical shared templates.
During normal resume render workflows, treat them as read-only.

- Do not edit `templates/resume/index.html` or `templates/resume/styles.css`.
- Do not create one-off section-specific CSS overrides for a single resume.
- Do not create an alternate HTML structure when the canonical template can express the resume.
- Generate rendered output only under `outputs/**/final/`.
- Copy required local assets into `outputs/**/final/assets/` when needed and rewrite final HTML paths to those copied assets.
- Do not leave final HTML dependent on `raw/**` paths.
- If the user asks for a new section or layout that the shared template cannot express, stop and treat it as a separate shared template-design change, not a render task.

## Resume content contract

Render only source resumes that match the shared template shape.

- 기본 섹션은 `About Me`, `Work Experience`, `Projects`, `Awards & Activities`만 사용한다.
- Work Experience와 Projects는 같은 content shape을 사용해야 한다.
- 각 Work Experience item은 회사/역할명, 1문장 소개, 2개 이상의 contribution block을 가진다.
- 각 Project item은 프로젝트명, 1문장 소개, 2개 이상의 contribution block을 가진다.
- 각 contribution block은 제목, 태그 3-5개, 환경/문제/필요성이 드러나는 1-2줄 요약, 큰 구현 bullet, 하위 구현 detail bullet, Result line으로 작성되어야 한다.
- 요약은 구현 방법을 반복하지 않고 어떤 업무/서비스 환경에서 어떤 문제가 실제로 있었고 왜 재발 방지나 개선이 필요했는지 설명해야 한다. 필요하면 두 줄까지 허용한다.
- 기본 기능 구현처럼 강한 문제 해결 claim이 없는 경우, 요약은 "구현해야 했던 상황"만 설명해야 한다.
- 기술적 선택이 있으면 큰 구현 bullet에서 `A vs B` 선택과 이유를 써야 한다.
- 기술적 선택이 없으면 큰 구현 bullet은 기본 구현 내용을 한 줄로 써야 한다.
- Awards와 Activities는 기본적으로 `Awards & Activities` 단일 섹션에 합친다.
- 단일 프로젝트를 bullet list 하나로만 끝내지 않는다.
- `Skills`, `Education`, 또는 다른 새 섹션이 필요하면 shared template-design change로 분리한다.

## Allowed edits

- `outputs/general/final/resume.html`
- `outputs/general/final/resume.pdf`
- `outputs/custom/*/final/resume.html`
- `outputs/custom/*/final/resume.pdf`
- `outputs/**/final/assets/**`
- 필요 시 `log.md`

## Forbidden edits

- `raw/**`
- `wiki/**`
- `templates/resume/index.html`
- `templates/resume/styles.css`
- 대상 `source/resume.md` 의미 변경
- 포트폴리오 렌더링
- remote image를 최종 렌더에 직접 의존

## Workflow

1. 대상 source resume을 확정한다.
2. 필요한 로컬 프로필 이미지 또는 자산이 존재하는지 확인한다.
3. source resume이 Resume content contract를 만족하는지 확인한다.
4. read-only shared resume template을 적용해 HTML을 만든다.
5. 요청 시 PDF를 생성한다.
6. 모든 asset path가 local final path 또는 template path로 해결되는지 확인하고 final HTML이 `raw/**`에 직접 의존하지 않게 한다.
7. HTML/PDF에서 깨진 이미지, overflow, placeholder, source와의 불일치를 확인한다.
8. 단독 실행이면 `log.md`에 `output` 항목을 append 한다.

## Output files

- `outputs/.../final/resume.html`
- optional `outputs/.../final/resume.pdf`
- optional `outputs/.../final/assets/**`

## Quality gates

- source markdown의 사실과 순서가 보존된다.
- source markdown이 Resume content contract를 만족한다.
- broken link/image가 없다.
- final HTML이 `raw/**` asset path에 직접 의존하지 않는다.
- 글자가 카드/페이지 밖으로 밀리지 않는다.
- placeholder, initials-only 이미지, remote-only 이미지가 없다.
- `git diff --check`가 통과한다.

## Stop conditions

- source resume이 없거나 placeholder 상태다.
- source resume이 Resume content contract를 만족하지 않는다.
- 필요한 프로필 이미지가 없고 사용자가 이미지 없는 렌더를 허용하지 않았다.
- 요청한 출력이 shared template 수정 없이는 불가능하다.
- PDF 렌더링 도구가 없어 요청한 형식을 만들 수 없다.

## Log format

```md
## [YYYY-MM-DD] output | rendered resume updated

- Rendered from `outputs/.../source/resume.md`
- Wrote `outputs/.../final/resume.html`
- Wrote `outputs/.../final/resume.pdf` if requested
```
