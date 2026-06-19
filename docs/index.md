---
layout: default
title: "Marketplace ANS — Claude Code"
subTitle: "Amplifiez votre développement avec l'IA"
---

<section class="hero-section">
  <p class="hero-lead">
    L'ANS met à disposition un <strong>catalogue de super-pouvoirs</strong> pour Claude Code :
    des plugins et compétences prêts à l'emploi, conçus pour les équipes qui développent
    des services numériques en santé.
  </p>
</section>

---

## Pourquoi un marketplace ANS ?

Claude Code est un assistant IA puissant, mais c'est sa capacité à être <strong>étendu par des plugins</strong> qui le rend vraiment transformateur pour nos équipes.

<div class="why-grid">
  <div class="why-card">
    <div class="why-icon">🏗️</div>
    <h3>Capitaliser les pratiques ANS</h3>
    <p>Nos standards qualité, nos règles de revue, nos conventions de code — tout ça peut être encodé dans un plugin et partagé à toutes les équipes d'un coup.</p>
  </div>
  <div class="why-card">
    <div class="why-icon">⚡</div>
    <h3>Automatiser les tâches répétitives</h3>
    <p>Revues de PR, audits de sécurité, génération de documentation, conformité réglementaire — les super-pouvoirs font tourner ces workflows sans intervention manuelle.</p>
  </div>
  <div class="why-card">
    <div class="why-icon">🔒</div>
    <h3>Maîtriser la chaîne de confiance</h3>
    <p>Installer un plugin depuis ce marketplace, c'est installer du code relu et maintenu par l'ANS. Pas de plugin tiers non vérifié, pas de surprise.</p>
  </div>
  <div class="why-card">
    <div class="why-icon">🤝</div>
    <h3>Partager l'intelligence entre équipes</h3>
    <p>Un outil utile dans une équipe devient immédiatement disponible partout. Le marketplace est le point de convergence de l'intelligence collective ANS.</p>
  </div>
</div>

---

<section id="skills-internes">
<h2>Skills internes</h2>
<p>Développés et maintenus par l'ANS. <a href="{{ '/skills-internes/' | relative_url }}">Voir tous les skills internes →</a></p>

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

</section>

---

<section id="skills-externes">
<h2>Skills externes</h2>
<p>Une sélection de compétences IA de confiance, issues de Claude Code ou de la communauté. <a href="{{ '/skills-externes/' | relative_url }}">Voir tous les skills externes →</a></p>

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

</section>

---

## Comment installer un super-pouvoir

<div class="install-steps">
  <div class="install-step">
    <span class="step-num">1</span>
    <div>
      <strong>Ouvrez Claude Code</strong> dans votre terminal ou IDE
    </div>
  </div>
  <div class="install-step">
    <span class="step-num">2</span>
    <div>
      <strong>Installez via la commande</strong>
      <pre class="install-code">/plugin install ans-review@claude-plugins-ans-official</pre>
    </div>
  </div>
  <div class="install-step">
    <span class="step-num">3</span>
    <div>
      <strong>Ou découvrez les plugins disponibles</strong>
      <pre class="install-code">/plugin &gt; Discover</pre>
    </div>
  </div>
</div>

