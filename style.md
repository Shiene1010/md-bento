---
# style.md = 이 사이트의 스타일 소스. 이 파일만 바꾸면 전체 테마 변경.
# 엔진(index.html)이 아래 css 펜스를 추출해 그대로 주입한다.
# 토큰을 바꾸면 펜스 안 :root 변수도 같이 바꿔야 한다.
tokens:
  ink: "#10140F"
  ink_2: "#161C13"
  parchment: "#F3EEE3"
  parchment_dim: "#DCD6C7"
  gold: "#C9A227"
  gold_dim: "#8E7420"
  moss: "#4B5D4E"
  moss_light: "#7C8F7A"
  rule: "rgba(243, 238, 227, 0.14)"
  muted: "#9A9E92"
fonts:
  display: "Montserrat"
  sans: "Inter"
  mono: "IBM Plex Mono"
  korean: "Pretendard Variable (CDN)"
layout:
  max_width: "1240px"
  section_pad: "140px"
  section_pad_mobile: "88px"
---

# Design System — md-bento

> `index.html`은 손대지 않는다. 아래 css 펜스가 스타일 원본, 이 산문은 해설서다. 둘은 1:1로 유지한다.

## 1. 색상

| 토큰 | 값 | 용도 |
| :--- | :--- | :--- |
| `ink` | `#10140F` | 페이지 배경 |
| `ink-2` | `#161C13` | 밴드(Origins) 배경 |
| `parchment` | `#F3EEE3` | 본문 |
| `parchment-dim` | `#DCD6C7` | 부본문·요약·코드라인 |
| `gold` | `#C9A227` | 포인트: 라벨·인용선·티커점·링크·허브 |
| `gold-dim` | `#8E7420` | 예비 (저채도 포인트) |
| `moss` / `moss-light` | `#4B5D4E` / `#7C8F7A` | 그래프 리프 엣지·도트 |
| `rule` | `rgba(243,238,227,.14)` | 경계선·카드 테두리 |
| `muted` | `#9A9E92` | 보조 텍스트·뱃지·윈도우 타이틀 |

## 2. 타이포그래피

- Display `Montserrat` 700/800 (제목·카드명·인용), Body `Inter` (본문 1rem·1.65), Label `IBM Plex Mono` (eyebrow·태그·그래프 라벨), 한글 `Pretendard Variable` (CDN, 라틴 폰트 미보유 글리프 자동 폴백)
- 스케일: H1 `clamp(52px,10vw,148px)` / H2 `clamp(28px,4vw,44px)` / 인용 `clamp(24px,4vw,44px)`

## 3. 레이아웃

- `.wrap` 최대 1240px 중앙, 좌우 6vw. 섹션 여백 140px (모바일 88px). Hero 100svh 하단 정렬.

## 4. 컴포넌트

| 클래스 | 역할 |
| :--- | :--- |
| `nav` (fixed·difference) | 상단 메뉴, 스크롤 반전 |
| `hero` · `hero-bg` | 차트 라인 배경 + 아바타·타이틀 |
| `ticker` (32s 무한) | 키워드 스트립 |
| `work-scroll` (가로 snap) | On/Off 카드 행, 카드 260px 고정·동일 높이 |
| `bento-card` · `win-card` | 카드 베이스 + 윈도우형(도트·타이틀·구분선) |
| `work-link` (pill) | 노란 둥근 버튼, 카드 하단 우측 고정 |
| `window-bar` · `dot` · `window-rule` | 윈도우 크롬 |
| `meet-section` · `meet-section-bg` | 아치 배경 섹션 |
| `graph` · `cluster` · `e-hub/e-leaf` · `n-hub/n-leaf/n-center` | 노드-엣지 그래프 + 스포트라이트 |
| `band` | Origins band 배경 |
| `quote` · `footer` · `foot-grid` | 인용·푸터 3열 |

## 5. 모션

- `reveal` (IO 0.15, .8s 상승), 카드 호버 (gold 테두리 + 2px 상승, .25s), 그래프 클러스터 스포트라이트 (`:has`)

## 6. 동기화 규칙

- frontmatter `tokens` ↔ `:root` 1:1. 새 클래스 추가 시 §4에 한 줄. 펜스 시작 문자열을 산문에 쓰지 않는다 (추출 오작동).

```css
:root {
  --ink: #10140F;
  --ink-2: #161C13;
  --parchment: #F3EEE3;
  --parchment-dim: #DCD6C7;
  --gold: #C9A227;
  --gold-dim: #8E7420;
  --moss: #4B5D4E;
  --moss-light: #7C8F7A;
  --rule: rgba(243, 238, 227, 0.14);
  --muted: #9A9E92;
}
* { box-sizing: border-box; }
html { scroll-behavior: smooth; }
body {
  background: var(--ink);
  color: var(--parchment);
  font-family: 'Inter', 'Pretendard Variable', 'Pretendard', sans-serif;
  margin: 0; overflow-x: hidden;
}
.wrap { max-width: 1240px; margin: 0 auto; padding: 0 6vw; }
.eyebrow {
  font-family: 'IBM Plex Mono', monospace;
  font-size: 11px; letter-spacing: 0.22em;
  text-transform: uppercase; color: var(--gold);
}
h1 {
  font-family: 'Montserrat', 'Pretendard Variable', 'Pretendard', sans-serif;
  font-size: clamp(52px, 10vw, 148px);
  line-height: 0.95; font-weight: 700; margin: 0.4em 0; letter-spacing: -0.02em;
}
h2 {
  font-family: 'Montserrat', 'Pretendard Variable', 'Pretendard', sans-serif;
  font-size: clamp(28px, 4vw, 44px);
  font-weight: 700; margin: 0 0 1rem 0; letter-spacing: -0.01em;
}
h3 { font-size: 1.05rem; color: var(--parchment-dim); }
.tagline { font-size: 1.25rem; color: var(--parchment-dim); max-width: 34em; }
.typed { font-family: 'IBM Plex Mono', monospace; font-size: clamp(1rem, 2.4vw, 1.4rem); color: var(--gold); margin: 0 0 1rem; }
.typed span { display: inline-block; overflow: hidden; white-space: nowrap; vertical-align: bottom; max-width: 0; border-right: 2px solid var(--gold); animation: typing 3.2s steps(40) 0.6s forwards, caret 1s step-end infinite; }
@keyframes typing { to { max-width: 100%; } }
@keyframes caret { 50% { border-color: transparent; } }
@media (prefers-reduced-motion: reduce) { .typed span { animation: none; max-width: none; border: none; } }
.badge-bar { color: var(--muted); }
a { color: inherit; text-decoration: underline; text-underline-offset: 3px; }
.nav {
  position: fixed; top: 0; left: 0; right: 0; z-index: 50;
  mix-blend-mode: difference; color: #fff;
}
.nav-inner { display: flex; justify-content: space-between; align-items: center; padding-top: 26px; padding-bottom: 26px; }
.nav-links { display: flex; gap: 1.2rem; font-size: 0.9rem; }
.nav a { text-decoration: none; }
.hero { min-height: 100svh; display: flex; flex-direction: column; justify-content: flex-end; padding-top: 140px; padding-bottom: 80px; position: relative; overflow: hidden; }
.hero-bg { position: absolute; inset: 0; pointer-events: none; }
.hero-bg svg { width: 100%; height: 100%; display: block; }
.hero > *:not(.hero-bg) { position: relative; }
.tok-flow { animation: tokflow 1.2s linear infinite; }
@keyframes tokflow { to { stroke-dashoffset: -16; } }
.tok { transform-box: fill-box; transform-origin: center; offset-path: path('M110,250 C250,240 350,210 480,185'); animation: toktravel 3s linear infinite; }
.t1 { animation-delay: 0s; }
.t2 { animation-delay: 0.75s; }
.t3 { animation-delay: 1.5s; }
.t4 { animation-delay: 2.25s; }
@keyframes toktravel { 0% { offset-distance: 0%; scale: 0.6; opacity: 0.2; } 15% { opacity: 1; scale: 1.4; } 75% { opacity: 1; } 100% { offset-distance: 100%; scale: 0.7; opacity: 0.2; } }
.bars rect { transform-box: fill-box; transform-origin: bottom; animation: barpulse 3s ease-in-out infinite; }
.bars rect:nth-child(1) { animation-delay: 0s; }
.bars rect:nth-child(2) { animation-delay: 0.6s; }
.bars rect:nth-child(3) { animation-delay: 1.2s; }
.bars rect:nth-child(4) { animation-delay: 1.8s; }
.bars rect:nth-child(5) { animation-delay: 2.4s; }
@keyframes barpulse { 0%, 100% { transform: scaleY(0.4); } 30% { transform: scaleY(1.15); } 60% { transform: scaleY(0.6); } }
.curve-gold { animation: curvex 3s ease-in-out infinite; }
.curve-moss { animation: curvex 3s ease-in-out -1.5s infinite; }
@keyframes curvex { 0%, 100% { opacity: 0.3; } 50% { opacity: 0.6; } }
.i-ring { transform-box: fill-box; transform-origin: center; animation: ring 2s ease-out infinite; }
@keyframes ring { from { transform: scale(1); opacity: 0.8; } to { transform: scale(1.8); opacity: 0; } }
@media (prefers-reduced-motion: reduce) { .tok-flow, .tok, .bars rect, .curve-gold, .curve-moss, .i-ring { animation: none; } }
.hero img[alt="avatar"] { width: 96px; height: 96px; border-radius: 50%; object-fit: cover; border: 1px solid var(--rule); }
.work-card { gap: 0.5rem; }
.work-tags { display: flex; flex-wrap: wrap; gap: 0.3rem; }
.work-detail { color: var(--parchment-dim); font-size: 0.88rem; }
.work-link {
  margin-top: auto; align-self: flex-end;
  display: inline-block; border: 1.5px solid var(--gold); color: var(--gold);
  border-radius: 999px; padding: 0.35rem 1rem; font-size: 0.88rem; font-weight: 600;
  text-decoration: none; transition: background 0.25s ease;
}
.work-link:hover { background: rgba(201, 162, 39, 0.12); }
.window-bar { display: flex; align-items: center; gap: 0.45rem; }
.window-bar .dot { width: 10px; height: 10px; border-radius: 50%; }
.dot.gold { background: var(--gold); }
.dot.moss { background: var(--moss-light); }
.dot.muted { background: var(--muted); }
.window-title { margin-left: 0.4rem; font-family: 'IBM Plex Mono', monospace; font-size: 0.78rem; letter-spacing: 0.14em; text-transform: uppercase; color: var(--muted); }
.window-rule { border: none; border-top: 1px solid var(--rule); margin: 0.2rem 0 0.6rem; width: 100%; }
.meet-section { position: relative; padding: 1.5rem 0 0.5rem; }
.meet-section-bg { position: absolute; top: 0; right: 0; height: 100%; opacity: 0.18; pointer-events: none; }
.meet-section > *:not(.meet-section-bg) { position: relative; }
.work-scroll {
  display: flex; gap: 1rem;
  overflow-x: auto; scroll-snap-type: x mandatory; padding-bottom: 0.75rem;
}
.work-scroll .bento-card { flex: 0 0 260px; min-width: 0; scroll-snap-align: start; min-height: 260px; }
.ticker { border-top: 1px solid var(--rule); border-bottom: 1px solid var(--rule); overflow: hidden; white-space: nowrap; }
.ticker-track { display: inline-block; padding: 14px 0; animation: scroll-left 32s linear infinite; }
.ticker-track span { margin-right: 0.8em; font-family: 'IBM Plex Mono', monospace; font-size: 13px; letter-spacing: 0.18em; text-transform: uppercase; }
.dot { color: var(--gold); }
@keyframes scroll-left { to { transform: translateX(-50%); } }
.band { background: var(--ink-2); padding: 140px 0; margin-top: 88px; }
blockquote { border-left: 2px solid var(--gold); margin: 1.2rem 0; padding-left: 1rem; color: var(--parchment-dim); font-style: italic; }
code { font-family: 'IBM Plex Mono', monospace; font-size: 0.78em; background: rgba(243,238,227,0.08); padding: 2px 6px; border-radius: 4px; }
details { border: 1px solid var(--rule); border-radius: 8px; padding: 0.9rem 1rem; margin: 1rem 0; }
summary { cursor: pointer; }
.quote { text-align: center; padding: 120px 0 40px 0; }
.quote blockquote { border: none; font-size: clamp(24px, 4vw, 44px); font-family: 'Montserrat', 'Pretendard Variable', 'Pretendard', sans-serif; font-weight: 600; }
.footer { padding: 88px 0 60px 0; border-top: 1px solid var(--rule); }
.foot-grid { display: grid; grid-template-columns: 1.2fr 1fr 1fr; gap: 2rem; }
.bento-card {
  position: relative; display: flex; flex-direction: column; gap: 0.3rem;
  border: 1px solid var(--rule); border-radius: 12px; padding: 1rem 1rem 0.9rem;
  text-decoration: none; transition: border-color 0.25s ease, transform 0.25s ease;
}
.bento-card:hover { border-color: var(--gold); transform: translateY(-2px); }
.bento-title { font-family: 'Montserrat', 'Pretendard Variable', 'Pretendard', sans-serif; font-weight: 700; font-size: 1.1rem; overflow-wrap: break-word; min-width: 0; }
.bento-role { color: var(--muted); font-size: 0.88rem; }
.graph { width: 100%; height: auto; display: block; margin: 1.5rem 0; }
.e-hub { stroke: var(--gold); stroke-width: 1.5; opacity: 0.45; }
.e-leaf { stroke: var(--moss-light); stroke-width: 1.5; opacity: 0.5; }
.n-hub { fill: var(--gold); }
.n-leaf { fill: var(--parchment-dim); }
.n-center { fill: var(--gold); }
.n-hub-label { font-family: 'IBM Plex Mono', monospace; font-size: 11px; letter-spacing: 0.18em; fill: var(--gold); text-anchor: middle; text-transform: uppercase; }
.n-label { font-size: 12.5px; fill: var(--parchment); }
.n-center-label { font-size: 13px; font-weight: 600; fill: var(--parchment); text-anchor: middle; }
.graph a:hover .n-leaf { fill: var(--gold); }
.graph a { cursor: pointer; }
.cluster { transition: opacity 0.25s ease; }
.graph:has(.cluster:hover) .cluster:not(:hover) { opacity: 0.3; }
.cluster:hover .e-leaf { stroke: var(--gold); opacity: 0.9; }
.cluster:hover .e-hub { opacity: 1; }
.cluster:hover .n-leaf { fill: var(--gold); }
.e-leaf, .e-hub { transition: stroke-width 0.2s ease, opacity 0.25s ease; }
.e-leaf:hover, .e-hub:hover { stroke-width: 3; }
.n-leaf { transform-box: fill-box; transform-origin: center; transition: transform 0.2s ease, fill 0.25s ease; }
a:hover .n-leaf { transform: scale(1.6); }
.reveal { opacity: 0; transform: translateY(28px); transition: opacity 0.8s ease, transform 0.8s ease; }
.reveal.visible { opacity: 1; transform: none; }
@media (max-width: 640px) {
  .band { padding: 88px 0; }
  .foot-grid { grid-template-columns: 1fr; }
  .work-scroll .bento-card { flex-basis: 220px; }
}
```
