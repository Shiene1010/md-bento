PRD: Zero-Build Markdown Portfolio (md-bento) — 구현상세서

Live: https://shiene1010.github.io/md-bento/ · 캐치프레이즈: "I talk, Agents token — in Markdown."

1. 개요 (Overview)

• 목적: 빌드 파이프라인 없이 `data.md` 하나 수정으로 갱신되는 1인 포트폴리오. 원형은 youngest.dev 리버스 엔지니어링 (根 파일: `youngest-dev.json`, 로컬 전용·배포 제외).
• 핵심 철학: "I talk, Agents token — in Markdown." 사람이 md로 말하면 에이전트가 페이지로 짓는다.
• 현실: 순수 md만으로 부족한 레이아웃·인터랙션은 `render.md`(구조 템플릿)+`style.md`(css 원본)가 담당. `index.html`은 고정 엔진으로 수정 금지.

2. 시스템 아키텍처 (As-Built)

[data.md: YAML frontmatter] ─┐
[render.md: Jinja 부분집합 템플릿] ─┼─▶ index.html 엔진 (fetch 3파일 → js-yaml 파싱 → 템플릿 렌더 → css 펜스 주입 → marked 파싱 → #content) ─▶ DOM
[style.md: ```css 펜스 + 해설 산문] ─┘

• CDN 핀: js-yaml@4.1.0, marked@15.0.12, Google Fonts (Montserrat+Inter+IBM Plex Mono), Pretendard Variable (jsdelivr).
• 렌더 순서상 `data.md` 본문은 비어 있고(YAML만), 최종 마크다운은 `render.md`×데이터 결합으로 생성된다.
• 템플릿 부분집합: `{{ a.b }}`, `| default('x')`, `{% for x in y.z %}`, `{% if x %}`. 중첩 for 가능, `else` 없음, 값 안의 `{{ }}`는 재해석 안 됨 (단일 패스).
• marked 특성상 `<div>` 직후 빈 줄 필수, 카드 내부는 순수 HTML만 (위반 시 원문 노출·`<p>` 오감김).

3. 데이터 스키마 (data.md)

profile(신원·메일·avatar) / hero(eyebrow·title·tagline·typed) / ticker(6) / nav(6: Work·Origins·Network·News·Publications·Contact) / contacts(17종 링크 인벤토리) / current_roles(4) / work_on_build(3)·work_off_build(3, 카드 슬롯 고정) / origins(인용+4문단+details) / link_groups(6허브·14리프, 그래프 좌표 hx/hy/x/y + left/right 포함) / news(3, GitHub 활동 수동 반영) / publications(3, Pages 수동 반영) / closing_quote.

4. 섹션·네비 (페이지 순서)

hero(`#top`, 타이핑 캐치프레이즈+토큰 차트) → 01 The Work(`#build`, On 가로 snap 윈도우카드 3 + Off Meet 윈도우카드 3) → 02 Origins(`#origins`, band) → 03 Where the Network Works(`#partners`, SVG 노드-엣지 그래프, 클러스터 스포트라이트) → 04 News(`#news`) → 05 Publications(`#publications`) → 인용 → footer(`#contact`). 전 뷰 `.view` 88px 리듬, 앵커 `scroll-margin-top: 90px`.

5. 디자인 시스템

• 토큰: ink #10140F / ink-2 #161C13 / parchment #F3EEE3 / gold #C9A227 / moss-light #7C8F7A / rule rgba / muted. 타이포 Montserrat 700/800 + Inter + IBM Plex Mono + Pretendard 폴백.
• 상호작용은 CSS only: 타이핑·토큰 3궤도 동기 애니메이션·그래프 `:has` 스포트라이트·reveal(IO 0.15). `prefers-reduced-motion` 시 정지.

6. 검증·배포·제약

• 검증: js-yaml+marked 실파이프라인 렌더 후 태그 잔여·섹션·링크·div 균형 확인 (37항목, 로컬 `/tmp/mdbtest`, 저장소 미포함).
• 배포: `main` 푸시 → GitHub Pages 자동 배포. `.nojekyll` 필수 (Jekyll의 md 가공 방지). `file://` 불가, http 서빙 필수.
• 제약: News·Publications 자동화 없음 (수동). Publications 썸네일 미보유 (`image` 키 제거됨). `assets/img/favicon.png`은 원본 보관용 (실사용은 루트 `favicon.ico`).
