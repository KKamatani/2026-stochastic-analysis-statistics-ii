---
layout: default
title: Stochastic Analysis and Statistics 2026-II
permalink: /
image: /assets/img/hero.jpg
---
{% assign event = site.data.event %}
<section id="home" class="hero parallax text-light" style="--hero-img: url('{{ '/assets/img/hero.jpg' | relative_url }}'); --speed: .15;" aria-labelledby="event-title">
  <div class="container py-5">
    <div class="row gx-4 gy-5 align-items-center">
      <div class="col-lg-7">
        <span class="badge bg-glass mb-3">{{ event.date_short }} | Tokyo, Japan</span>
        <h1 id="event-title" class="display-4 fw-bold">Stochastic Analysis<br>and Statistics <span class="hero-edition">2026-II</span></h1>
        <p class="lead mt-3">A one-day workshop on stochastic analysis and statistical inference for stochastic processes.</p>
        <div class="d-flex gap-2 mt-4 flex-wrap">
          <a href="#programme" class="btn btn-light btn-lg">View Programme</a>
          <a href="#venue" class="btn btn-outline-light btn-lg">Venue &amp; Access</a>
        </div>
      </div>
      <div class="col-lg-5">
        <div class="hero-card shadow-lg p-4 rounded-4 bg-glass">
          <h2 class="h5 mb-3"><i class="bi bi-calendar-week me-2" aria-hidden="true"></i>Quick Facts</h2>
          <dl class="event-details mb-0">
            <dt>Date</dt><dd><time datetime="{{ event.date }}">{{ event.date_label }}</time></dd>
            <dt>Venue</dt><dd>{{ event.venue }}<br><span class="small">{{ event.campus }}</span></dd>
            <dt>Room</dt><dd>{{ event.room }}</dd>
          </dl>
        </div>
      </div>
    </div>
  </div>
</section>

<section id="about" class="section-pad" aria-labelledby="about-title">
  <div class="container">
    <div class="row g-4 align-items-center">
      <div class="col-lg-7">
        <h2 id="about-title" class="h3 mb-3">About</h2>
        <p>Stochastic Analysis and Statistics 2026-II brings together researchers working on stochastic analysis and statistical methodology for stochastic processes. The workshop will feature a special lecture by Arnaud Gloter and talks by early-career researchers.</p>
        <p>The workshop is scheduled for {{ event.date_label }} at the {{ event.venue }}, {{ event.campus }}, {{ event.room }}.</p>
        <a class="small" href="{{ event.previous_url }}">Previous meeting: Stochastic Analysis and Statistics 2026<i class="bi bi-arrow-up-right ms-1" aria-hidden="true"></i></a>
      </div>
      <div class="col-lg-5">
        <div class="card shadow-sm">
          <div class="card-body p-4">
            <h3 class="h6 mb-3">Latest Information</h3>
            <p class="small mb-0">A tentative afternoon programme is listed below, with a 40-minute special lecture by Arnaud Gloter and six 25-minute early-career talks. Talk titles and abstracts will be announced. Information on participation will follow.</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<section id="programme" class="section-pad bg-body-secondary" aria-labelledby="programme-title">
  <div class="container">
    <div class="d-flex flex-wrap gap-3 justify-content-between align-items-center mb-4">
      <h2 id="programme-title" class="h3 mb-0">Tentative Programme</h2>
      <a class="btn btn-outline-primary btn-sm" href="#abstracts">See Abstracts</a>
    </div>
    <div class="card shadow-sm">
      <div class="card-body p-4">
        <h3 class="h5 mb-1">{{ event.date_label }}</h3>
        <p class="small text-secondary mb-3">{{ event.room }} · {{ event.campus }}</p>
        <p class="small text-secondary mb-3">Provisional schedule; times and the number of early-career talks are subject to change. All talk slots include questions and discussion.</p>
        {% if site.data.programme.size > 0 %}
        <ol class="schedule mb-0">
          {% for slot in site.data.programme %}
          <li class="schedule-row">
            <span class="schedule-time">{{ slot.time | escape }}</span>
            <div>
              {% if slot.speaker %}
              {% assign speaker = site.data.speakers[slot.speaker] %}
              <a class="fw-semibold" href="#abs-{{ slot.speaker }}">{{ speaker.name | escape }}</a>
              <span class="d-block small text-secondary">{{ speaker.affiliation | escape }}</span>
              {% if speaker.role %}<span class="d-block small mt-1">{{ speaker.role | escape }}</span>{% endif %}
              {% if speaker.title and speaker.title != '' %}<span class="d-block small mt-1">{{ speaker.title | escape }}</span>{% endif %}
              {% else %}{{ slot.label | escape }}{% endif %}
            </div>
          </li>
          {% endfor %}
        </ol>
        {% else %}
        <p class="mb-0 text-secondary">The programme and session times will be announced.</p>
        {% endif %}
      </div>
    </div>
  </div>
</section>

<section id="abstracts" class="section-pad" aria-labelledby="abstracts-title">
  <div class="container">
    <div class="d-flex flex-wrap gap-3 justify-content-between align-items-center mb-3">
      <h2 id="abstracts-title" class="h3 mb-0">Abstracts</h2>
      <a class="btn btn-outline-primary btn-sm" href="#speakers">See Speakers</a>
    </div>
    {% if site.data.speakers.size > 0 %}
    <div class="abstracts">
      {% for entry in site.data.speakers %}
      {% assign speaker = entry[1] %}
      <article class="abstract-entry" id="abs-{{ entry[0] }}">
        <h3 class="h6 mb-1">{{ speaker.name | escape }}</h3>
        <p class="small text-secondary mb-2">{{ speaker.affiliation | escape }}</p>
        {% if speaker.title and speaker.title != '' %}<p class="fw-semibold mb-2">{{ speaker.title | escape }}</p>{% endif %}
        {% if speaker.abstract and speaker.abstract != '' %}
        <div class="abstract-body">{{ speaker.abstract | markdownify }}</div>
        {% else %}<p class="text-secondary mb-0">Abstract to be announced.</p>{% endif %}
      </article>
      {% endfor %}
    </div>
    {% else %}<p class="text-secondary mb-0">Talk titles and abstracts will be announced.</p>{% endif %}
  </div>
</section>

<section id="speakers" class="section-pad bg-body-secondary" aria-labelledby="speakers-title">
  <div class="container">
    <h2 id="speakers-title" class="h3 mb-3">Speakers</h2>
    <p class="text-secondary">Special lecture: Arnaud Gloter. The tentative list of speakers is shown below.</p>
    {% if site.data.speakers.size > 0 %}
    <ul class="row g-4 list-unstyled mb-0">
      {% for entry in site.data.speakers %}
      {% assign speaker = entry[1] %}
      <li class="col-md-6 col-lg-4">
        <a href="#abs-{{ entry[0] }}">{{ speaker.name | escape }}</a>
        <span class="d-block small text-secondary">{{ speaker.affiliation | escape }}</span>
        {% if speaker.url and speaker.url != '' %}
        <a class="d-inline-block small mt-1" href="{{ speaker.url | escape }}" target="_blank" rel="noopener noreferrer" aria-label="Website of {{ speaker.name | escape }} (opens in a new tab)">Website<i class="bi bi-box-arrow-up-right ms-1" aria-hidden="true"></i></a>
        {% endif %}
      </li>
      {% endfor %}
    </ul>
    {% else %}<p class="text-secondary mb-0">The list of speakers will be announced.</p>{% endif %}
  </div>
</section>

<section id="venue" class="section-pad" aria-labelledby="venue-title">
  <div class="container">
    <h2 id="venue-title" class="h3 mb-4">Venue</h2>
    <div class="row g-4 align-items-stretch">
      <div class="col-lg-6">
        <h3 class="h5 mb-3">{{ event.venue }}</h3>
        <p class="mb-3"><strong>{{ event.room }}</strong> · {{ event.campus }}</p>
        <p class="mb-2">{{ event.address }}</p>
        <p class="small text-secondary mb-4">Nearest station: Komaba-todaimae (Keio Inokashira Line).</p>
        <a class="btn btn-outline-primary" href="{{ event.access_url }}" target="_blank" rel="noopener noreferrer">Campus Access &amp; Map<i class="bi bi-box-arrow-up-right ms-2" aria-hidden="true"></i></a>
      </div>
      <div class="col-lg-6">
        <div class="ratio ratio-16x9 shadow-sm rounded-3 overflow-hidden">
          <iframe title="Map of the Graduate School of Mathematical Sciences, The University of Tokyo" src="https://www.google.com/maps?q=Graduate+School+of+Mathematical+Sciences+University+of+Tokyo&amp;output=embed&amp;hl=en" loading="lazy" referrerpolicy="no-referrer-when-downgrade" style="border:0" allowfullscreen></iframe>
        </div>
      </div>
    </div>
  </div>
</section>

<section id="organisers" class="section-pad bg-body-secondary" aria-labelledby="organisers-title">
  <div class="container">
    <h2 id="organisers-title" class="h3 mb-4">Organisers</h2>
    <ul class="row g-4 list-unstyled mb-0">
      {% for organiser in site.data.organisers %}
      <li class="col-md-6 col-lg-4">
        {% if organiser.url and organiser.url != '' %}
        <a href="{{ organiser.url | escape }}" target="_blank" rel="noopener noreferrer" aria-label="Website of {{ organiser.name | escape }} (opens in a new tab)">{{ organiser.name | escape }}<i class="bi bi-box-arrow-up-right ms-1" aria-hidden="true"></i></a>
        {% else %}{{ organiser.name | escape }}{% endif %}
        <span class="d-block small text-secondary">{{ organiser.affiliation | escape }}</span>
      </li>
      {% endfor %}
    </ul>
  </div>
</section>

{% if event.funding and event.funding != '' %}
<section class="py-4 bg-body-tertiary" aria-label="Acknowledgements">
  <div class="container">
    <p class="small text-secondary mb-0">This workshop is supported in part by <a href="{{ event.funding_url }}" target="_blank" rel="noopener noreferrer">{{ event.funding }}</a>.</p>
  </div>
</section>
{% endif %}
