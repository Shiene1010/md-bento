# SPRINT — 디자인 리뷰 + 리팩토링

근거: 디자인 평가 리뷰 17항 + 리팩토링所见 6항. 완료조건은 pipe 테스트 갱신을 포함한다.

## Sprint 1 — done (2a6364d) — 치명 (실사용 품질)

- [x] D1 reduced-motion 완성: `.reveal`·ticker·그래프 트랜지션에 `animation:none;transition:none` (`style.md`)
- [x] D2 모바일 nav: 640px 이하 `flex-wrap` 또는 가로스크롤 (`render.md`+`style.md`)
- [x] D3 그래프 모바일 폴백: 640px 이하 리스트형 링크 목록으로 전환 (미디어쿼리 내 SVG 숨김 + HTML 리스트)

## Sprint 2 — done (3d9de40) — 데이터 정합

- [x] D4 표기 통일: `아영읽` vs `아이읽영` vs `아이들 영어원서 읽어주기` → 1개로 (노드명은 좌표 그대로)
- [x] D5 프레딩 링크 정본 1개 확정 + `danggn_*` 오타 키 정리 (`data.md`)
- [x] D6 당근모임 2건 org_url 정본 교체 (아영읽→daangn) (`data.md`)
- [x] D7 Origins 영문 부제 번역 + details 실원문 교체 (`render.md`+`data.md`)

## Sprint 3 — done — 완성도

- [x] D8 Publications 카드화 (Work 윈도우카드 재사용) 또는 섹션 격하
- [x] D9 a11y: alt 한글화·aria 한글화·`:focus-visible` 스타일
- [x] D11 SEO: title·description·OG·favicon link (엔진 1회 수정 + AGENTS.md 규칙 개정)
- [x] D12 Off pill 라벨 체계 통일 · D13 띄어쓰기 · D14 utm 제거 (`data.md`)
- [x] R3 `favicon.png` 원본 보관 위치 확정 (`assets/src/` 이동 또는 삭제)

## Backlog

- D16 히어로 애니 감량 · D17 서체 이탈 명시 · footer mailto 마스킹
- R1 검증 스크립트 저장소 편입 (`scripts/verify/`, npm 절차 포함)
- R2 `PRD: ... .md` 콜론 파일명 개명 (`PRD.md`)
- R4 contacts 단일화 — 엔진 재귀 렌더 전제, 보류 (기각 가능)
