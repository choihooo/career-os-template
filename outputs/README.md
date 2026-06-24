# Output Layer

`outputs/`는 제출 가능한 이력서와 제출 직전 markdown 원본을 저장하는 Output layer다. 현재 범위는 resume-only다.

## General Resume

- Source of truth: `outputs/general/source/resume.md`
- Optional rendered files:
  - `outputs/general/final/resume.html`
  - `outputs/general/final/resume.pdf`

## Company-specific Resume

회사별 폴더는 아래 구조를 따른다.

```text
outputs/custom/YYYY-MM-DD-company-role/
├── source/
│   ├── jd.md
│   ├── brief.md
│   └── resume.md
├── research/
│   ├── company.md
│   └── signals.md
└── final/
    ├── resume.html
    └── resume.pdf
```

`research/`와 `final/`은 필요할 때만 생성한다.

## Rules

- `source/`가 source of truth다.
- `final/`은 검수, 공유, 제출용 렌더 결과다.
- output에서 새 사실을 만들지 않는다. 새 사실은 `raw/`와 `wiki/`로 역반영한 뒤 다시 조립한다.
- 포트폴리오 산출물은 현재 scope에 포함하지 않는다.
