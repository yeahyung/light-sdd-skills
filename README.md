# light-sdd-skills

요구사항을 명세로 정리하고 Feature별 구현·검증과 처리 로직 설명에 사용하는 한국어 스킬 모음이다.

## 사용 순서

1. 명세: `$sdd-spec problem.md와 제공 자료로 spec.md를 작성해 줘. 총 180분이야.` 같은 세션에서 질의에 답하고, 답변·합의가 `spec.md`에 저장됐는지 확인한 뒤 대화를 초기화한다.
2. Feature별 구현: `$sdd-build spec.md의 F01만 구현·검증하고 결과와 자율 판단의 근거를 기록해 줘. 기존 Feature 기록은 보존해 줘.` 결과·진행 상태를 저장한 뒤 대화를 초기화하고 다음 F번호로 반복한다.
3. 최종 검증·설명: `$sdd-verify 원문·spec.md와 전체 구현·실행 결과를 대조하고, 각 Feature와 공통 완료 조건에 사용된 알고리즘·로직·주요 판단을 설명해 줘.`

## 구성

| 스킬 | 용도 |
|---|---|
| [sdd-spec](skills/sdd-spec/SKILL.md) | 명세 작성·갱신 |
| [sdd-build](skills/sdd-build/SKILL.md) | 구현·결과 보고 |
| [sdd-verify](skills/sdd-verify/SKILL.md) | 명세·구현·검증 결과 대조와 항목별 알고리즘·로직 설명 |

## 설치

`skills/` 안의 **3개 폴더**를 템플릿과 함께 대상 프로젝트의 스킬 경로에 복사한다. `skills/`를 한 단계 더 중첩하지 않는다. 기존 설치본은 비교·백업한 뒤 갱신한다.

| 대상 | 프로젝트 설치 위치 | 설치 후 파일 예 |
|---|---|---|
| Codex | `.agents/skills/` | `.agents/skills/sdd-spec/SKILL.md` |
| Claude Code | `.claude/skills/` | `.claude/skills/sdd-spec/SKILL.md` |

Codex CLI·IDE에서는 `$sdd-spec`처럼 호출한다. 인식되지 않으면 설치 경로를 확인하고 새 세션을 시작한다. 원격 환경은 해당 환경에 파일을 복사해야 한다. [Codex 안내](https://learn.chatgpt.com/docs/build-skills) · [Claude Code 안내](https://code.claude.com/docs/en/skills)

## 프로젝트 파일

| 파일 | 용도 |
|---|---|
| `problem.md` | 요구사항 입력 |
| `spec.md` | 명세와 구현 결과 |
| `result.md` | 명세가 없을 때 구현 결과 |

사용자가 지정한 파일명을 우선한다. 양식은 [spec.template.md](skills/sdd-spec/spec.template.md)와 [result.template.md](skills/sdd-build/result.template.md)를 참조한다.

## 배포 형태

각 스킬은 `SKILL.md`, `agents/openai.yaml`과 해당 템플릿으로 구성된다. 필수 외부 패키지·실행 스크립트·MCP 연결은 없다. ZIP을 사용할 때도 개별 스킬 폴더와 템플릿을 함께 복사한다.
