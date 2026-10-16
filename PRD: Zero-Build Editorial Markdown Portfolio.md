
PRD: Zero-Build Editorial Markdown Portfolio (md-bento)


1. 개요 (Overview)

• 목적: 복잡한 빌드 파이프라인(Next.js/Astro)이나 무거운 프레임워크 없이, 순수 마크다운 파일(data.md + 제로 빌드 뷰어)만으로 youngest.dev 스타일의 에디토리얼·벤토 포트폴리오를 브라우저에 실시간 렌더링합니다.
• 핵심 철학: "작성한 원문(.md) 자체가 곧 완성된 웹페이지다." 파일만 수정하면 브라우저에서 즉시 반영됩니다.
• 타겟 사용자: 개발, 프로덕트, 글쓰기를 겸업하며 유지보수 비용을 0으로 수렴시키고 싶은 1인 메이커.

2. 시스템 아키텍처 (Architecture)

text
[ data.md ] (YAML + Markdown Content)
       │
       ▼  (Client-side Fetch or Zero-Config CDN Viewer)
[ index.html + Zero-Build Engine (예: Marked.js / Docsify / Github-style CSS) ]
       │
       ▼
[ Browser Rendering (Editorial Typography & Matrix Table) ]
Use code with caution.
• 제로 빌드 전략: 별도의 npm run build나 서버사이드 렌더링(SSR) 없이, 가벼운 단일 HTML 러너가 마크다운 파일을 로드하여 파싱합니다.
• 파일 구성:
	• data.md: 사용자의 프로필, 이력, 에세이, 매트릭스 데이터가 담긴 원본.
	• index.html: 마크다운을 읽어들여 style.css와 함께 브라우저에 그려주는 싱글 파일 엔진.
	• style.css: 에디토리얼 그리드, 타이포그래피, 다크모드를 정의하는 순수 CSS.

3. 기능 요구사항 (Functional Requirements)


FR-01: 데이터 분리 및 동적 주입

• data.md의 YAML Frontmatter와 본문 섹션을 클라이언트 혹은 경량 스크립트가 파싱하여 DOM에 매핑한다.
• data.md가 수정되면 새로고침만으로 전체 텍스트와 링크 테이블이 동기화된다.

FR-02: 에디토리얼 레이아웃 렌더링

• 최대 너비 700px 중앙 정렬 레이아웃을 강제하여 매거진 가독성을 확보한다.
• 01 — The Work 내 On the Build / Off the Build 구조를 뱃지(code span)와 함께 시각적으로 구분한다.
• 03 — Where the Work Lives 영역을 경계선이 최소화된 매트릭스 테이블로 표현한다.

FR-03: 인터랙티브 디테일 (<details>)

• 긴 로그, 새벽 인프라 회고, 아키텍처 원문은 네이티브 <details> 태그를 활용해 접고 펼칠 수 있게 지원한다.

FR-04: 반응형 및 다크모드

• 미디어쿼리(prefers-color-scheme)를 통해 라이트/다크모드를 자동 전환한다.
• 모바일 환경(max-width: 640px)에서 폰트 크기와 테이블 패딩이 자연스럽게 축소된다.

4. 비기능 요구사항 (Non-Functional Requirements)

• 로딩 속도: First Contentful Paint(FCP) 0.5초 이내 (CDN 캐시 및 제로 JS 원칙).
• 유지보수성: Git 저장소에 data.md만 푸시하면 끝나는 구조.
• 이식성: GitHub Profile README, Obsidian, 웹 브라우저 뷰어 어디서나 동일한 가독성 유지.