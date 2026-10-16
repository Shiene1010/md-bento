<!-- layout: youngest.dev sections | data: data.md | style: style.md -->
<!-- 이 파일은 레이아웃 전용. 평소에는 손댈 필요 없음. -->

<nav class="nav">
<div class="wrap nav-inner">
<a class="brand" href="#top">{{ profile.name }}</a>
<div class="nav-links">{% for item in nav %}<a href="{{ item.href }}">{{ item.label }}</a>{% endfor %}
</div>
</div>
</nav>

<div id="top" class="wrap hero reveal">
<div class="hero-bg" aria-hidden="true">
<svg viewBox="0 0 1200 600" preserveAspectRatio="xMidYMid slice">
<g stroke="var(--rule)" stroke-width="1">
<line x1="0" y1="120" x2="1200" y2="120"/>
<line x1="0" y1="240" x2="1200" y2="240"/>
<line x1="0" y1="360" x2="1200" y2="360"/>
<line x1="0" y1="480" x2="1200" y2="480"/>
</g>
<polyline points="0,480 150,440 250,460 350,380 450,300 550,340 650,260 750,180 900,220 1050,120 1200,100" fill="none" stroke="var(--gold)" stroke-width="1.5" opacity="0.45"/>
<polyline points="0,520 180,500 320,505 470,440 620,450 770,380 920,390 1080,300 1200,290" fill="none" stroke="var(--moss-light)" stroke-width="1.5" opacity="0.5"/>
</svg>
</div>

{% if profile.avatar %}![avatar]({{ profile.avatar }}){% endif %}
<p class="eyebrow">{{ hero.eyebrow }}</p>

# {{ hero.title }}

<p class="tagline">{{ hero.tagline }}</p>
<p class="badge-bar"><small><code>{{ profile.role_title }}</code> · {{ profile.status_badge }}</small></p>

{% for item in current_roles %}
* **{{ item.role }}** · [{{ item.org }}]({{ item.org_url }})
{% endfor %}
</div>

<div class="ticker" aria-hidden="true">
<div class="ticker-track">{% for t in ticker %}<span>{{ t }}</span><span class="dot">·</span>{% endfor %}{% for t in ticker %}<span>{{ t }}</span><span class="dot">·</span>{% endfor %}
</div>
</div>

<div class="wrap">

## 01 — The Work
> On the build, and off it.

### On the Build
<div class="bento-grid work-scroll">
<div class="bento-card window-card" aria-hidden="true">
<div class="window-bar"><span class="dot gold"></span><span class="dot moss"></span><span class="dot muted"></span><span class="window-title">On the Build</span></div>
<hr class="window-rule">
<div class="window-body">
<svg viewBox="0 0 280 110">
<g stroke="var(--parchment-dim)" stroke-width="7" stroke-linecap="round" opacity="0.55">
<line x1="8" y1="16" x2="180" y2="16"/>
<line x1="8" y1="44" x2="250" y2="44"/>
<line x1="8" y1="72" x2="150" y2="72"/>
<line x1="8" y1="100" x2="210" y2="100"/>
</g>
</svg>
</div>
<a class="work-link" href="https://github.com/Shiene1010">All Repos ↗</a>
</div>
{% for item in work_on_build %}
<div class="bento-card work-card">
<span class="bento-title">{{ item.title }}</span>
<span class="work-tags">{% for tag in item.tags %}<code>{{ tag }}</code> {% endfor %}</span>
<span class="bento-role">{{ item.summary }}</span>
{% if item.metrics_or_detail %}<span class="work-detail">{{ item.metrics_or_detail }}</span>{% endif %}
<a class="work-link" href="{{ item.link_url }}">{{ item.link_text | default('Link ↗') }}</a>
</div>{% endfor %}
</div>

### Off the Meet
<div class="bento-grid work-scroll">
<div class="bento-card meet-art" aria-hidden="true">
<svg class="meet-bg" viewBox="0 0 240 220">
<path d="M40,200 L40,100 A80,80 0 0 1 200,100 L200,200 Z" fill="none" stroke="var(--gold)" stroke-width="1.5" opacity="0.8"/>
<path d="M70,200 L70,115 A50,50 0 0 1 170,115 L170,200" fill="none" stroke="var(--moss-light)" stroke-width="1.5" opacity="0.7"/>
<line x1="24" y1="200" x2="216" y2="200" stroke="var(--rule)" stroke-width="1.5"/>
<circle cx="120" cy="60" r="4" fill="var(--gold)"/>
</svg>
<a class="work-link" href="https://www.daangn.com/kr/group/아이들-영어원서-읽어주기-wto6ua7xpeez/">아영읽 ↗</a>
</div>
{% for item in work_off_build %}
<div class="bento-card work-card">
<span class="bento-title">{{ item.title }}</span>
<span class="work-tags">{% for tag in item.tags %}<code>{{ tag }}</code> {% endfor %}</span>
<span class="bento-role">{{ item.summary }}</span>
{% if item.metrics_or_detail %}<span class="work-detail">{{ item.metrics_or_detail }}</span>{% endif %}
<a class="work-link" href="{{ item.link_url }}">{{ item.link_text | default('Link ↗') }}</a>
</div>{% endfor %}
</div>

</div>

<div id="origins" class="band">
<div class="wrap">

## 02 — Origins
> How a writer ended up shipping systems.

> *"{{ origins.quote }}"*

{% for p in origins.paragraphs %}
* {{ p }}
{% endfor %}

<details>
<summary><b>더 보기: 새벽 1시 인프라와 로그 기록 원문</b></summary>

클라우드 비용 절감과 자체 호스팅(Traefik + Docker) 전환 과정에서 마주친 엣지 케이스 아카이브. `data.md`의 `origins.paragraphs`에 추가하면 여기 리스트에 그대로 반영된다.
</details>

</div>
</div>

<div id="partners" class="wrap">

## 03 — Where the Work Lives

<svg class="graph" viewBox="0 0 680 450" role="img" aria-label="link graph">
{% for g in link_groups %}<line x1="340" y1="228" x2="{{ g.hx }}" y2="{{ g.hy }}" class="e-hub"/>{% for row in g.links %}<line x1="{{ g.hx }}" y1="{{ g.hy }}" x2="{{ row.x }}" y2="{{ row.y }}" class="e-leaf"/>{% endfor %}{% endfor %}
{% for g in link_groups %}<circle cx="{{ g.hx }}" cy="{{ g.hy }}" r="5" class="n-hub"/><text x="{{ g.hx }}" y="{{ g.hy }}" dy="-14" class="n-hub-label">{{ g.name }}</text>{% endfor %}
<a href="#top"><circle cx="340" cy="228" r="8" class="n-center"/><text x="340" y="228" dy="26" class="n-center-label">Shiene1010</text></a>
{% for g in link_groups %}{% if g.left %}{% for row in g.links %}<a href="{{ row.target_url }}"><title>{{ row.target }} — {{ row.role_desc }} · {{ row.nature }}</title><circle cx="{{ row.x }}" cy="{{ row.y }}" r="4" class="n-leaf"/><text x="{{ row.x }}" y="{{ row.y }}" dx="-10" dy="4" text-anchor="end" class="n-label">{{ row.target }}</text></a>{% endfor %}{% endif %}{% if g.right %}{% for row in g.links %}<a href="{{ row.target_url }}"><title>{{ row.target }} — {{ row.role_desc }} · {{ row.nature }}</title><circle cx="{{ row.x }}" cy="{{ row.y }}" r="4" class="n-leaf"/><text x="{{ row.x }}" y="{{ row.y }}" dx="10" dy="4" text-anchor="start" class="n-label">{{ row.target }}</text></a>{% endfor %}{% endif %}{% endfor %}
</svg>

</div>

<div id="news" class="wrap">

## News

{% for n in news %}
* **{{ n.date }}** — {{ n.text }}
{% endfor %}

</div>

<div id="publications" class="wrap">

## Publications

{% for pub in publications %}
* **{{ pub.title }}** — {{ pub.author }}
  {% if pub.image %}* ![{{ pub.title }}]({{ pub.image }}){% endif %}
  {% if pub.link_url %}* [Link]({{ pub.link_url }}){% endif %}
  {% if pub.demo_url %}* [Live Demo]({{ pub.demo_url }}){% endif %}
{% endfor %}

</div>

<div class="wrap quote">

> *"{{ closing_quote.quote }}"*
> — *{{ closing_quote.source }}*

</div>

<div id="contact" class="wrap footer">
<div class="foot-grid">
<div>
<p class="eyebrow">Contact</p>
<p><a href="mailto:{{ contacts.email }}">{{ contacts.email }}</a><br><a href="mailto:{{ contacts.email_apple1 }}">{{ contacts.email_apple1 }}</a></p>
</div>
<div>
<p class="eyebrow">Elsewhere</p>
<p><a href="{{ contacts.github }}">GitHub ↗</a> · <a href="{{ contacts.blogger }}">Blogger ↗</a> · <a href="{{ contacts.naver_blog }}">Naver ↗</a><br><a href="{{ contacts.voyager }}">Voyager ↗</a> · <a href="{{ contacts.youtube }}">YouTube ↗</a> · <a href="{{ contacts.discord }}">Discord ↗</a> · <a href="{{ contacts.steam }}">Steam ↗</a></p>
</div>
<div>
<p class="eyebrow">Colophon</p>
<p><small>© {{ profile.copyright_year }} {{ profile.name }} · data.md + style.md → zero-build</small></p>
</div>
</div>
</div>
