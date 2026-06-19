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

