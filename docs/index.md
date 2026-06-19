---
layout: default
title: "Superpowers"
subTitle: "ANS Claude Marketplace"
---

<section class="hero mb-5">
  <p class="lead">
    Amplifiez Claude Code avec des <strong>super-pouvoirs</strong> conçus par l'ANS.<br>
    Installez des plugins pour automatiser vos workflows, analyser votre code et collaborer plus vite.
  </p>
  <a href="https://github.com/ansforge/ia-claude-marketplace" class="btn btn-primary mt-3">
    Voir sur GitHub
  </a>
</section>

<hr class="mb-5">

<section>
  <h2 class="mb-4">Catalogue des super-pouvoirs</h2>

  <div class="row row-cols-1 row-cols-md-2 row-cols-lg-3 g-4">
    {% for superpower in site.superpowers %}
    <div class="col">
      <div class="card h-100 superpower-card">
        <div class="card-body">
          <div class="superpower-icon mb-3">{{ superpower.icon | default: "⚡" }}</div>
          <h3 class="card-title h5">
            <a href="{{ superpower.url | relative_url }}" class="stretched-link text-decoration-none">
              {{ superpower.title }}
            </a>
          </h3>
          <p class="card-text text-muted">{{ superpower.description }}</p>
        </div>
        <div class="card-footer bg-transparent border-0">
          <span class="badge rounded-pill bg-primary">{{ superpower.category }}</span>
          {% if superpower.version %}
          <span class="badge rounded-pill bg-light text-dark">v{{ superpower.version }}</span>
          {% endif %}
        </div>
      </div>
    </div>
    {% endfor %}
  </div>
</section>

<hr class="my-5">

<section class="install-section mb-5">
  <h2 class="mb-3">Installation</h2>
  <p>Installez n'importe quel super-pouvoir directement depuis Claude Code :</p>

  <div class="install-steps">
    <div class="install-step">
      <span class="step-num">1</span>
      <div>
        <strong>Via la commande</strong>
        <pre class="install-code">/plugin install &lt;nom&gt;@claude-plugins-ans-official</pre>
      </div>
    </div>
    <div class="install-step">
      <span class="step-num">2</span>
      <div>
        <strong>Via la découverte</strong>
        <pre class="install-code">/plugin &gt; Discover</pre>
      </div>
    </div>
  </div>
</section>

<style>
.hero { padding: 2rem 0; }

.superpower-card {
  transition: box-shadow 0.2s ease, transform 0.2s ease;
  border: 1px solid #dee2e6;
}
.superpower-card:hover {
  box-shadow: 0 4px 20px rgba(0,0,0,0.12);
  transform: translateY(-2px);
}

.superpower-icon {
  font-size: 2rem;
  line-height: 1;
}

.install-steps { display: flex; flex-direction: column; gap: 1rem; margin-top: 1rem; }
.install-step {
  display: flex;
  align-items: flex-start;
  gap: 1rem;
  padding: 1rem 1.25rem;
  background: #f8f9fa;
  border-radius: 0.5rem;
  border-left: 4px solid #0053b3;
}
.step-num {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 2rem;
  height: 2rem;
  min-width: 2rem;
  border-radius: 50%;
  background: #0053b3;
  color: #fff;
  font-weight: 700;
  font-size: 0.9rem;
}
.install-code {
  margin: 0.25rem 0 0;
  padding: 0.4rem 0.75rem;
  background: #e9ecef;
  border-radius: 0.25rem;
  font-size: 0.9rem;
  display: inline-block;
}
</style>
