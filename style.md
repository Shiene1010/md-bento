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
  moss: "#4B5D4E"
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

# Style — youngest.dev editorial dark

> 색/폰트/여백을 바꾸고 싶으면 아래 `css` 펜스만 수정. `index.html`은 손대지 않는다.

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
.hero img[alt="avatar"] { width: 96px; height: 96px; border-radius: 50%; object-fit: cover; border: 1px solid var(--rule); }
.work-card { gap: 0.5rem; }
.work-tags { display: flex; flex-wrap: wrap; gap: 0.3rem; }
.work-detail { color: var(--parchment-dim); font-size: 0.88rem; }
.work-link {
  margin-top: auto; padding-top: 0; align-self: flex-start;
  display: inline-block; border: 1.5px solid var(--gold); color: var(--gold);
  border-radius: 999px; padding: 0.35rem 1rem; font-size: 0.88rem; font-weight: 600;
  text-decoration: none; transition: background 0.25s ease;
}
.work-link:hover { background: rgba(201, 162, 39, 0.12); }
.work-art { align-items: center; justify-content: center; }
.work-art svg { width: 100%; height: auto; max-height: 150px; }
.window-bar { display: flex; align-items: center; gap: 0.45rem; }
.window-bar .dot { width: 10px; height: 10px; border-radius: 50%; }
.dot.gold { background: var(--gold); }
.dot.moss { background: var(--moss-light); }
.dot.muted { background: var(--muted); }
.window-title { margin-left: 0.4rem; font-family: 'IBM Plex Mono', monospace; font-size: 0.78rem; letter-spacing: 0.14em; text-transform: uppercase; color: var(--muted); }
.window-rule { border: none; border-top: 1px solid var(--rule); margin: 0.2rem 0 0.6rem; width: 100%; }
.window-body { flex: 1; display: flex; align-items: center; }
.window-body svg { width: 100%; height: auto; }
.meet-art { position: relative; overflow: hidden; justify-content: flex-end; }
.meet-bg { position: absolute; right: -30px; bottom: -10px; width: 78%; opacity: 0.3; pointer-events: none; }
.meet-art .work-link { position: relative; }
.work-scroll {
  display: flex; gap: 1rem;
  overflow-x: auto; scroll-snap-type: x mandatory; padding-bottom: 0.75rem;
}
.work-scroll .bento-card { flex: 0 0 300px; scroll-snap-align: start; min-height: 300px; }
.ticker { border-top: 1px solid var(--rule); border-bottom: 1px solid var(--rule); overflow: hidden; white-space: nowrap; }
.ticker-track { display: inline-block; padding: 14px 0; animation: scroll-left 32s linear infinite; }
.ticker-track span { margin-right: 0.8em; font-family: 'IBM Plex Mono', monospace; font-size: 13px; letter-spacing: 0.18em; text-transform: uppercase; }
.dot { color: var(--gold); }
@keyframes scroll-left { to { transform: translateX(-50%); } }
.band { background: var(--ink-2); padding: 140px 0; margin-top: 88px; }
blockquote { border-left: 2px solid var(--gold); margin: 1.2rem 0; padding-left: 1rem; color: var(--parchment-dim); font-style: italic; }
code { font-family: 'IBM Plex Mono', monospace; font-size: 0.78em; background: rgba(243,238,227,0.08); padding: 2px 6px; border-radius: 4px; }
table { width: 100%; border-collapse: collapse; margin: 1.5rem 0; font-size: 0.92rem; }
th, td { padding: 0.7rem 0.5rem; text-align: left; border-bottom: 1px solid var(--rule); }
details { border: 1px solid var(--rule); border-radius: 8px; padding: 0.9rem 1rem; margin: 1rem 0; }
summary { cursor: pointer; }
.quote { text-align: center; padding: 120px 0 40px 0; }
.quote blockquote { border: none; font-size: clamp(24px, 4vw, 44px); font-family: 'Montserrat', 'Pretendard Variable', 'Pretendard', sans-serif; font-weight: 600; }
.footer { padding: 88px 0 60px 0; border-top: 1px solid var(--rule); }
.foot-grid { display: grid; grid-template-columns: 1.2fr 1fr 1fr; gap: 2rem; }
.bento-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1rem; margin: 1.5rem 0; }
.bento-card:first-child { grid-column: span 2; }
.bento-card {
  position: relative; display: flex; flex-direction: column; gap: 0.3rem;
  border: 1px solid var(--rule); border-radius: 12px; padding: 1.2rem 1.2rem 1.1rem;
  text-decoration: none; transition: border-color 0.25s ease, transform 0.25s ease;
}
.bento-card:hover { border-color: var(--gold); transform: translateY(-2px); }
.bento-title { font-family: 'Montserrat', 'Pretendard Variable', 'Pretendard', sans-serif; font-weight: 700; font-size: 1.1rem; }
.bento-role { color: var(--muted); font-size: 0.88rem; }
.bento-arrow { position: absolute; top: 1rem; right: 1.1rem; color: var(--gold); }
.net { position: relative; margin: 1.5rem 0; padding-left: 28px; }
.net::before {
  content: ""; position: absolute; left: 10px; top: 14px; bottom: 14px; width: 2px;
  background: linear-gradient(var(--gold), var(--moss-light), transparent);
}
.net-group { position: relative; padding: 0.7rem 0; }
.net-hub { display: flex; align-items: center; gap: 0.6rem; }
.net-dot {
  position: absolute; left: -23px; width: 10px; height: 10px; border-radius: 50%;
  background: var(--gold); box-shadow: 0 0 8px rgba(201, 162, 39, 0.6);
}
.net-nodes { display: flex; flex-wrap: wrap; gap: 0.5rem; margin-top: 0.55rem; }
.net-node {
  border: 1px solid var(--rule); border-radius: 999px; padding: 0.35rem 0.95rem;
  font-size: 0.9rem; text-decoration: none; transition: border-color 0.25s ease;
}
.net-node:hover { border-color: var(--gold); }
.reveal { opacity: 0; transform: translateY(28px); transition: opacity 0.8s ease, transform 0.8s ease; }
.reveal.visible { opacity: 1; transform: none; }
@media (max-width: 640px) {
  .band { padding: 88px 0; }
  .foot-grid { grid-template-columns: 1fr; }
  .bento-grid { grid-template-columns: 1fr; }
  .bento-card:first-child { grid-column: span 1; }
  .work-scroll .bento-card { flex-basis: 260px; }
}
```

## 토큰 설명

- `ink / ink-2`: 배경. `parchment`: 본문. `gold`: 포인트(eyebrow, 인용선, 티커 점).
- `Montserrat`(제목 display) + `Inter`(본문) + `IBM Plex Mono`(라벨) + `Pretendard Variable`(한글, CDN). 한글은 라틴 폰트에 없는 글리프라 자동 폴백된다.
- 섹션 여백: 데스크탑 `140px`, 모바일 `88px`. `max-width: 1240px`.
