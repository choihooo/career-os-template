---
name: career-ingest
description: Use when adding new career source material into this repository, such as awards, self-introduction fragments, experience notes, project links, or achievement evidence, and you need to update raw sources, related wiki pages, sentence bank, stories, index, and log in one pass.
---

# Career Ingest

## Purpose

이 스킬은 새 커리어 원천 자료를 이 저장소에 반입하고, 관련 위키 지식과 재사용 산출 기반을 함께 갱신할 때 사용한다.

## Read First

Before editing, read these files in order:

1. `AGENTS.md`
2. `index.md`
3. `log.md`
4. Relevant existing pages under `wiki/`

## Source Types

Classify the new input into one primary raw location:

- awards: 수상, 장학, 선발, 인증
- bios: 자기소개 조각, 지원 동기, 한 줄 소개, 회고 문장
- experiences: 회사/역할/성과/책임 관련 사실
- projects: 프로젝트 소개, 링크, 기여, 기술, 결과
- links: 외부 링크 모음, 레포 링크, 기사 링크, 발표 링크

If the material spans multiple categories, choose the strongest primary category and link to the others from wiki pages rather than duplicating the raw source.

## Required Workflow

1. Save the raw source into the correct `raw/` directory.
2. Read the closest matching pages under `wiki/` before creating anything new.
3. Extract only reusable facts:
   - what happened
   - where and when
   - your role
   - measurable result
   - evidence or link
4. Update or create the relevant wiki page.
5. Update `wiki/sentence-bank/resume-bullets.md` if the source yields reusable resume bullets.
6. Update `wiki/stories/story-bank.md` if the source yields a reusable STAR/CAR story.
7. Update `index.md` if you created a new wiki page or raw source page worth cataloging.
8. Append one entry to `log.md`.

## Writing Rules

- Default to Korean.
- Keep raw sources close to the original wording and evidence.
- Keep wiki pages normalized and reusable.
- Prefer updating existing wiki pages over creating near-duplicates.
- Do not invent metrics or dates.
- If evidence is missing, mark it explicitly as missing instead of guessing.

## Expected Output Shape

When the ingest is complete, the repository should show:

- one new or updated file in `raw/`
- one or more new or updated files in `wiki/`
- optional updates to:
  - `wiki/sentence-bank/resume-bullets.md`
  - `wiki/stories/story-bank.md`
  - `index.md`
  - `log.md`

## Log Format

Append entries in this format:

```md
## [YYYY-MM-DD] ingest | short description

- Added raw source under `raw/...`
- Updated `wiki/...`
- Updated sentence bank and story bank if applicable
```

## Stop Conditions

Stop and ask the user if:

- the source belongs to multiple incompatible categories and placement is unclear
- the source contradicts existing facts in the wiki
- a metric looks unreliable or unsupported
- the source is too sparse to extract reusable facts
