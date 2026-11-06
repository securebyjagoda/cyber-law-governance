---
title: Data Classification Center
permalink: /data-classification-center/
layout: single
classes: wide
---

<p class="dc-kicker">Classify. Govern. Protect.</p>

A centralized library of the data categories collected during corporate due diligence, third-party screening, and background checks. Select a category for a quick summary of its sensitivity, risks, and governing laws, then open its full page for the details.

<div class="dc-cards">
{% for type in site.data.data_types %}<button type="button" class="dc-card lvl-{{ type.level }}" data-id="{{ type.id }}">
<span class="dc-card-name">{{ type.name }}</span>
<span class="dc-card-text">{{ type.tagline }}</span>
<span class="dc-card-level"><span class="dc-bars">{% for i in (1..3) %}<i class="{% if i <= type.level %}on{% endif %}"></i>{% endfor %}</span>{{ type.sensitivity }} sensitivity</span>
</button>
{% endfor %}
</div>

<div class="dc-profiles">
{% for type in site.data.data_types %}
<div class="dc-profile lvl-{{ type.level }}" id="profile-{{ type.id }}" hidden>

<div class="dc-head">
<h2>{{ type.name }}</h2>
<span class="dc-tier lvl-{{ type.level }}">{{ type.sensitivity }}</span>
</div>

<p class="dc-summary">{{ type.summary }}</p>

<div class="dc-facts">
<div><h4>Why it is sensitive</h4><p>{{ type.sensitive }}</p></div>
<div><h4>Typical data</h4><p>{{ type.typical }}</p></div>
<div><h4>Main risks</h4><p>{{ type.risks }}</p></div>
<div><h4>How to protect it</h4><p>{{ type.protect }}</p></div>
</div>

<div class="dc-laws">
<h4>Governing laws</h4>
<div class="dc-law-list">{% for law in type.laws %}{% if law.url %}<a href="{{ law.url | relative_url }}">{{ law.name }}</a>{% else %}<span>{{ law.name }}</span>{% endif %}{% endfor %}</div>
</div>

<p class="dc-phases"><b>Workflow phases:</b> {{ type.phases }} (<a href="{{ '/workflow/' | relative_url }}">see workflow</a>)</p>

<a class="dc-open" href="{{ type.url | relative_url }}">View full page &rarr;</a>

</div>
{% endfor %}
</div>

<p class="dc-note">Sensitivity ratings and handling guidance are an educational assessment for this project, not legal advice.</p>

<script>

var cards = document.querySelectorAll('.dc-card');
var profiles = document.querySelectorAll('.dc-profile');

function showProfile(id) {

  var found = false;

  cards.forEach(function (card) {
    if (card.dataset.id == id) {
      found = true;
    }
  });

  if (!found) {
    id = cards[0].dataset.id;
  }

  cards.forEach(function (card) {
    card.classList.toggle('active', card.dataset.id == id);
  });

  profiles.forEach(function (profile) {
    profile.hidden = profile.id != 'profile-' + id;
  });
}

cards.forEach(function (card) {
  card.addEventListener('click', function () {
    showProfile(card.dataset.id);
    history.replaceState(null, '', '#' + card.dataset.id);
  });
});

showProfile(window.location.hash.slice(1));

</script>