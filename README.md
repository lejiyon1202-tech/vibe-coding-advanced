# 바이브 코딩 고급 교안 — 리더 대상

리더가 **Claude 앱 Projects + Skills** 및 **Claude Code CLI의 Skills / CLAUDE.md / Subagents / Hooks / MCP**를 실무에 바로 활용할 수 있도록 정리한 7시간 분량의 교안입니다. "이제 막 Claude Code를 써보기 시작한" 난이도에 맞춰, 개념 → 실습 → 실전 사례 → 보안 순으로 구성했습니다.

## 구성

| 파일 | 용도 |
|------|------|
| `index.html` | 교안 본문 (강사 진행용 HTML 슬라이드/웹 교재) |
| `org-diagram.svg` | 역할 기반 멀티 에이전트 조직 구조 다이어그램 |
| `assets/img-projects.svg` | Projects 지식 컨테이너 개념도 |
| `assets/img-skills.svg` | Skills Progressive Disclosure 3단계 |
| `assets/img-claudemd.svg` | CLAUDE.md 3계층 구조 |
| `assets/img-hooks.svg` | Hooks 이벤트·핸들러 자동 실행 플로우 |
| `assets/img-mcp.svg` | MCP 외부 서비스 연결 허브 |
| `examples/CLAUDE-md-example.md` | 전역/프로젝트/서브폴더 3계층 CLAUDE.md 템플릿 |
| `examples/skill-md-example.md` | Claude 앱 SKILL.md + Claude Code 슬래시 Skill 예시 |
| `examples/hook-settings-example.json` | PreToolUse·PostToolUse·Stop 등 Hook 설정 5종 예시 |
| `examples/mcp-config-example.md` | MCP 서버 연결 설정 + 업무 시나리오 |
| `examples/subagent-example.md` | 코드리뷰·HRD·데이터 분석 Subagent 예시 + 병렬 실행 패턴 |

## 실행 방법

1. 저장소 clone 후 `index.html`을 브라우저에서 열면 그대로 교안으로 사용할 수 있습니다.
2. `examples/` 폴더의 템플릿을 복사해 각자 프로젝트에 맞게 수정하면 바로 Skills·Hooks·Subagents·MCP 실습이 가능합니다.

## 교안 섹션

1. **Intro** — 바이브 코딩 2026 트렌드 + "앱 Projects vs CLI 프로젝트" 개념 비교표 + 7시간 일정
2. **Part 1** — Claude 앱 Projects & Skills (기획·문서·의사결정 지원)
3. **Part 2** — Claude Code CLI 심화 (CLAUDE.md / Skills / Hooks / Subagents / MCP)
4. **Part 3** — 멀티 에이전트 조직 실전 사례 (역할 기반·Gate 프로세스·최근 프로젝트 쇼케이스)
5. **통합 실습 워크숍** — 5개 시나리오 단계별 가이드
6. **보안 · 거버넌스** — 기밀정보·프롬프트 인젝션·MCP 권한·키 관리 6축
7. **마무리** — 요약 + 다음 단계 로드맵

## 라이선스 / 출처

- 본 교안 텍스트·구조: 내부 사용 목적.
- Part 1·2 근거: Anthropic 공식 Docs (`docs.claude.com`·`code.claude.com`).
- 이미지: 자체 제작 SVG (unDraw 블루 팔레트 기반 커스텀).
- 폰트: Pretendard (오픈 소스).
