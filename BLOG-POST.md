# I talk, Agents token — in Markdown: md-bento 제작기

> 이 글은 구글 블로거·네이버 블로그·Voyager 공용 원본입니다. 플랫폼별로는 제목과 링크 형식만 맞춰 붙여넣으세요.

## 1. 뭘 만들었나

빌드 없는 포트폴리오 `md-bento` (https://shiene1010.github.io/md-bento/).
`data.md` 하나만 고치면 홈페이지가 바뀝니다. 사람이 md로 말하면 에이전트가 페이지로 짓는 구조입니다.

## 2. 구조 3줄 요약

- `data.md`: 콘텐츠 원본 (프로필·프로젝트·링크·뉴스)
- `render.md`: 레이아웃 템플릿 (Jinja 부분집합)
- `style.md`: 스타일 원본 (css 펜스) + 디자인 시스템 문서
- `index.html`은 고정 엔진. fetch 3파일 → YAML 파싱 → 템플릿 렌더 → marked 변환.

## 3. 핵심 결정 5개

1. youngest.dev 리버스 엔지니어링으로 원형 확보 (ink·parchment·gold 토큰 계승)
2. 서체는 의도적 차별화: Fraunces 대신 Montserrat + Pretendard (한글 병기 일관성)
3. The Work는 윈도우형 벤토카드 (도트+DETAILS+구분선+pill 버튼)
4. 링크 모음은 SVG 노드-엣지 그래프 (6허브·14리프, 클러스터 스포트라이트)
5. 히어로는 토큰 이코노믹스 차트 + 타이핑 캐치프레이즈 (CSS only, reduced-motion 대응)

## 4. 숫자

- 50+ 커밋, 1일 완성. 검증 파이프라인 44항목 PASS.
- 외부 JS는 marked·js-yaml CDN 핀 버전만. 빌드·번들러 없음.

## 5. 다음

- News·Publications 매주 1회 갱신. 검증 스크립트 저장소 편입은 백로그.
- "쓴 글이 곧 페이지가 된다"에서 "I talk, Agents token — in Markdown"으로. 말하는 쪽은 사람, 토큰 쓰는 쪽은 에이전트입니다.
