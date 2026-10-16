# CHANGELOG

## 2026-10-16 — 초기 구축 (41 commits)

### 기반
- `4c8c35b` 빈 레포에 제로빌드 구조 수립 (`data.md`+`render.md`+`style.md`+엔진)
- CDN 핀 고정 (`js-yaml@4.1.0`, `marked@15.0.12`), 정규식·플레이스홀더 버그 수정
- `5682d42` MiniMorph 전역 규칙 준용 `AGENTS.md` + `.env` 컨벤션
- Pages 배포 (`main`, `.nojekyll`), `https://shiene1010.github.io/md-bento/` 라이브

### 데이터 (Shiene1010 실데이터)
- `e1c65b6` minimal-light 참고 → iOS/Service Dev + 당근모임 2개로 정체성 전환
- `b8ff7f6` 링크 인벤토리 완성 (GitHub·블로거·네이버·SNS 4종·메일 2개·당근)
- `c72b2e0` News·Publications를 GitHub 최근 활동·Pages 3건으로 교체
- `a9a2136` The Work를 실레포 3종으로 교체; `feb0677` youngest.dev 이식 명시
- 캐치프레이즈 확정: "I talk, Agents token — in Markdown." (`61790e6`)

### 디자인
- Montserrat + Pretendard (Fraunces 제외), ink/parchment/gold 토큰
- The Work: 리스트 → 벤토카드 → 윈도우형 카드 (도트+DETAILS+구분선+pill, 260px, 가로 snap)
- 03 섹션: 표 → 벤토그리드 → 데이터 주도 SVG 노드-엣지 그래프 (클러스터 스포트라이트)
- 히어로: 타이핑 캐치프레이즈 + 토큰 이코노믹스 차트 (I 노드·토큰 3궤도·막대 5개·동기 애니메이션, CSS only)
- 뷰 리듬 통일 (`.view` 88px) + 앵커 `scroll-margin`

### 에셋·정리
- `f4a3c4d` 아바타 (brandingMe), `6128a70` 파비콘 (`/favicon.ico` 자동 인식)
- `95e1114`·`49ec956` data/style 정리 + 디자인 시스템 문서화
- 렌더 규칙 3종을 `AGENTS.md`에 기록 (div 빈 줄, 단일 패스, css 펜스 금지어)
