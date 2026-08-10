---
title: CV
icon: fas fa-file-alt
order: 2
---

[TODO: put a PDF resume in `assets/` and link it here, e.g. `[Download PDF](/assets/cv.pdf)`]

## Education

{% assign edu = site.data.profile.education %}
{% if edu.size > 0 %}
<ul class="cv-list">
{% for e in edu %}
<li>
<div class="cv-list__header">
<span class="cv-list__title">{{ e.degree }}</span>
<span class="cv-list__period">{{ e.period }}</span>
</div>
<div class="cv-list__subtitle">{{ e.school }}</div>
{% if e.details %}<div class="cv-list__details">{{ e.details }}</div>{% endif %}
</li>
{% endfor %}
</ul>
{% endif %}

## Experience

[TODO: research/work experience — role, lab/company, dates, one line on what you did.]

## Awards & Honors

[TODO: fellowships, scholarships, competition placements, etc.]

## Skills

[TODO: e.g. Python, PyTorch, Machine Learning, Signal Processing.]

## Publications

See the full list on the [Publications]({{ '/publications/' | relative_url }}) page.
