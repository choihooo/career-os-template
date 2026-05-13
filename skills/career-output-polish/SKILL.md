---
name: career-output-polish
description: Use when polishing final resume or portfolio output files before delivery, especially to remove common AI writing tells, trim inflated phrasing, reduce repetitive sentence patterns, and make Korean application materials read more human and specific.
---

# Career Output Polish

## Purpose

이 스킬은 최종 이력서나 포트폴리오 산출물을 제출 직전에 교정하는 데 사용한다. 목표는 AI 티를 줄이고, 문장을 더 사람처럼 구체적으로 만드는 것이다.

## When To Use

Use this skill right before finalizing:

- `outputs/general/*.md`
- `outputs/custom/*/resume.md`
- `outputs/custom/*/portfolio.md`

Use it after the main content is already written. Do not use it as a substitute for content generation.

## Read Order

1. The target output file
2. `skills/career-output-polish/references/ai-writing-tropes.md`
3. Supporting strategy or positioning files only if needed for meaning preservation

## Required Workflow

1. Read the target file end to end.
2. Scan for repeated AI writing patterns from the reference file.
3. Rewrite only where needed:
   - remove inflated or templated phrasing
   - remove fake drama or fake insight
   - reduce repetitive rhythm
   - keep claims concrete and defensible
4. Preserve the actual meaning, evidence, and positioning.
5. Prefer shorter edits over full rewrites unless the section is clearly weak.

## Editing Rules

- Do not make the text bland just to avoid AI tells.
- Do not remove important specificity, metrics, dates, or named technologies.
- Avoid rhetorical flourishes that sound bloggy in a resume or portfolio.
- Prefer direct Korean phrasing over translated-English cadence.
- If a phrase is acceptable once but repeated many times, vary or cut it.
- For resume files, preserve or convert to 개조식 where appropriate. Do not polish resumes into essay-style paragraphs.
- For resume bullets, remove feature-only phrasing. A bullet like `애플 소셜 로그인 구현` should be rewritten, if source evidence exists, into 개조식 that shows problem/context + technical solution + outcome + feature.
- Prefer `이메일 가입 과정의 이탈을 줄이기 위해 OAuth 2 기반 애플 소셜 로그인을 구현해 회원가입 진입 장벽을 낮춤` over `OAuth 2 애플 소셜 로그인 구현`.
- Prefer `리뷰 게시글 조회 시 느린 응답이 발생해 로딩 처리와 데이터 요청 흐름을 개선하고 응답 속도를 350ms에서 20ms로 단축` over `리뷰 게시글 조회 로딩 개선`.
- Do not invent a metric while polishing. If only a qualitative result is supported, state the observable improvement in user, operator, QA, or developer experience.
- For portfolio files, narrative paragraphs are allowed, but keep resume-like evidence bullets concise.

## Output Standard

After polishing, the file should feel:

- specific
- credible
- restrained
- varied in sentence rhythm
- free of obvious AI trope clustering

## Stop Conditions

Stop and ask the user if:

- polishing would materially change the intended positioning
- the source text is too weak and needs rewriting rather than polishing
- the file appears to be notes, not a final-form document
