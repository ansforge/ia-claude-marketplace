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

<style>
.wrapper { font-size: 1.05rem; }
.page-intro { font-size: 1.15rem; line-height: 1.75; max-width: 720px; margin-bottom: 2rem; }

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(340px, 1fr));
  gap: 1.5rem;
  margin: 1.5rem 0 2rem;
}
.skill-card {
  border-radius: 0.6rem;
  padding: 1.75rem;
  border: 1px solid #dee2e6;
  display: flex;
  flex-direction: column;
  gap: 1rem;
  transition: box-shadow 0.15s ease, transform 0.15s ease;
  min-height: 200px;
}
.skill-card:hover { box-shadow: 0 6px 20px rgba(0,0,0,0.11); transform: translateY(-3px); }
.skill-card--curated { border-top: 4px solid #005e46; }

.skill-header { display: flex; align-items: flex-start; gap: 1.1rem; }
.skill-icon { font-size: 2.5rem; line-height: 1; flex-shrink: 0; margin-top: 2px; }
.skill-title { font-size: 1.15rem; font-weight: 700; margin: 0 0 0.3rem; }
.skill-title--plain { color: #212529; }
.skill-command { font-size: 0.9rem; color: #6c757d; background: #f1f3f5; padding: 0.15rem 0.45rem; border-radius: 4px; }

.skill-desc { font-size: 1rem; color: #495057; margin: 0; line-height: 1.65; flex: 1; }
.skill-footer { display: flex; gap: 0.4rem; flex-wrap: wrap; margin-top: auto; }

.badge { font-size: 0.8rem; padding: 0.25rem 0.65rem; border-radius: 999px; font-weight: 600; }
.badge-category { background: #e7effe; color: #0053b3; }
.badge-source   { background: #d4edda; color: #155724; }
</style>
