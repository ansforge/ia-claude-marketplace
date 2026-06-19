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

## Skills internes

Développés et maintenus par l'ANS. <a href="{{ '/skills-internes/' | relative_url }}">Voir tous les skills internes →</a>

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

## Skills externes

Une sélection de compétences IA de confiance, issues de Claude Code ou de la communauté. <a href="{{ '/skills-externes/' | relative_url }}">Voir tous les skills externes →</a>

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

<style>
/* ── Base ── */
.wrapper, .wrapper p, .wrapper li { font-size: 1.2rem; }

/* ── Hero ── */
.hero-section { padding: 1.5rem 0 2rem; }
.hero-lead { font-size: 1.45rem; line-height: 1.75; max-width: 820px; }

/* ── Why grid ── */
.why-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: 1.25rem;
  margin: 1.5rem 0 2rem;
}
.why-card {
  padding: 1.5rem;
  background: #f8f9fa;
  border-radius: 0.5rem;
  border-left: 4px solid #0053b3;
}
.why-icon { font-size: 2.5rem; margin-bottom: 0.6rem; }
.why-card h3 { font-size: 1.35rem; font-weight: 700; margin: 0 0 0.5rem; }
.why-card p { font-size: 1.2rem; color: #495057; margin: 0; line-height: 1.75; }

/* ── Skills grid ── */
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
.skill-card--internal { border-top: 4px solid #0053b3; }
.skill-card--curated  { border-top: 4px solid #005e46; }

.skill-header { display: flex; align-items: flex-start; gap: 1.1rem; }
.skill-icon { font-size: 2.75rem; line-height: 1; flex-shrink: 0; margin-top: 2px; }
.skill-title { font-size: 1.3rem; font-weight: 700; margin: 0 0 0.3rem; }
.skill-title a { color: #0053b3; text-decoration: none; }
.skill-title a:hover { text-decoration: underline; }
.skill-title--plain { color: #212529; }
.skill-command {
  font-size: 1rem;
  color: #6c757d;
  background: #f1f3f5;
  padding: 0.15rem 0.45rem;
  border-radius: 4px;
}

.skill-desc { font-size: 1.15rem; color: #495057; margin: 0; line-height: 1.7; flex: 1; }
.skill-footer { display: flex; gap: 0.4rem; flex-wrap: wrap; margin-top: auto; }

/* ── Badges ── */
.badge {
  font-size: 0.9rem;
  padding: 0.3rem 0.75rem;
  border-radius: 999px;
  font-weight: 600;
  letter-spacing: 0.02em;
}
.badge-category { background: #e7effe; color: #0053b3; }
.badge-version  { background: #f1f3f5; color: #495057; }
.badge-ans      { background: #0053b3; color: #fff; }
.badge-source   { background: #d4edda; color: #155724; }

/* ── Install steps ── */
.install-steps { display: flex; flex-direction: column; gap: 0.75rem; margin: 1rem 0 2rem; }
.install-step {
  display: flex;
  align-items: flex-start;
  gap: 1rem;
  padding: 1.1rem 1.4rem;
  background: #f8f9fa;
  border-radius: 0.5rem;
  font-size: 1.2rem;
}
.step-num {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 2.3rem;
  height: 2.3rem;
  min-width: 2.3rem;
  border-radius: 50%;
  background: #0053b3;
  color: #fff;
  font-weight: 700;
  font-size: 1.1rem;
  flex-shrink: 0;
}
.install-code {
  margin: 0.35rem 0 0;
  padding: 0.45rem 0.85rem;
  background: #e9ecef;
  border-radius: 0.3rem;
  font-size: 1.05rem;
  display: inline-block;
}
</style>
