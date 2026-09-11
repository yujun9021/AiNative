# AI-native 개발 공통 규칙

## 판단과 승인

- 판단 순서: 사용자 최신 결정 → 승인된 `intent` → `spec` → `plan` → 코드 → 증거
- 문서 역할: `intent`는 목적·범위, `spec`은 동작, `plan`은 구현·검사, `evidence`는 결과·인수
- 기본 순서: `intent → spec → plan → 구현 → evidence → 사용자 인수 → 커밋 → 종료`
- `plan` 승인 전에는 제품 코드를 수정하지 않는다.
- 개발환경 세팅은 총괄에서 확정·실행·검증한 뒤 작업 채팅을 시작한다.
- 도구 설치, 서비스 로그인·연결, 외부 서비스 생성은 승인된 plan에 명시하고 별도 실행 승인 후에만 한다.
- 배포는 사용자가 직접 수행하며 작업 채팅 범위에 포함하지 않는다.
- 승인, 로컬 검사, CI, 사용자 인수는 서로 구분해 기록한다.
- 작업은 사용자 인수 후 최종 커밋을 1회만 만든다.

## 상태

- `intent`, `spec`, `plan`: `draft` 또는 `approved`
- `evidence`: `draft`, `review`(사용자 인수 전), 또는 `done`(사용자 인수 후)
- ROADMAP 구성 승인: `pending` 또는 `approved`
- ROADMAP 작업: `pending`, `building`, `review`, 또는 `done`

## 작업 경계

- 한 작업 채팅은 하나의 `AN-xxx`만 담당한다.
- 다른 기능이나 공통 구조에 영향을 주는 변경은 구현을 멈추고 총괄 채팅에서 결정 후 진행한다.
- 별도 회의록·진행 보고서·에이전트별 보고서는 만들지 않는다.

## 문서 위치

- 총괄 채팅 절차: `docs/workflow/COORDINATOR.md`
- 작업 채팅 절차: `docs/workflow/WORK_CHAT.md`
- 작업 문서: `work/AN-xxx-slug/`
- 새 작업 템플릿: `work/_template/`
