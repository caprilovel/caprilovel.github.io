---
title: Projects
icon: fas fa-diagram-project
order: 3
---

{% assign projects = site.data.projects %}
{% if projects.size > 0 %}
<div class="project-grid">
{% for p in projects %}
<div class="project-card">
<div class="project-card__header">
<span class="project-card__title">{{ p.title }}</span>
{% if p.period %}<span class="project-card__period">{{ p.period }}</span>{% endif %}
</div>
{% if p.description %}<p class="project-card__desc">{{ p.description }}</p>{% endif %}
{% if p.tags.size > 0 %}
<div class="project-card__tags">
{% for tag in p.tags %}<span class="tag">{{ tag }}</span>{% endfor %}
</div>
{% endif %}
{% if p.links.size > 0 %}
<div class="project-card__links">
{% for link in p.links %}<a href="{{ link.url }}" target="_blank" rel="noopener noreferrer">{{ link.label }}</a>{% endfor %}
</div>
{% endif %}
</div>
{% endfor %}
</div>
{% endif %}
