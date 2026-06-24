# Proof Map

이 파일은 proof ID와 raw source, claim의 연결을 관리한다.

## Proof Template

```md
## proof:<stable-id>

- Type: github | feedback | metric | screenshot | certificate | document | other
- Source: raw/...
- Related item:
- Supports claims:
  - claim:<stable-id>
- Evidence strength: high | medium | low
- Notes:
```

## Active Proofs

아직 등록된 proof가 없다. `cos-register-source`, `cos-ingest-github-repo`, `cos-ingest` 과정에서 추가한다.
