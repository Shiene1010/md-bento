---
# ==========================================
# [USER CONFIG] 이 파일만 수정하면 홈페이지 완성
# 원본 참고: https://shiene1010.github.io/minimal-light/
# 스타일 변경은 style.md, 레이아웃 변경은 render.md
# ==========================================
profile:
  name: "Shiene1010"
  slug: "shiene1010"
  role_title: "Service Dev · OpenCode · Muse Spark 1.3"
  hook: "OpenCode Muse Spark 1.3으로 서비스를 개발하는 사람"
  status_badge: "🌱 Muse Spark로 서비스 개발중"
  copyright_year: "2026"
  location: "Suwon, South Korea"
  avatar: "./assets/img/avatar.png"

hero:
  eyebrow: "Service Dev · Suwon, South Korea"
  title: "Shiene1010"
  tagline: "OpenCode로 서비스를 개발하고, 당근모임에서 아이들 영어원서로 읽어줍니다."

ticker:
  - "OpenCode"
  - "Muse Spark 1.3"
  - "Zero-Build"
  - "Kids English"
  - "Small Talk"
  - "GitHub Pages"

nav:
  - label: "Work"
    href: "#build"
  - label: "Origins"
    href: "#origins"
  - label: "Network"
    href: "#partners"
  - label: "News"
    href: "#news"
  - label: "Publications"
    href: "#publications"
  - label: "Contact"
    href: "#contact"

contacts:
  email: "whatwillmyversebe@naver.com"
  email_apple1: "whatwillmyversebe@icloud.com"
  github: "https://github.com/Shiene1010"
  blogger: "https://shiene1010.blogspot.com/"
  naver_blog: "https://blog.naver.com/whatiwillbeaverse"
  voyager: "https://shiene1010.github.io/voyager/"
  youtube: "https://www.youtube.com/@8Knockdowns"
  discord: "https://discord.gg/ef6YzwNA"
  steam: "https://steamcommunity.com/profiles/76561198355440490/"
  soundcloud: "https://soundcloud.com/whatwillmyversebe?ref=clipboard&p=i&c=1&si=F690524B20EF4A8EBC04F16BAAB5AFD9&utm_source=clipboard&utm_medium=text&utm_campaign=social_sharing"
  facebook: "https://www.facebook.com/headtometa"
  instagram: "https://www.instagram.com/headtometa/"
  threads: "https://www.threads.com/@8knockdowns"
  x: "https://x.com/shienePark"
  danggn_kids: "https://www.daangn.com/kr/group/아이들-영어원서-읽어주기-wto6ua7xpeez/"
  danggn_freding: "https://blog.naver.com/whatiwillbeaverse"

# 히어로 하단 리스트용
current_roles:
  - role: "Service Dev"
    org: "OpenCode · Muse Spark 1.3"
    org_url: "https://github.com/Shiene1010/md-bento"
  - role: "아이들 영어원서 읽어주기"
    org: "운영자 (당근모임)"
    org_url: "https://shiene1010.github.io/voyager/"
  - role: "프레딩 소몰톡"
    org: "참가자 (당근모임)"
    org_url: "https://shiene1010.github.io/voyager/"
  - role: "youngest.dev 리버스 엔지니어링"
    org: "md-bento에 이식"
    org_url: "https://shiene1010.github.io/md-bento/"

# 01 — Projects
work_on_build:
  - title: "chunk-soundpad-mvp"
    tags: ["WEB-AUDIO", "SPEECH", "VANILLA"]
    summary: "영어 청크 말하기 연습용 4탭 사운드패드 (듣기연습/형태/기록/내정보)"
    metrics_or_detail: "Web Audio + Web Speech, 무빌드 단일 app.js"
    link_text: "Repo ↗"
    link_url: "https://github.com/Shiene1010/chunk-soundpad-mvp"

  - title: "tense-edge-kids"
    tags: ["CANVAS", "GAME", "KIDS-ENGLISH"]
    summary: "5세 원어민 대상 영어 시제 Canvas 학습 게임 (기차·공장·로켓 어드벤처)"
    metrics_or_detail: "60fps procedural 렌더 + Web Audio 신스"
    link_text: "Repo ↗"
    link_url: "https://github.com/Shiene1010/tense-edge-kids"

  - title: "vector-shredder"
    tags: ["CANVAS", "VECTOR", "PLAYGROUND"]
    summary: "미니멀 벡터 그래픽 플레이그라운드 및 데모"
    link_text: "Live Demo ↗"
    link_url: "https://shiene1010.github.io/vector-shredder"

work_off_build:
  - title: "당근모임 운영자"
    tags: ["KIDS-ENGLISH", "ORGANIZER"]
    summary: "아이들영어원서 읽어주기"
    link_url: "https://shiene1010.github.io/voyager/"
  - title: "프레딩 소몰톡"
    tags: ["ENGLISH", "SMALLTALK"]
    summary: "당근모임 참가자로 스몰톡 영어 연습"
    link_url: "https://shiene1010.github.io/voyager/"
  - title: "Voyager 블로그"
    tags: ["BLOG", "WRITING"]
    summary: "개인 블로그 및 기록"
    link_url: "https://shiene1010.github.io/voyager/"

# 02 — About Me
origins:
  quote: "OpenCode로 서비스를 만들고, 아이들 영어원서로 읽어주는 Shiene1010입니다."
  paragraphs:
    - "**OpenCode Muse Spark 1.3**으로 서비스를 직접 만들고 배포합니다."
    - "**당근모임 운영자**: 아이들 영어원서로 읽어줍니다."
    - "**프레딩 소몰톡 참가자**: 당근모임에서 스몰톡으로 영어를 씁니다."
    - "**youngest.dev 리버스 엔지니어링** 결과를 md-bento 제로빌드 구조에 이식 (현재!)"

# 03 — 링크 그래프 (그룹별 허브 + 노드, 좌표 포함)
link_groups:
  - name: "코드"
    hx: 200
    hy: 75
    left: true
    links:
      - target: "GitHub"
        target_url: "https://github.com/Shiene1010"
        role_desc: "@Shiene1010"
        nature: "Repos"
        x: 115
        y: 50
  - name: "모임들"
    hx: 200
    hy: 215
    left: true
    links:
      - target: "아이읽영"
        target_url: "https://www.daangn.com/kr/group/아이들-영어원서-읽어주기-wto6ua7xpeez/"
        role_desc: "운영자"
        nature: "당근모임"
        x: 115
        y: 180
      - target: "프레딩 소몰톡"
        target_url: "https://blog.naver.com/whatiwillbeaverse"
        role_desc: "참가자"
        nature: "당근모임"
        x: 115
        y: 250
  - name: "블로그들"
    hx: 200
    hy: 360
    left: true
    links:
      - target: "Voyager"
        target_url: "https://shiene1010.github.io/voyager/"
        role_desc: "개인 블로그"
        nature: "Writing"
        x: 115
        y: 320
      - target: "Google Blogger"
        target_url: "https://shiene1010.blogspot.com/"
        role_desc: "개인 블로그"
        nature: "Blogspot"
        x: 115
        y: 365
      - target: "Naver Blog"
        target_url: "https://blog.naver.com/whatiwillbeaverse"
        role_desc: "개인 블로그"
        nature: "Naver"
        x: 115
        y: 410
  - name: "SNS들"
    hx: 480
    hy: 105
    right: true
    links:
      - target: "Facebook"
        target_url: "https://www.facebook.com/headtometa"
        role_desc: "@headtometa"
        nature: "SNS"
        x: 565
        y: 55
      - target: "Instagram"
        target_url: "https://www.instagram.com/headtometa/"
        role_desc: "@headtometa"
        nature: "SNS"
        x: 565
        y: 100
      - target: "Threads"
        target_url: "https://www.threads.com/@8knockdowns"
        role_desc: "@8knockdowns"
        nature: "SNS"
        x: 565
        y: 150
      - target: "X"
        target_url: "https://x.com/shienePark"
        role_desc: "@shienePark"
        nature: "SNS"
        x: 565
        y: 195
  - name: "영상·오디오"
    hx: 480
    hy: 260
    right: true
    links:
      - target: "YouTube"
        target_url: "https://www.youtube.com/@8Knockdowns"
        role_desc: "@8Knockdowns"
        nature: "Channel"
        x: 565
        y: 235
      - target: "SoundCloud"
        target_url: "https://soundcloud.com/whatwillmyversebe?ref=clipboard&p=i&c=1&si=F690524B20EF4A8EBC04F16BAAB5AFD9&utm_source=clipboard&utm_medium=text&utm_campaign=social_sharing"
        role_desc: "오디오"
        nature: "Audio"
        x: 565
        y: 285
  - name: "커뮤니티·플레이"
    hx: 480
    hy: 390
    right: true
    links:
      - target: "Discord"
        target_url: "https://discord.gg/ef6YzwNA"
        role_desc: "서버 초대"
        nature: "Chat"
        x: 565
        y: 365
      - target: "Steam"
        target_url: "https://steamcommunity.com/profiles/76561198355440490/"
        role_desc: "프로필"
        nature: "Gaming"
        x: 565
        y: 415
# News (GitHub 최근 활동 3건)
news:
  - date: "2026.10"
    text: "md-bento 포트폴리오 공개 (제로빌드 md-only, Pages 배포)"
  - date: "2026.10"
    text: "TRIP-HomeOS-MD 정리 (16개 문서 → 실행 엔진 분리)"
  - date: "2026.10"
    text: "global-grid-2062 배포 (Tweego SugarCube2 CYOA 데모)"

# Publications (최근 GitHub Pages 3건)
publications:
  - title: "md-bento"
    author: "Shiene1010"
    image: ""
    link_url: "https://github.com/Shiene1010/md-bento"
    demo_url: "https://shiene1010.github.io/md-bento/"
  - title: "TRIP-HomeOS-MD"
    author: "Shiene1010"
    image: ""
    link_url: "https://github.com/Shiene1010/TRIP-HomeOS-MD"
    demo_url: "https://shiene1010.github.io/TRIP-HomeOS-MD/"
  - title: "global-grid-2062"
    author: "Shiene1010"
    image: ""
    link_url: "https://github.com/Shiene1010/global-grid-2062"
    demo_url: "https://shiene1010.github.io/global-grid-2062/"


closing_quote:
  quote: "I talk, Agents token — in Markdown."
  source: "md-bento · OpenCode Muse Spark 1.3"
---
