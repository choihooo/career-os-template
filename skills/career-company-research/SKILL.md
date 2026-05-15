---
name: career-company-research
description: Use when the user provides a JD link, company careers page, or target company name and wants compact research materials for an application, saved into outputs/custom/YYYY-MM-DD-company/research.
---

# Career Company Research

## Purpose

이 스킬은 특정 회사 지원 전에 조사 패키지를 만드는 스킬이다. JD만 읽는 것이 아니라 회사의 공식 메시지, 인재상, 채용 신호, 인터뷰 신호를 모아 지원 전략의 입력 자료를 만든다.

JD부터 최종 resume/portfolio까지 한 번에 만드는 요청에서는 `career-apply-pipeline`의 research 단계로 실행한다.

## Source Priority

Use sources in this order:

1. Official JD or careers page
2. Official company site
3. Official leadership messages
4. Official hiring or culture pages
5. Official tech blog, newsroom, or investor materials if relevant
6. Secondary sources such as interview 후기, employee posts, and community threads

Treat secondary sources as weak evidence.

## Required Inputs

At least one of:

- JD URL
- company careers URL
- company name plus target role

## Output Folder

Write into:

`outputs/custom/YYYY-MM-DD-company/research/`

If the package folder does not exist yet, create it along with `source/`.

## Required Files

This skill produces or updates:

- `research/company.md`
- `research/signals.md`

It may also update:

- `source/jd.md`
- `source/brief.md`
- `log.md`

## Required Workflow

1. Create or locate the target company folder under `outputs/custom/YYYY-MM-DD-company/`.
2. Save the JD text or a structured summary in `source/jd.md` if it is not already there.
3. Research official company sources and write `research/company.md`:
   - company summary
   - business direction
   - recent priorities
   - role relevance
   - dated source links
4. Extract official values, talent signals, leadership language, interview themes, and repeated patterns into `research/signals.md`.
5. Push only actionable tailoring implications back into `source/brief.md` when useful.
6. If this skill is running inside `career-apply-pipeline`, let the pipeline own the final log entry. Otherwise, append one `research` or `output` entry to `log.md`.

## Research Rules

- Use web sources when facts may be current or unstable.
- Prefer official sources whenever possible.
- Include dates and links for claims that could change over time.
- Do not present community anecdotes as company truth.
- If the company has little public information, say so plainly.

## Log Format

```md
## [YYYY-MM-DD] research | built company research package for company

- Saved JD summary and source links
- Added `research/company.md`
- Added `research/signals.md`
- Backfilled `source/brief.md` if useful
```

## Stop Conditions

Stop and ask the user if:

- the provided link is dead or clearly unrelated
- multiple roles or business units are mixed together
- the available evidence is too weak to support meaningful fit hypotheses
