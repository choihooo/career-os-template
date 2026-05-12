# Sample Dashboard

## Identity

- Project: Sample Dashboard
- Period: 2025.07 - 2025.08
- Link: https://github.com/example/sample-dashboard
- Related raw source: `raw/projects/sample-dashboard.md`
- Related experience: none

## One-line Summary

운영자가 수동으로 합치던 지표를 필터와 차트가 있는 웹 대시보드로 확인하게 만든 샘플 프로젝트다.

## Context

- Problem: 여러 CSV와 문서를 오가며 주간 리포트를 만들어야 했다.
- Users or stakeholders: 내부 운영 담당자
- Constraints: 짧은 기간, 변경 가능한 API, 데스크톱 중심 사용

## My Role

- Role: Frontend Lead
- Ownership: 대시보드 UI, 필터 상태, 차트 시각화
- Collaborators: 기획, 디자인, 백엔드
- Decisions I made: 서버 상태와 URL 상태를 분리했다.

## Work Done

- Workstream: Data and Filter Flow
  - Action: TanStack Query와 URL query를 조합해 필터 상태를 공유 가능하게 만들었다.
  - Reason: 운영자가 같은 조건을 다시 재현하거나 공유해야 했다.
  - Tool or method: React, TypeScript, TanStack Query, Recharts
  - Tradeoff: 모바일 최적화보다 데스크톱 밀도를 우선했다.

## Result

- Metric: 리포트 작성 시간이 2시간에서 30분으로 줄었다는 피드백
- Qualitative outcome: 필터 공유와 재현이 쉬워졌다.
- Evidence: `raw/projects/sample-dashboard.md`
- Follow-up: 실제 사용 로그와 스크린샷이 필요하다.

## Reusable Output Material

### Resume Bullets

- TanStack Query와 URL query를 조합해 대시보드 필터 상태를 공유 가능하게 만들고, 주간 리포트 작성 시간을 2시간에서 30분으로 줄였다는 운영자 피드백을 받았다.

### Portfolio Case Study

- Hook: 운영자가 반복하던 리포트 작업을 재현 가능한 대시보드 흐름으로 바꿨다.
- Problem: 여러 파일을 오가며 지표를 확인해야 했다.
- Approach: 서버 상태, 필터 상태, 차트 시각화를 분리했다.
- Result: 리포트 작성 시간이 줄었다는 피드백을 받았다.
- Proof: 샘플 proof. 실제 링크로 교체해야 한다.

## Gaps

- Missing metric: 실제 사용 로그
- Missing link: 배포 URL
- Missing image: 대시보드 스크린샷
- Unclear role boundary: 실제 팀 기여 범위
