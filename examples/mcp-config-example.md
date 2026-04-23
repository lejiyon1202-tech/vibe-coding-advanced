# MCP 서버 설정 실습 예시
# 바이브 코딩 고급 교육 — Part 2 실습 템플릿

---

## 📋 MCP(Model Context Protocol) 연동 실습

MCP로 Claude Code에 외부 도구를 연결하는 방법을 실습합니다.

---

## 🔌 기본 설정 방법

### 방법 1: 명령어로 추가 (권장)

```bash
# GitHub 서버 추가 (project 범위 — 이 프로젝트에만 적용)
claude mcp add github --scope project

# Slack 서버 추가 (user 범위 — 내 모든 프로젝트에 적용)
claude mcp add slack --scope user

# 설정된 서버 목록 확인
claude mcp list

# 특정 서버 제거
claude mcp remove github
```

---

### 방법 2: settings.json 직접 편집

**파일 위치:** `.claude/settings.json` (프로젝트 범위)

```json
{
  "mcpServers": {
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_TOKEN": "ghp_your_token_here"
      }
    },
    "slack": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-slack"],
      "env": {
        "SLACK_BOT_TOKEN": "xoxb-your-token-here",
        "SLACK_TEAM_ID": "T0XXXXXXXXX"
      }
    }
  }
}
```

> ⚠️ **보안 주의**: 실제 토큰은 `.env` 파일에 저장하고, `settings.json`에는 환경변수 참조만 사용하세요!

---

## 🏢 휴넷 실무 활용 시나리오

### 시나리오 1: GitHub + Slack 연동

**상황**: 코드 리뷰 완료 시 자동으로 Slack 알림 발송

```bash
# Claude Code에게 요청:
"현재 PR #42에 대한 리뷰 코멘트를 확인하고,
 리뷰 완료되면 #개발팀 슬랙 채널에 알림 보내줘"
```

**필요 MCP 서버:**
- `github` — PR, 이슈, 코멘트 접근
- `slack` — 채널 메시지 발송

---

### 시나리오 2: Google Drive + Calendar 연동

**상황**: 교육 자료를 Drive에 올리고 일정에 자동 추가

```bash
# Claude Code에게 요청:
"오늘 작성한 교육 교안(index.html)을 
 Google Drive '2026년 교육자료' 폴더에 업로드하고,
 다음 주 화요일 교육 일정 캘린더에 링크 추가해줘"
```

**필요 MCP 서버:**
- `google-drive` — 파일 업로드/공유
- `google-calendar` — 일정 생성/수정

---

### 시나리오 3: DB 직접 조회

**상황**: 학습자 수강 데이터를 Claude에게 직접 분석 요청

```bash
# Claude Code에게 요청:
"학습관리 DB에서 이번 달 완료율이 50% 미만인 
 과정 목록과 원인 분석 리포트 작성해줘"
```

**필요 MCP 서버:**
- `postgres` 또는 `mysql` — DB 쿼리 실행

---

## 📊 MCP vs 기존 방식 비교

| 작업 | 기존 방식 | MCP 연동 후 |
|------|-----------|------------|
| PR 상태 확인 | GitHub 열기 → 클릭 → 복사 | Claude에게 말로 요청 |
| Slack 공지 | Slack 앱 → 채널 선택 → 작성 | "이 내용 #채널에 보내줘" |
| DB 조회 | SQL 작성 → 실행 → 결과 해석 | "OO 데이터 분석해줘" |
| Drive 업로드 | 드래그 앤 드롭 → 공유 설정 | "이 파일 폴더에 올려줘" |

---

## 🔒 보안 체크리스트 (MCP 설정 전 필수)

- [ ] API 토큰/키는 환경변수로만 관리 (하드코딩 금지)
- [ ] MCP 서버 scope를 필요한 범위로 제한 (user < project < local)
- [ ] 사용하지 않는 MCP 서버는 즉시 제거
- [ ] 팀 공유 설정 시 토큰 노출 여부 재확인
- [ ] 민감한 DB는 읽기 전용 계정으로만 연결

---

## ✏️ 실습 과제

**과제**: 본인이 매일 반복하는 도구 전환 작업 1가지를 MCP로 자동화하는 계획을 세워보세요.

1. 어떤 도구와 Claude를 연결하고 싶은가?
2. 어떤 반복 작업을 자동화할 수 있는가?
3. 필요한 MCP 서버는 무엇인가?
4. 보안 고려사항은 무엇인가?

---

> 💡 **팁**: MCP 서버 목록은 계속 늘어나고 있습니다.
> `claude mcp list` 또는 MCP 공식 서버 목록(3,000+)에서 필요한 서버를 찾아보세요!
