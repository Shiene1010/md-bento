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
{% for item in work_on_build %}
* **{{ item.title }}** — {% for tag in item.tags %}`{{ tag }}` {% endfor %}
  * {{ item.summary }}
  {% if item.metrics_or_detail %}* *Detail:* {{ item.metrics_or_detail }}{% endif %}
  * [{{ item.link_text | default('View Project ↗') }}]({{ item.link_url }})
{% endfor %}

### Off the Build
{% for item in work_off_build %}
* **{{ item.title }}** — {% for tag in item.tags %}`{{ tag }}` {% endfor %}
  * {{ item.summary }}
  * [Link ↗]({{ item.link_url }})
{% endfor %}

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
| :--- | :--- | :--- | :--- |
{% for row in work_matrix %}
| **{{ row.category }}** | [{{ row.target }}]({{ row.target_url }}) | {{ row.role_desc }} (`{{ row.nature }}`) | [↗]({{ row.target_url }}) |
{% endfor %}

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
