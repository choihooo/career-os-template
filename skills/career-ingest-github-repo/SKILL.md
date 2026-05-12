---
name: career-ingest-github-repo
description: Use when the user provides a GitHub repository, pull request, or commit URL and wants the repo history analyzed into structured career raw material, especially STAR/CAR story candidates, technical decisions, impact evidence, and contribution notes saved under raw/ for later wiki ingestion.
---

# Career Ingest GitHub Repo

## Purpose

이 스킬은 GitHub 링크를 받아 repo, commit, PR, file history를 분석하고, 이력서/포트폴리오/면접에 쓸 수 있는 STAR/CAR 후보를 `raw/` 원천 자료로 저장할 때 사용한다.

이 단계의 산출물은 정규화된 wiki 페이지가 아니라 증거가 붙은 원천 분석 파일이다. 이후 필요하면 `career-ingest`로 wiki, sentence bank, story bank에 반영한다.

지원 패키지 작업 중 GitHub 근거가 필요해 이 스킬을 실행했다면, raw 분석을 만든 뒤 본인 기여와 근거 수준이 확인된 항목만 `career-ingest` 또는 `career-apply-pipeline`으로 넘긴다.

## Inputs

Accept any of:

- GitHub repository URL
- GitHub pull request URL
- GitHub commit URL
- GitHub compare URL
- local cloned repository path, if already available

If the user provides only a repo URL, analyze the default branch and available branch/PR history. If the user provides a PR or commit URL, scope the analysis to that change first.

## Read First

Before writing:

1. `AGENTS.md`
2. `index.md`
3. Existing related raw/wiki pages if the project appears to already exist

## Source Priority

Use evidence in this order:

1. Commit metadata: hash, date, author, title, changed files
2. PR metadata: title, description, review comments, merge commit, linked issues
3. Repository files: README, package files, architecture files, source code
4. Release notes, tags, issues, discussions
5. External links from the repo, if directly relevant

Do not infer personal ownership from a repo alone. Treat authorship, role, and impact as unknown unless commits, PRs, or user-provided context support it.

## Output Location

Create one raw file under the best matching folder:

- project repo: `raw/projects/<project-slug>-github-analysis.md`
- company/work repo: `raw/experiences/<company-or-role-slug>-github-analysis.md`
- award or event repo: `raw/awards/<event-or-project-slug>-github-analysis.md`

Use ASCII lowercase slugs.

## Required Workflow

1. Resolve the GitHub target:
   - owner/repo
   - branch, PR number, commit hash, or compare range if provided
2. Collect evidence:
   - README and project purpose
   - main tech stack
   - commit/PR timeline
   - files or modules with meaningful changes
   - tests, CI, releases, deployments, or docs
3. Identify candidate contribution themes:
   - architecture or state management
   - performance optimization
   - UX flow or product behavior
   - testing, CI, automation, reliability
   - migration or refactoring
   - collaboration, review, or leadership
4. For each strong candidate, structure it as STAR/CAR:
   - Situation or Context
   - Task or Challenge
   - Action
   - Result or Evidence
   - Proof links: commit/PR/file paths
   - Confidence: high, medium, or low
5. Separate facts from interpretation:
   - Facts: verifiable from commits/files/PRs
   - Inferences: likely meaning, marked clearly
   - Gaps: missing user role, missing metrics, missing before/after evidence
6. Save the analysis to the raw file.
7. Update `index.md` if the raw file is worth cataloging.
8. Append one `ingest` entry to `log.md`.

## Raw File Template

Use this shape:

```md
# <Project or Repo Name> GitHub Analysis

## Source

- Repository:
- Scope:
- Analysis date:
- Access notes:

## Repo Summary

- Purpose:
- Tech stack:
- Main surfaces:

## Evidence Timeline

- `<date>` `<hash or PR>` - summary, files/modules, link

## STAR/CAR Candidates

### <Candidate Title>

- Confidence:
- Situation/Context:
- Task/Challenge:
- Action:
- Result/Evidence:
- Proof:
  - Commit/PR:
  - Files:
- Reusable angle:
- Gaps:

## Technical Decisions Found

- Decision:
- Evidence:
- Possible resume/portfolio use:

## Gaps And Questions

- Unknown role boundaries:
- Missing metrics:
- Missing external proof:
```

## Writing Rules

- Default to Korean.
- Keep raw evidence close to the original source.
- Do not invent metrics, users, business impact, awards, or ownership.
- Mark weak evidence as weak.
- Prefer “후보” wording until the user confirms role and impact.
- If the repo is large, sample commits around meaningful modules rather than summarizing every trivial commit.
- If there are many authors, distinguish the target user's commits from overall repo history when possible.

## Validation

At minimum:

- Confirm the raw file exists.
- Confirm every cited local file path or GitHub URL is plausible.
- Run `git diff --check`.

If using `gh` or network access fails, record the limitation in `Access notes` and continue only with accessible local evidence.

## Log Format

```md
## [YYYY-MM-DD] ingest | GitHub repo analysis for <project>

- Analyzed GitHub source `<url>`
- Created `raw/projects/<project-slug>-github-analysis.md`
- Extracted STAR/CAR candidates with evidence and gaps
```

## Stop Conditions

Stop and ask the user if:

- the GitHub link is private or inaccessible and no local clone is available
- the repo has multiple likely projects and the target scope is ambiguous
- the user's identity or GitHub username is needed to separate their commits from other contributors
- the commit history contradicts the user's stated role or dates
