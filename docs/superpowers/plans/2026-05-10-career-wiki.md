# Career Wiki Scaffolding Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** 커리어 위키 저장소의 초기 구조를 만들고, LLM 운영 규칙과 핵심 템플릿 파일을 추가해 바로 ingest와 산출물 생성을 시작할 수 있게 한다.

**Architecture:** 저장소는 `raw/`, `wiki/`, `outputs/`의 3층 구조를 갖는다. `AGENTS.md`가 운영 규칙을 정의하고, `index.md`와 `log.md`가 탐색과 이력 관리를 담당하며, 각 하위 디렉터리는 커리어 자료를 원천 자료, 정규화 지식, 제출 산출물로 구분해 저장한다.

**Tech Stack:** Markdown, plain text repository structure, shell commands, Git optional

---

### Task 1: Create Repository Skeleton

**Files:**
- Create: `AGENTS.md`
- Create: `index.md`
- Create: `log.md`
- Create: `raw/awards/.gitkeep`
- Create: `raw/bios/.gitkeep`
- Create: `raw/experiences/.gitkeep`
- Create: `raw/projects/.gitkeep`
- Create: `raw/links/.gitkeep`
- Create: `wiki/overview/.gitkeep`
- Create: `wiki/experiences/.gitkeep`
- Create: `wiki/projects/.gitkeep`
- Create: `wiki/awards/.gitkeep`
- Create: `wiki/skills/.gitkeep`
- Create: `wiki/stories/.gitkeep`
- Create: `wiki/themes/.gitkeep`
- Create: `wiki/sentence-bank/.gitkeep`
- Create: `outputs/general/.gitkeep`
- Create: `outputs/custom/.gitkeep`

- [ ] **Step 1: Verify the repository root is still the expected empty workspace**

Run:

```bash
pwd
ls -la
```

Expected: current directory is `/Users/choiho/Desktop/carrer-wiki` and only the previously created `docs/` tree may exist.

- [ ] **Step 2: Create the directory skeleton**

Run:

```bash
mkdir -p raw/awards raw/bios raw/experiences raw/projects raw/links
mkdir -p wiki/overview wiki/experiences wiki/projects wiki/awards wiki/skills wiki/stories wiki/themes wiki/sentence-bank
mkdir -p outputs/general outputs/custom
```

Expected: all target directories exist with no errors.

- [ ] **Step 3: Create placeholder keep files for empty directories**

Use `apply_patch` to add the following empty files:

```diff
*** Begin Patch
*** Add File: /Users/choiho/Desktop/carrer-wiki/raw/awards/.gitkeep
+
*** Add File: /Users/choiho/Desktop/carrer-wiki/raw/bios/.gitkeep
+
*** Add File: /Users/choiho/Desktop/carrer-wiki/raw/experiences/.gitkeep
+
*** Add File: /Users/choiho/Desktop/carrer-wiki/raw/projects/.gitkeep
+
*** Add File: /Users/choiho/Desktop/carrer-wiki/raw/links/.gitkeep
+
*** Add File: /Users/choiho/Desktop/carrer-wiki/wiki/overview/.gitkeep
+
*** Add File: /Users/choiho/Desktop/carrer-wiki/wiki/experiences/.gitkeep
+
*** Add File: /Users/choiho/Desktop/carrer-wiki/wiki/projects/.gitkeep
+
*** Add File: /Users/choiho/Desktop/carrer-wiki/wiki/awards/.gitkeep
+
*** Add File: /Users/choiho/Desktop/carrer-wiki/wiki/skills/.gitkeep
+
*** Add File: /Users/choiho/Desktop/carrer-wiki/wiki/stories/.gitkeep
+
*** Add File: /Users/choiho/Desktop/carrer-wiki/wiki/themes/.gitkeep
+
*** Add File: /Users/choiho/Desktop/carrer-wiki/wiki/sentence-bank/.gitkeep
+
*** Add File: /Users/choiho/Desktop/carrer-wiki/outputs/general/.gitkeep
+
*** Add File: /Users/choiho/Desktop/carrer-wiki/outputs/custom/.gitkeep
+
*** End Patch
```

- [ ] **Step 4: Verify the directory tree**

Run:

```bash
find raw wiki outputs -maxdepth 2 | sort
```

Expected: the output lists every created directory and `.gitkeep` file under the intended paths.

- [ ] **Step 5: Commit**

If the repository has already been initialized as Git:

```bash
git add raw wiki outputs
git commit -m "chore: scaffold career wiki directories"
```

Expected: commit succeeds.

If Git is not initialized yet, skip commit and record that fact in the execution notes.

### Task 2: Write AGENTS.md Operating Rules

**Files:**
- Create: `AGENTS.md`
- Reference: `docs/superpowers/specs/2026-05-10-career-wiki-design.md`

- [ ] **Step 1: Write the file with the repository contract**

Use `apply_patch` to create `AGENTS.md` with this exact content:

```md
# Career Wiki Agent Guide

## Purpose

이 저장소는 채용 지원용 커리어 위키다. 원천 자료를 구조화된 경력 지식으로 정리하고, 그 지식을 바탕으로 범용 이력서/포트폴리오와 회사별 맞춤 지원 패키지를 생성한다.

## Layers

### raw/

- 원천 자료 저장소다.
- 수상경력, 자기소개 조각, 경력 사실, 프로젝트 링크와 소개, 성과 메모를 저장한다.
- 사실 원형을 보존하고 덮어쓰기보다 추가를 우선한다.

### wiki/

- LLM이 유지하는 정규화 지식 계층이다.
- 경험, 프로젝트, 수상, 기술, 스토리, 강점, 문장 뱅크를 관리한다.
- 직접 제출하지 않는 중간 컴파일 결과물이다.

### outputs/

- 제출 가능한 문서를 저장한다.
- 범용본은 `outputs/general/`에 보관한다.
- 회사별 맞춤본은 `outputs/custom/YYYY-MM-DD-company/`에 보관한다.

## Standard Output Files

### General

- `outputs/general/resume-general-v1.md`
- `outputs/general/resume-general-v2.md`
- `outputs/general/portfolio-general-v1.md`
- `outputs/general/portfolio-general-v2.md`

### Company-specific package

Each company folder must contain:

- `jd.md`
- `analysis.md`
- `strategy.md`
- `resume.md`
- `portfolio.md`

## Workflows

### Ingest

1. 새 자료를 `raw/`의 적절한 위치에 저장한다.
2. 관련 `wiki/` 페이지가 있는지 먼저 확인한다.
3. 핵심 사실, 수치, 재사용 가능한 문장을 추출한다.
4. 관련 `wiki/` 페이지와 `wiki/sentence-bank/`, `wiki/stories/`를 업데이트한다.
5. `index.md`를 갱신한다.
6. `log.md`에 ingest 항목을 append 한다.

### Build General Outputs

1. `wiki/themes/`, `wiki/stories/`, `wiki/sentence-bank/`를 우선 읽는다.
2. 전달하려는 포지셔닝에 맞게 문장을 선택한다.
3. 해당 범용 산출물 파일을 갱신한다.
4. `log.md`에 변경 이유를 기록한다.

### Build Company-Specific Outputs

1. `outputs/custom/YYYY-MM-DD-company/` 디렉터리를 만든다.
2. `jd.md`에 JD 원문 또는 요약을 저장한다.
3. `analysis.md`에 요구사항과 키워드를 정리한다.
4. `strategy.md`에 강조 포인트와 제외 포인트를 정리한다.
5. `resume.md`와 `portfolio.md`를 생성한다.
6. 새롭게 정리된 강점이나 문장은 `wiki/`에 역반영한다.
7. `log.md`에 output 항목을 append 한다.

### Query

- 질문에 답하기 전에 `index.md`를 먼저 읽는다.
- 관련 `wiki/` 페이지를 읽고 합성한다.
- 가치 있는 분석 결과는 새 위키 페이지나 산출물로 저장할 수 있다.

### Lint

- 고아 페이지를 찾는다.
- 중복된 프로젝트 설명을 찾는다.
- 상충되는 수치나 사실을 찾는다.
- 반복적으로 쓰이는 강점인데 독립 페이지가 없는 경우를 찾는다.
- 원천 자료 대비 업데이트가 누락된 페이지를 찾는다.

## Writing Rules

- 기본 언어는 한국어다.
- 사실과 해석을 섞지 않는다.
- 같은 내용을 여러 산출물에 직접 복붙하지 않는다. 먼저 `wiki/`를 갱신하고 산출물을 다시 만든다.
- 회사명은 가능하면 ASCII 소문자 slug를 사용한다.
- 맞춤본은 반드시 디렉터리 단위로 관리한다.

## Index and Log

### index.md

- 위키의 주요 페이지를 분류별 링크와 한 줄 설명으로 정리한다.
- 새 페이지를 만들거나 중요한 구조 변경이 있으면 함께 갱신한다.

### log.md

- append-only 파일로 유지한다.
- 각 항목은 아래 형식을 따른다.

```md
## [2026-05-10] ingest | 프로젝트 foo 소개 추가
## [2026-05-10] output | 2026-05-10-openai 맞춤 이력서 생성
## [2026-05-10] lint | stories 고아 페이지 점검
```
```

- [ ] **Step 2: Verify the file exists and includes all mandatory sections**

Run:

```bash
rg -n "^## Purpose|^## Layers|^## Workflows|^## Writing Rules|^## Index and Log" AGENTS.md
```

Expected: one match per required section.

- [ ] **Step 3: Commit**

If Git is initialized:

```bash
git add AGENTS.md
git commit -m "docs: add career wiki agent guide"
```

Expected: commit succeeds.

If Git is not initialized yet, skip commit and record that fact in the execution notes.

### Task 3: Create index.md and log.md Templates

**Files:**
- Create: `index.md`
- Create: `log.md`

- [ ] **Step 1: Create `index.md` template**

Use `apply_patch` to create `index.md` with this exact content:

```md
# Career Wiki Index

## Overview

- [Career Wiki Design](docs/superpowers/specs/2026-05-10-career-wiki-design.md) - 커리어 위키의 구조와 운영 원칙

## Raw Sources

### Awards

### Bios

### Experiences

### Projects

### Links

## Wiki

### Overview

### Experiences

### Projects

### Awards

### Skills

### Stories

### Themes

### Sentence Bank

## Outputs

### General

- [resume-general-v1](outputs/general/resume-general-v1.md) - 범용 이력서 버전 1
- [resume-general-v2](outputs/general/resume-general-v2.md) - 범용 이력서 버전 2
- [portfolio-general-v1](outputs/general/portfolio-general-v1.md) - 범용 포트폴리오 버전 1
- [portfolio-general-v2](outputs/general/portfolio-general-v2.md) - 범용 포트폴리오 버전 2

### Custom

- 회사별 맞춤 패키지는 `outputs/custom/` 아래에 `YYYY-MM-DD-company/` 형식으로 추가
```

- [ ] **Step 2: Create `log.md` template**

Use `apply_patch` to create `log.md` with this exact content:

```md
# Career Wiki Log

## [2026-05-10] init | initial design spec created

- Added the first design spec for the career wiki.
- Defined the three-layer structure: raw, wiki, outputs.
```

- [ ] **Step 3: Verify both files render as expected**

Run:

```bash
sed -n '1,220p' index.md
sed -n '1,120p' log.md
```

Expected: `index.md` includes all top-level sections and `log.md` includes a single initial entry.

- [ ] **Step 4: Commit**

If Git is initialized:

```bash
git add index.md log.md
git commit -m "docs: add career wiki index and log templates"
```

Expected: commit succeeds.

If Git is not initialized yet, skip commit and record that fact in the execution notes.

### Task 4: Create General Output Templates

**Files:**
- Create: `outputs/general/resume-general-v1.md`
- Create: `outputs/general/resume-general-v2.md`
- Create: `outputs/general/portfolio-general-v1.md`
- Create: `outputs/general/portfolio-general-v2.md`

- [ ] **Step 1: Create the general resume templates**

Use `apply_patch` to create `outputs/general/resume-general-v1.md` with this content:

```md
# General Resume v1

## Summary

-

## Experience Highlights

-

## Projects

-

## Awards

-

## Skills

-
```

Use `apply_patch` to create `outputs/general/resume-general-v2.md` with this content:

```md
# General Resume v2

## Positioning

-

## Core Impact

-

## Selected Experience

-

## Selected Projects

-

## Skills

-
```

- [ ] **Step 2: Create the general portfolio templates**

Use `apply_patch` to create `outputs/general/portfolio-general-v1.md` with this content:

```md
# General Portfolio v1

## Profile

-

## Featured Projects

-

## Case Studies

-

## Awards and Activities

-
```

Use `apply_patch` to create `outputs/general/portfolio-general-v2.md` with this content:

```md
# General Portfolio v2

## Narrative

-

## Strengths

-

## Project Stories

-

## Proof

-
```

- [ ] **Step 3: Verify the files exist**

Run:

```bash
find outputs/general -maxdepth 1 -type f | sort
```

Expected: output includes the four general markdown templates and `.gitkeep`.

- [ ] **Step 4: Commit**

If Git is initialized:

```bash
git add outputs/general
git commit -m "docs: add general resume and portfolio templates"
```

Expected: commit succeeds.

If Git is not initialized yet, skip commit and record that fact in the execution notes.

### Task 5: Add First Wiki Seed Pages

**Files:**
- Create: `wiki/overview/career-overview.md`
- Create: `wiki/themes/positioning.md`
- Create: `wiki/sentence-bank/resume-bullets.md`
- Create: `wiki/stories/story-bank.md`

- [ ] **Step 1: Create `career-overview.md`**

Use `apply_patch` to create `wiki/overview/career-overview.md` with this content:

```md
# Career Overview

## Current Positioning

- 아직 정리 전

## Core Themes

- 아직 정리 전

## Priority Evidence to Ingest

- 수상경력
- 자기소개 조각
- 프로젝트 링크와 소개
- 경력 사실과 성과 수치
```

- [ ] **Step 2: Create the seed theme and reusable content pages**

Use `apply_patch` to create `wiki/themes/positioning.md` with this content:

```md
# Positioning

## Main Narrative

- 아직 정리 전

## Target Roles

- 아직 정리 전

## Repeated Strengths

- 아직 정리 전
```

Use `apply_patch` to create `wiki/sentence-bank/resume-bullets.md` with this content:

```md
# Resume Bullets

## Reusable Bullets

- 아직 정리 전
```

Use `apply_patch` to create `wiki/stories/story-bank.md` with this content:

```md
# Story Bank

## STAR Stories

- 아직 정리 전
```

- [ ] **Step 3: Add the seed pages to `index.md`**

Use `apply_patch` to update the `Wiki` section of `index.md` so it contains these lines:

```md
### Overview

- [career-overview](wiki/overview/career-overview.md) - 현재 커리어 포지셔닝과 우선 ingest 대상

### Stories

- [story-bank](wiki/stories/story-bank.md) - 면접과 자기소개에 재사용할 STAR 스토리 모음

### Themes

- [positioning](wiki/themes/positioning.md) - 목표 역할과 반복 강점 정리

### Sentence Bank

- [resume-bullets](wiki/sentence-bank/resume-bullets.md) - 재사용 가능한 이력서 bullet 초안
```

- [ ] **Step 4: Verify the seed pages and index references**

Run:

```bash
rg -n "career-overview|story-bank|positioning|resume-bullets" index.md wiki
```

Expected: matches appear in both `index.md` and the corresponding page files.

- [ ] **Step 5: Commit**

If Git is initialized:

```bash
git add wiki index.md
git commit -m "docs: add initial career wiki seed pages"
```

Expected: commit succeeds.

If Git is not initialized yet, skip commit and record that fact in the execution notes.

### Task 6: Optional Git Initialization

**Files:**
- Modify: repository metadata only if the user wants Git enabled

- [ ] **Step 1: Check whether Git is already initialized**

Run:

```bash
git rev-parse --is-inside-work-tree
```

Expected: either `true` or an error saying the directory is not a Git repository.

- [ ] **Step 2: Initialize Git only if the user wants version control enabled now**

Run:

```bash
git init
```

Expected: `.git/` directory is created and the repository is initialized on the default branch.

- [ ] **Step 3: Create the first repository commit**

Run:

```bash
git add .
git commit -m "chore: initialize career wiki"
```

Expected: initial commit succeeds and includes the spec, templates, and directory scaffold.

- [ ] **Step 4: Verify repository status is clean**

Run:

```bash
git status --short
```

Expected: no output.

This task is optional because the current workspace is not yet a Git repository. Skip the task if the user does not want Git initialized now.
