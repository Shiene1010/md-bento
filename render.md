<!-- layout: youngest.dev sections | data: data.md | style: style.md -->
<!-- 이 파일은 레이아웃 전용. 평소에는 손댈 필요 없음. -->

<nav class="nav">
<div class="wrap nav-inner">
<a class="brand" href="#top">{{ profile.name }}</a>
<div class="nav-links">
{% for item in nav %}
<a href="{{ item.href }}">{{ item.label }}</a>
{% endfor %}
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
<p class="badge-bar"><small>`{{ profile.role_title }}` · {{ profile.status_badge }}</small></p>

{% for item in current_roles %}
* **{{ item.role }}** · [{{ item.org }}]({{ item.org_url }})
{% endfor %}
</div>

<div class="ticker" aria-hidden="true">
<div class="ticker-track">
{% for t in ticker %}
<span>{{ t }}</span><span class="dot">·</span>
{% endfor %}
{% for t in ticker %}
<span>{{ t }}</span><span class="dot">·</span>
{% endfor %}
</div>
</div>

<div class="wrap">

## 01 — The Work
> On the build, and off it.

### On the Build
<div class="split-row">
<div class="split-text">

{% for item in work_on_build %}
* **{{ item.title }}** — {% for tag in item.tags %}`{{ tag }}` {% endfor %}
  * {{ item.summary }}
  {% if item.metrics_or_detail %}* *Detail:* {{ item.metrics_or_detail }}{% endif %}
  * [{{ item.link_text | default('View Project ↗') }}]({{ item.link_url }})
{% endfor %}

</div>
<div class="split-art" aria-hidden="true">
<svg viewBox="0 0 320 220">
<rect x="8" y="8" width="304" height="204" rx="12" fill="none" stroke="var(--rule)" stroke-width="1.5"/>
<circle cx="32" cy="34" r="5" fill="var(--gold)"/>
<circle cx="52" cy="34" r="5" fill="var(--moss-light)"/>
<circle cx="72" cy="34" r="5" fill="var(--muted)"/>
<line x1="24" y1="56" x2="296" y2="56" stroke="var(--rule)" stroke-width="1"/>
<g stroke="var(--parchment-dim)" stroke-width="6" stroke-linecap="round" opacity="0.55">
<line x1="32" y1="84" x2="180" y2="84"/>
<line x1="32" y1="108" x2="240" y2="108"/>
<line x1="32" y1="132" x2="150" y2="132"/>
<line x1="32" y1="156" x2="210" y2="156"/>
</g>
<rect x="32" y="172" width="70" height="20" rx="10" fill="none" stroke="var(--gold)" stroke-width="1.5" opacity="0.7"/>
</svg>
</div>
</div>

### Off the Build
<div class="split-row">
<div class="split-text">

{% for item in work_off_build %}
* **{{ item.title }}** — {% for tag in item.tags %}`{{ tag }}` {% endfor %}
  * {{ item.summary }}
  * [Link ↗]({{ item.link_url }})
{% endfor %}

</div>
<div class="split-art" aria-hidden="true">
<svg viewBox="0 0 240 220">
<path d="M40,200 L40,100 A80,80 0 0 1 200,100 L200,200 Z" fill="none" stroke="var(--gold)" stroke-width="1.5" opacity="0.8"/>
<path d="M70,200 L70,115 A50,50 0 0 1 170,115 L170,200" fill="none" stroke="var(--moss-light)" stroke-width="1.5" opacity="0.7"/>
<line x1="24" y1="200" x2="216" y2="200" stroke="var(--rule)" stroke-width="1.5"/>
<circle cx="120" cy="60" r="4" fill="var(--gold)"/>
</svg>
</div>
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

| 분류 | 대상 / 플랫폼 | 역할 및 성격 | 링크 |
| :--- | :--- | :--- | :--- |{% for row in work_matrix %}
| **{{ row.category }}** | [{{ row.target }}]({{ row.target_url }}) | {{ row.role_desc }} (`{{ row.nature }}`) | [↗]({{ row.target_url }}) |{% endfor %}

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
<p><a href="mailto:{{ contacts.email }}">{{ contacts.email }}</a></p>
</div>
<div>
<p class="eyebrow">Elsewhere</p>
<p><a href="{{ contacts.voyager }}">Voyager ↗</a> · <a href="{{ contacts.youtube }}">YouTube ↗</a> · <a href="{{ contacts.discord }}">Discord ↗</a> · <a href="{{ contacts.steam }}">Steam ↗</a></p>
</div>
<div>
<p class="eyebrow">Colophon</p>
<p><small>© {{ profile.copyright_year }} {{ profile.name }} · data.md + style.md → zero-build</small></p>
</div>
</div>
</div>
