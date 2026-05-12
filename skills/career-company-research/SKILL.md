---
name: career-company-research
description: Use when the user provides a JD link, company careers page, or target company name and wants research materials for an application, including analysis of the JD, official company messaging, talent principles, hiring signals, new year messages, and interview or acceptance patterns, saved into the company package folder.
---

# Career Company Research

## Purpose

이 스킬은 특정 회사 지원 전에 조사 패키지를 만드는 스킬이다. JD만 읽는 것이 아니라 회사의 공식 메시지, 인재상, 채용 신호, 인터뷰 신호를 모아 지원 전략의 입력 자료를 만든다.

JD부터 최종 resume/portfolio까지 한 번에 만드는 요청에서는 `career-apply-pipeline`의 research 단계로 실행한다.

## Source Priority

Use sources in this order:

1. Official JD or careers page
2. Official company site
3. Official leadership messages:
   - CEO message
   - annual letter
   - new year message
   - mission or values page
4. Official hiring or culture pages
5. Official tech blog, newsroom, or investor materials if relevant
6. Secondary sources:
   - interview 후기
   - employee posts
   - 합격자 후기
   - community threads

Treat secondary sources as weak evidence. Use them to generate hypotheses, not to state company facts confidently.

## Required Inputs

At least one of:

- JD URL
- company careers URL
- company name plus target role

If there is no URL, infer the company package name from the company name and date, then stop if the role context is too vague.

## Output Folder

Write into:

`outputs/custom/YYYY-MM-DD-company/`

If the folder does not exist yet, create it.

## Required Files

This skill produces or updates:

- `jd.md`
- `company-research.md`
- `culture-signals.md`
- `interview-signals.md`
- `fit-hypotheses.md`

It may also update:

- `analysis.md`
- `strategy.md`
- `log.md`

## Required Workflow

1. Create or locate the target company folder under `outputs/custom/YYYY-MM-DD-company/`.
2. Save the JD text or a structured summary in `jd.md`.
3. Research official company sources and write `company-research.md`:
   - company summary
   - business direction
   - recent priorities
   - role relevance
   - dated source links
4. Extract official values, talent signals, leadership language, and recurring internal themes into `culture-signals.md`.
5. Review secondary signals and write `interview-signals.md`:
   - likely interview themes
   - commonly emphasized competencies
   - weak or noisy signals clearly labeled
6. Synthesize the findings into `fit-hypotheses.md`:
   - why you may fit
   - where your evidence is strong
   - where your fit is weaker
   - what stories or metrics to emphasize
   - what claims to avoid
7. If useful, backfill:
   - `analysis.md`
   - `strategy.md`
8. If this skill is running inside `career-apply-pipeline`, let the pipeline own the final log entry. Otherwise, append one `research` or `output` entry to `log.md`.

## File Expectations

### `company-research.md`

Keep this factual and source-driven:

- target company and role
- official source list with dates
- business and product context
- team or role context if available
- recent strategic signals

### `culture-signals.md`

Capture:

- mission and values wording
- talent principles
- leadership language patterns
- phrases worth matching in application materials
- signals that should shape tone or emphasis

### `interview-signals.md`

Separate clearly:

- strong signals from official or repeated evidence
- weak signals from anecdotal reports

Always label anecdotal material as anecdotal.

### `fit-hypotheses.md`

This is the bridge to resume and portfolio tailoring. It should answer:

- what angle should the application take
- which projects should lead
- which stories should support them
- which gaps need careful handling

## Research Rules

- Use web sources when facts may be current or unstable.
- Prefer official sources whenever possible.
- Include dates and links for claims that could change over time.
- Do not present community anecdotes as company truth.
- Do not infer culture from a single blog post or a single 후기.
- If the company has little public information, say so plainly.

## Log Format

```md
## [YYYY-MM-DD] research | built company research package for company

- Saved JD summary and source links
- Added company, culture, and interview signal notes
- Wrote fit hypotheses for tailored application materials
```

## Stop Conditions

Stop and ask the user if:

- the provided link is dead or clearly unrelated
- multiple roles or business units are mixed together
- the company slug or target package folder is ambiguous
- the available evidence is too weak to support meaningful fit hypotheses
