---
layout: default
title: "Skills externes"
subTitle: "Sélection curée par l'ANS"
permalink: /skills-externes/
---

<p class="page-intro">
  Une sélection de compétences IA issues de Claude Code ou de la communauté,
  choisies pour leur fiabilité et leur pertinence dans nos contextes de développement.
</p>

<div class="skills-grid">
  {% for skill in site.data.curated_skills %}
  {% unless skill.internal %}
  <div class="skill-card skill-card--curated">
    <div class="skill-header">
      <span class="skill-icon">{{ skill.icon }}</span>
      <div>
        <h3 class="skill-title skill-title--plain">{{ skill.name }}</h3>
        {% if skill.command %}<code class="skill-command">{{ skill.command }}</code>{% endif %}
      </div>
    </div>
    <p class="skill-desc">{{ skill.description }}</p>
    <div class="skill-footer">
      <span class="badge badge-category">{{ skill.category }}</span>
      <span class="badge badge-source">{{ skill.source }}</span>
    </div>
  </div>
  {% endunless %}
  {% endfor %}
</div>

