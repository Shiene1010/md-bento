# md-bento — Zero-Build Markdown Portfolio

Live: `https://shiene1010.github.io/md-bento/` · "I talk, Agents token — in Markdown."

빌드 없음. `data.md`만 고치면 홈페이지가 바뀐다. 규칙 전문은 `AGENTS.md`.

## 파일 역할

| 파일 | 역할 | 수정 |
| :--- | :--- | :--- |
| `data.md` | 콘텐츠 원본 (YAML frontmatter) | 자유롭게 수정 |
| `render.md` | 레이아웃 템플릿 (Jinja 부분집합) | 구조 변경 시만 |
| `style.md` | 스타일 원본 (css 펜스) + 디자인 시스템 문서 | 테마 변경 시 펜스만 |
| `index.html` | 고정 엔진 (fetch→YAML→template→marked) | 수정 금지 |
| `assets/img/` | `avatar.png`, `favicon.png` | 이미지 교체 시 |
| `.nojekyll` | Pages Jekyll 방지 (삭제 금지) | 손대지 않음 |

## 미리보기·배포·검증

```sh
python3 -m http.server 8080  # file:// 불가 (fetch CORS)
git push                      # main 푸시 → Pages 자동 배포 (약 1분)
```

- 템플릿 문법: `{{ a.b }}`, `| default('x')`, `{% for %}`, `{% if %}`. 값 안의 `{{ }}`는 재해석 안 됨
- marked 특성상 `<div>` 직후 빈 줄 필수, 카드 내부는 순수 HTML만
- 검증: `js-yaml`+`marked` 실파이프라인 렌더 후 태그 잔여·섹션·링크·div 균형 확인 (상세 절차는 세션 기록 참조)

## 데이터 출처

- 프로필·링크: 디스크 조사 + 사용자 제공 (유튜브 `@8Knockdowns`, 블로그 3종, SNS 4종, 메일 2개, 당근모임)
- News·Publications: GitHub 최근 활동·Pages 상위 3건 기준 수동 갱신 (자동화 없음)
- 디자인 원형: `youngest.dev` 리버스 엔지니어링 (`youngest-dev.json`은 로컬 전용, 배포 제외)
