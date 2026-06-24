# Claims Ledger

이 파일은 이력서와 면접 답변에 사용할 수 있는 claim을 관리한다. 강한 claim은 반드시 source page와 proof ID를 가진다.

## Claim Template

```md
## claim:<stable-id>

- Claim:
- Allowed use: resume | interview | brief
- Source pages:
  - raw/...
  - wiki/...
- Proof IDs:
  - proof:<stable-id>
- Confidence: high | medium | low
- Caveat:
```

## Active Claims

아직 등록된 claim이 없다. `cos-ingest`로 raw source를 승격할 때 추가한다.
