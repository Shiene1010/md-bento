# md-bento — Zero-Build Editorial Markdown Portfolio

> "정직하게 먼저 써 내려가고, 그에 맞는 실물을 만든다."  
> 복잡한 프레임워크 없이 `data.md` 하나로 완성하는 에디토리얼 벤토 포트폴리오.

## ✨ Features
* **Zero Build**: `npm run build` 없음. 마크다운 파일 그대로 브라우저에서 구동.
* **Editorial Typography**: Inter/Pretendard와 JetBrains Mono 조합의 잡지형 레이아웃.
* **Bento Matrix**: CSS Grid 대신 정갈한 마크다운 테이블 매트릭스 활용.
* **Auto Dark Mode**: 시스템 테마 자동 대응.

---

## 🚀 Quick Start (로컬 브라우저에서 바로 띄우기)

### 방법 1: VS Code Live Server로 실행
1. 이 레포지토리를 클론하거나 다운로드합니다.
2. `data.md`를 열어 본인 정보로 수정합니다.
3. VS Code에서 `index.html` 우클릭 -> **Open with Live Server** 선택.

### 방법 2: Python HTTP 서버로 즉시 확인
```bash
# 프로젝트 루트 폴더에서 실행
python3 -m http.server 8080
# 브라우저에서 http://localhost:8080 접속
```

### 방법 3: GitHub Pages / Vercel 정적 호스팅
* `index.html`, `data.md`, `style.css`를 그대로 루트에 올리고 GitHub Pages를 켭니다.

---

## 🛠️ Configuration (`data.md`)

문서 상단의 YAML 값과 본문을 본인 것으로 수정하세요:

```yaml
profile:
  name: "이름"
  role_title: "Builder · Engineer · Writer"
  hook: "한 줄 후크 메시지"
  status_badge: "🟢 Building & Writing"
```

* **01 — The Work**: `On the Build`(본업)와 `Off the Build`(사이드/글쓰기) 항목을 리스트 형식으로 작성합니다. 태그는 백틱(`` `BACKEND` ``)으로 감쌉니다.
* **02 — Origins**: 철학적 배경과 에세이를 적고, 긴 기술 로그는 `<details>` 태그로 묶습니다.
* **03 — Where the Work Lives**: 플랫폼 매트릭스 테이블에 주요 링크를 정리합니다.

---

## 📁 File Structure
```text
.
├── data.md       # 내 이력 및 콘텐츠 원본 (여기만 수정하면 됨)
├── index.html    # 마크다운 파서 및 레이아웃 런타임
├── style.css     # 에디토리얼 타이포그래피 & 벤토 스타일시트
└── README.md     # 설명서
```

## 📄 License
MIT
