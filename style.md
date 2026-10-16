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
.hero { min-height: 100svh; display: flex; flex-direction: column; justify-content: flex-end; padding-top: 140px; padding-bottom: 80px; }
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
.reveal { opacity: 0; transform: translateY(28px); transition: opacity 0.8s ease, transform 0.8s ease; }
.reveal.visible { opacity: 1; transform: none; }
@media (max-width: 640px) {
  .band { padding: 88px 0; }
  .foot-grid { grid-template-columns: 1fr; }
}
```

## 토큰 설명

- `ink / ink-2`: 배경. `parchment`: 본문. `gold`: 포인트(eyebrow, 인용선, 티커 점).
- `Montserrat`(제목 display) + `Inter`(본문) + `IBM Plex Mono`(라벨) + `Pretendard Variable`(한글, CDN). 한글은 라틴 폰트에 없는 글리프라 자동 폴백된다.
- 섹션 여백: 데스크탑 `140px`, 모바일 `88px`. `max-width: 1240px`.
