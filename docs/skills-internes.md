---
layout: default
title: "Skills internes"
subTitle: "Développés et maintenus par l'ANS"
permalink: /skills-internes/
---

<p class="page-intro">
  Ces skills sont développés, relus et maintenus par les équipes de l'ANS.
  Ils encodent nos standards qualité, nos conventions et nos workflows — installables en une commande.
</p>

<div class="install-banner">
  <strong>Installation :</strong>
  <code>/plugin install &lt;nom&gt;@claude-plugins-ans-official</code>
</div>

<div class="skills-grid">
  {% for superpower in site.superpowers %}
  <div class="skill-card skill-card--internal">
    <div class="skill-header">
      <span class="skill-icon">{{ superpower.icon | default: "⚡" }}</span>
      <div>
        <h3 class="skill-title">
          <a href="{{ superpower.url | relative_url }}">{{ superpower.title }}</a>
        </h3>
        <code class="skill-command">/{{ superpower.install_name | default: superpower.slug }}</code>
      </div>
    </div>
    <p class="skill-desc">{{ superpower.description }}</p>
    <div class="skill-footer">
      <span class="badge badge-category">{{ superpower.category }}</span>
      {% if superpower.version %}<span class="badge badge-version">v{{ superpower.version }}</span>{% endif %}
      <span class="badge badge-ans">ANS</span>
    </div>
  </div>
  {% endfor %}
</div>

<style>
.wrapper { font-size: 1.05rem; }
.page-intro { font-size: 1.15rem; line-height: 1.75; max-width: 720px; margin-bottom: 1.5rem; }
.install-banner {
  display: inline-flex;
  align-items: center;
  gap: 0.75rem;
  padding: 0.8rem 1.25rem;
  background: #e7effe;
  border-radius: 0.4rem;
  font-size: 1rem;
  margin-bottom: 2rem;
}
.install-banner code { background: #fff; padding: 0.2rem 0.5rem; border-radius: 3px; font-size: 0.95rem; }

.skills-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
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
.skill-card--internal { border-top: 4px solid #0053b3; }

.skill-header { display: flex; align-items: flex-start; gap: 1.1rem; }
.skill-icon { font-size: 2.5rem; line-height: 1; flex-shrink: 0; margin-top: 2px; }
.skill-title { font-size: 1.15rem; font-weight: 700; margin: 0 0 0.3rem; }
.skill-title a { color: #0053b3; text-decoration: none; }
.skill-title a:hover { text-decoration: underline; }
.skill-command { font-size: 0.9rem; color: #6c757d; background: #f1f3f5; padding: 0.15rem 0.45rem; border-radius: 4px; }

.skill-desc { font-size: 1rem; color: #495057; margin: 0; line-height: 1.65; flex: 1; }
.skill-footer { display: flex; gap: 0.4rem; flex-wrap: wrap; margin-top: auto; }

.badge { font-size: 0.8rem; padding: 0.25rem 0.65rem; border-radius: 999px; font-weight: 600; }
.badge-category { background: #e7effe; color: #0053b3; }
.badge-version  { background: #f1f3f5; color: #495057; }
.badge-ans      { background: #0053b3; color: #fff; }
</style>
