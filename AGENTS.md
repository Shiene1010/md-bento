# md-bento — Project Agent Guide

> Parent: `/Volumes/Crucial X6/Development/workspaces/MiniMorph/AGENTS.md` 가 최상위 지침서이다.
> 이 파일은 프로젝트固有 규칙만 정의하고, 충돌 시 Parent가 우선한다.

## 1. Path
- Project root: `/Volumes/Crucial X6/Development/workspaces/md-bento`
- 금지: `~/Development`, `/Users/mini/...` 내장 경로 사용 금지
- Live URL: `https://shiene1010.github.io/md-bento/` (GitHub Pages, branch `main`, root)

## 2. Security
- 키는 `.env`에만 저장. `.env.example`은 이름만. (이 프로젝트는 정적 사이트라 현재 시크릿 없음)
- 커밋 전: `git status --porcelain` + `git check-ignore -v .env`
- `youngest-dev.json`은 세션 덤프라 공개 배포 제외 (`.gitignore` 처리됨)

## 3. Setup & Verify
```sh
cd "/Volumes/Crucial X6/Development/workspaces/md-bento"
python3 -m http.server 8080
# http://localhost:8080 접속 (file:// 불가: fetch CORS)
```
- `node --check` 로 인라인 엔진 문법 확인 (엔진 추출 후)
- 수정 후 `render.md` 태그 균형 확인: `{% for %}`/`endfor`, `{% if %}`/`endif`

## 4. Project-specific rules
- stack: 제로빌드 정적 사이트. 빌드·번들러·테스트러너 없음. `index.html`은 고정 엔진이므로 내용 수정 금지.
- 콘텐츠는 `data.md` (YAML frontmatter, Shiene1010 실데이터) / 레이아웃은 `render.md` / 스타일은 `style.md`의 css 펜스만 수정.
- 템플릿 부분집합만 지원: `{{ a.b }}`, `| default('x')`, `{% for x in y.z %}`, `{% if x %}`. 중첩 for 가능, `else` 없음.
- CDN 핀: `js-yaml@4.1.0`, `marked@15.0.12`, Google Fonts (Montserrat+Inter+IBM Plex Mono), Pretendard Variable (jsdelivr). `https://jsdelivr.net` 같은 플레이스홀더 금지.
- `style.md` 산문 안에 ```` ```css ```` 문자열 금지 (엔진이 첫 css 펜스를 추출하므로 오추출됨).
- `render.md` 작성 규칙 (marked 특성): `<div>` 직후는 빈 줄 필수 (없으면 내부 마크다운이 원문 노출). 테이블 행의 `{% for %}`/`{% endfor %}`는 행과 같은 줄에 붙임 (사이 빈 줄이 생기면 테이블 깨짐).
- 배포 필수: `.nojekyll` 유지 (Jekyll이 `.md`를 가공하는 것을 방지). `assets/img/*.png`는 레포에 없어 깨짐 — 추가 전까지 Publications 이미지 broken이 정상.
