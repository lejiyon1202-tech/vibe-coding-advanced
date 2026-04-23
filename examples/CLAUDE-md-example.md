# CLAUDE.md 실습 예시 파일
# 바이브 코딩 고급 교육 — Part 2 실습 템플릿

---

## 📋 실습 1: 팀 CLAUDE.md 작성해보기

아래 템플릿을 복사해서 본인 프로젝트에 맞게 수정해 보세요.

---

### 🏢 조직 레벨 CLAUDE.md (전역 설정)
**파일 위치:** `~/CLAUDE.md`

```markdown
# 팀 공통 설정

## 나의 역할
나는 [팀명] 소속 [직책]이다.

## 커뮤니케이션 원칙
- 한국어로 답변
- 전문 용어 사용 시 짧은 설명 병기
- 결론 먼저, 근거 나중

## 절대 금지 사항
- 코드에 API 키 하드코딩 금지
- 주석 없는 복잡한 로직 금지
```

---

### 📁 프로젝트 레벨 CLAUDE.md (프로젝트 루트)
**파일 위치:** `~/projects/my-project/CLAUDE.md`

```markdown
# [프로젝트명] 설정

## 프로젝트 개요
- 목적: [프로젝트 목적 한 줄 요약]
- 기술 스택: Node.js + Express + SQLite
- 배포 환경: AWS EC2 (Ubuntu 22.04)

## 개발 규칙
- 커밋 메시지: `feat:`, `fix:`, `docs:` 접두어 필수
- PR 올리기 전 `npm test` 통과 확인
- 함수 길이 50줄 이하 권고

## 자주 쓰는 명령어
- 서버 시작: `npm start`
- 테스트 실행: `npm test`
- 배포: `./deploy.sh`

## 금지 사항
- `node_modules/` 직접 수정 금지
- `main` 브랜치 직접 push 금지
```

---

### 📂 서브폴더 레벨 CLAUDE.md (특정 폴더)
**파일 위치:** `~/projects/my-project/backend/CLAUDE.md`

```markdown
# 백엔드 서브폴더 설정

## 이 폴더의 역할
Express.js 서버 코드. API 엔드포인트, 미들웨어, DB 연결 담당.

## 코드 스타일
- async/await 사용 (콜백 금지)
- 에러 핸들링: try/catch + 중앙화된 에러 미들웨어
- 환경변수: .env 파일, process.env로만 접근

## 폴더 구조
```
backend/
├── routes/      ← API 라우터
├── services/    ← 비즈니스 로직
├── middleware/  ← 인증, 로깅, 에러 처리
└── models/      ← DB 모델
```

## 주의사항
이 폴더에서 Claude에게 코드 수정을 요청할 때:
반드시 "서비스 레이어에서 처리"하는 패턴 유지
```

---

## ✏️ 실습 과제

1. 본인 현재 프로젝트(또는 가상 프로젝트)의 `CLAUDE.md` 초안을 작성해 보세요.
2. 포함 항목:
   - 프로젝트 개요 (2~3줄)
   - 개발 규칙 (3가지 이상)
   - 자주 쓰는 명령어 (2가지 이상)
   - 금지 사항 (1가지 이상)
3. 작성 후 Claude Code에게 "이 CLAUDE.md를 기반으로 README.md 초안 작성해줘"라고 요청해 효과를 확인하세요.

---

> 💡 **팁**: CLAUDE.md는 Claude에게 보내는 '상시 지시서'입니다.
> 팀원이 매번 반복 설명하던 내용을 여기 한 번 써두면 끝!
