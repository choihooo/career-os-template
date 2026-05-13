---
name: career-build-general
description: Use when updating the general-purpose resume or portfolio versions in outputs/general, especially resume-general-v1, resume-general-v2, portfolio-general-v1, or portfolio-general-v2, based on the current career wiki pages and positioning.
---

# Career Build General

## Purpose

이 스킬은 범용 이력서와 범용 포트폴리오를 현재 위키 상태에 맞게 갱신할 때 사용한다.

## Read Order

Read these files before writing:

1. `AGENTS.md`
2. `index.md`
3. `wiki/overview/career-overview.md`
4. `wiki/themes/positioning.md`
5. `wiki/stories/story-bank.md`
6. `wiki/sentence-bank/resume-bullets.md`
7. Relevant files under `wiki/output-briefs/`
8. Any directly relevant project, experience, award, or skill pages

## Output Targets

Only write to these files unless the task explicitly asks for more:

- `outputs/general/resume-general-v1.md`
- `outputs/general/resume-general-v2.md`
- `outputs/general/portfolio-general-v1.md`
- `outputs/general/portfolio-general-v2.md`

## Version Intent

Use this default interpretation unless the user overrides it:

- `resume-general-v1`: straightforward, broad, safe baseline
- `resume-general-v2`: stronger positioning, sharper emphasis, more opinionated
- `portfolio-general-v1`: balanced overview of projects and proof
- `portfolio-general-v2`: narrative-driven and positioning-heavy version

## Required Workflow

1. Identify which general output files the user wants updated.
2. Read the positioning and reusable evidence pages first.
3. Read the relevant output brief before choosing section order or emphasis.
4. Select only the strongest and most defensible stories.
5. Rewrite the target output files so they read as coherent final documents, not as notes.
6. Before finalizing the target output files, invoke `career-output-polish` on each final-form resume or portfolio file.
7. If you discover missing reusable phrasing, backfill:
   - `wiki/sentence-bank/resume-bullets.md`
   - `wiki/themes/positioning.md`
   - `wiki/stories/story-bank.md`
8. Append one `output` entry to `log.md`.

## Writing Rules

- Default to Korean unless the user asks for English.
- Remove weak, generic, or unsupported claims.
- Prefer concrete impact over responsibility lists.
- Keep each version meaningfully distinct. Do not clone v1 into v2 with superficial wording changes.
- Do not add filler sections just because a template has space.

## Resume Formatting Rules

Apply these rules to `resume-general-v1.md` and `resume-general-v2.md`:

- Default to 개조식. General resumes should be easy to scan as bullets and compact rows.
- Keep summary sections short: one positioning line plus 2-4 bullets is enough.
- Experience and project bullets should follow a fact/action/result shape whenever possible.
- Do not write feature-only bullets like `애플 소셜 로그인 구현` or `관리자 대시보드 개발`.
- In 개조식, make each implementation bullet show why it mattered: problem or friction + solution or technical choice + outcome + feature.
  - Weak: `OAuth 2 애플 소셜 로그인 구현`
  - Strong: `이메일 가입 과정의 이탈을 줄이기 위해 OAuth 2 기반 애플 소셜 로그인을 구현해 회원가입 진입 장벽을 낮춤`
  - Weak: `리뷰 게시글 조회 로딩 개선`
  - Strong: `리뷰 게시글 조회 시 느린 응답이 발생해 로딩 처리와 데이터 요청 흐름을 개선하고 응답 속도를 350ms에서 20ms로 단축`
- If no measured metric exists, use a defensible observable result such as 사용자 경험 개선, 운영자 확인 흐름 단축, QA 재현 비용 감소, 유지보수 범위 축소.
- Skills, awards, education, links, roles, and periods should use compact phrases rather than prose.
- Do not write portfolio-style paragraphs in a resume. Move longer explanation, motivation, and case-study narrative to portfolio outputs.
- Cut weaker detail before expanding bullets into long paragraphs.

## Log Format

```md
## [YYYY-MM-DD] output | updated general resume or portfolio

- Updated `outputs/general/...`
- Refined positioning based on `wiki/...`
```

## Stop Conditions

Stop and ask the user if:

- the requested version goal is unclear
- the wiki lacks enough evidence to produce a credible general version
- two wiki pages conflict on core positioning
