---
title: Data Classification Center
permalink: /data-classification-center/
layout: single
classes: wide
---

<p class="dc-kicker">Classify. Govern. Protect.</p>

A centralized resource for understanding how information collected during corporate due diligence, third-party screening, and background check processes should be classified, governed, protected, retained, and disposed of. Select a data category to see its sensitivity, risks, governing laws, and recommended controls, then open its full page for more detail.

<div class="dc-layout">

<div class="dc-index">
{% for type in site.data.data_types %}<button type="button" class="dc-item lvl-{{ type.level }}" data-id="{{ type.id }}">{{ type.name }}<small>{{ type.sensitivity }} sensitivity</small></button>
{% endfor %}
<p class="dc-note">Sensitivity ratings and handling guidance are an educational assessment for this project, not legal advice.</p>
</div>

<div class="dc-profiles">
{% for type in site.data.data_types %}
<div class="dc-profile" id="profile-{{ type.id }}" hidden>

<div class="dc-head">
<h2>{{ type.name }}</h2>
<span class="dc-tier lvl-{{ type.level }}">{{ type.sensitivity }}</span>
</div>

<div class="dc-scale lvl-{{ type.level }}">
<div class="dc-bars">{% for i in (1..3) %}<span class="{% if i <= type.level %}on{% endif %}"></span>{% endfor %}</div>
<div class="dc-scale-labels"><span>Medium</span><span>High</span><span>Very High</span></div>
</div>

<p class="dc-summary">{{ type.overview }}</p>
<p class="dc-sens">{{ type.sensitivity_note }}</p>
<p class="dc-where"><b>Workflow phases:</b> {{ type.phases }} (<a href="{{ '/workflow/' | relative_url }}">see workflow</a>)</p>

<div class="dc-blocks">

<div class="dc-block">
<h4>Common examples</h4>
<ul>
{% for item in type.examples %}<li>{{ item }}</li>
{% endfor %}
</ul>
</div>

<div class="dc-block">
<h4>{{ type.why_title | default: "Why it matters" }}</h4>
<ul>
{% for item in type.why %}<li>{{ item }}</li>
{% endfor %}
</ul>
</div>

<div class="dc-block">
<h4>Risks</h4>
<ul>
{% for risk in type.risks %}<li>{{ risk }}</li>
{% endfor %}
</ul>
</div>

<div class="dc-block">
<h4>Governing laws</h4>
<ul>
{% for law in type.laws %}<li>{% if law.url %}<a href="{{ law.url | relative_url }}">{{ law.name }}</a>{% else %}{{ law.name }}{% endif %}{% if law.note %} <small>({{ law.note }})</small>{% endif %}</li>
{% endfor %}
</ul>
</div>

<div class="dc-block wide">
<h4>Recommended governance approach</h4>
<ul>
{% for item in type.governance %}<li>{{ item }}</li>
{% endfor %}
</ul>
</div>

{% if type.special %}<div class="dc-block wide">
<h4>{{ type.special_title | default: "Special considerations" }}</h4>
<p>{{ type.special_intro }}</p>
<ul>
{% for item in type.special %}<li>{{ item }}</li>
{% endfor %}
</ul>
</div>
{% endif %}

<div class="dc-block wide">
<h4>Recommended security controls</h4>
<div class="dc-controls">
{% for group in type.controls %}<div><b>{{ group.group }}</b>
<ul>
{% for item in group.items %}<li>{{ item }}</li>
{% endfor %}
</ul>
</div>
{% endfor %}
</div>
</div>

</div>

<a class="dc-open" href="{{ type.url | relative_url }}">View full page &rarr;</a>

</div>
{% endfor %}
</div>

</div>

<script>

var items = document.querySelectorAll('.dc-item');
var profiles = document.querySelectorAll('.dc-profile');

function showProfile(id) {

  var found = false;

  items.forEach(function (item) {
    if (item.dataset.id == id) {
      found = true;
    }
  });

  if (!found) {
    id = items[0].dataset.id;
  }

  items.forEach(function (item) {
    item.classList.toggle('active', item.dataset.id == id);
  });

  profiles.forEach(function (profile) {
    profile.hidden = profile.id != 'profile-' + id;
  });
}

items.forEach(function (item) {
  item.addEventListener('click', function () {
    showProfile(item.dataset.id);
    history.replaceState(null, '', '#' + item.dataset.id);
  });
});

showProfile(window.location.hash.slice(1));

</script>