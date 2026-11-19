---
title: Security Controls
permalink: /security-controls/
layout: single
classes: wide
---

<p class="ctl-kicker">Protect. Monitor. Govern.</p>

A reference library of the cybersecurity controls used throughout the third-party due diligence process. Learn about specific controls, how they protect the CIA triad, their applicability and official frameworks.

{% assign phase_names = "Pre-Screening,Verification,Criminal & Legal,Financial,Sanctions,Monitoring" | split: "," %}
{% assign lanes = "Protect,Monitor,Govern" | split: "," %}

<div class="ctl-top">

<div class="ctl-triad">
<svg viewBox="0 0 560 440" role="img" aria-label="Confidentiality, integrity, availability triangle with controls placed by the objectives they serve">
<polygon class="ctl-shape" points="280,50 80,380 480,380"></polygon>
{% for c in site.data.controls %}{% if c.triad %}<g class="ctl-node lane-{{ c.lane | downcase }}" data-id="{{ c.id }}" data-obj="{{ c.objectives | join: ' ' }}" tabindex="0">
<circle cx="{{ c.triad[0] }}" cy="{{ c.triad[1] }}" r="10"></circle>
{% if c.label == "left" %}<text x="{{ c.triad[0] | minus: 16 }}" y="{{ c.triad[1] | plus: 5 }}" text-anchor="end">{{ c.short }}</text>{% else %}<text x="{{ c.triad[0] | plus: 16 }}" y="{{ c.triad[1] | plus: 5 }}">{{ c.short }}</text>{% endif %}
</g>
{% endif %}{% endfor %}
<g class="ctl-corner" data-obj="confidentiality">
<circle cx="280" cy="50" r="16"></circle>
<text x="280" y="56" text-anchor="middle">C</text>
<text x="304" y="56" class="ctl-corner-name">Confidentiality</text>
</g>
<g class="ctl-corner" data-obj="integrity">
<circle cx="80" cy="380" r="16"></circle>
<text x="80" y="386" text-anchor="middle">I</text>
<text x="80" y="418" text-anchor="middle" class="ctl-corner-name">Integrity</text>
</g>
<g class="ctl-corner" data-obj="availability">
<circle cx="480" cy="380" r="16"></circle>
<text x="480" y="386" text-anchor="middle">A</text>
<text x="480" y="418" text-anchor="middle" class="ctl-corner-name">Availability</text>
</g>
</svg>

<p class="ctl-caption">Near a corner, a control mainly serves one objective. On an edge, it serves two. In the middle, it serves all three. Click a corner to highlight the controls that serve it.</p>

<div class="ctl-outside">
<div>
<b>Detection and accountability</b>
<span>They record and watch activity instead of preventing it, so they sit outside the triangle.</span>
{% for c in site.data.controls %}{% if c.outside == "detection" %}<button type="button" class="ctl-chip lane-{{ c.lane | downcase }}" data-id="{{ c.id }}" data-obj="{{ c.objectives | join: ' ' }}">{{ c.name }}</button>{% endif %}{% endfor %}
</div>
<div>
<b>Program-level</b>
<span>It governs how vendors handle all three objectives.</span>
{% for c in site.data.controls %}{% if c.outside == "program" %}<button type="button" class="ctl-chip lane-{{ c.lane | downcase }}" data-id="{{ c.id }}" data-obj="{{ c.objectives | join: ' ' }}">{{ c.name }}</button>{% endif %}{% endfor %}
</div>
</div>

</div>

<div class="ctl-lanes">
{% for lane in lanes %}
<div class="ctl-lane">
<h3 class="ctl-lane-title lane-{{ lane | downcase }}">{{ lane }}</h3>
<div class="ctl-cards">
{% for c in site.data.controls %}{% if c.lane == lane %}<button type="button" class="ctl-card lane-{{ lane | downcase }}" data-id="{{ c.id }}" data-obj="{{ c.objectives | join: ' ' }}">
<span class="ctl-card-name">{{ c.name }}</span>
<span class="ctl-card-text">{{ c.tagline }}</span>
<span class="ctl-dots">{% if c.objectives.size > 0 %}<i class="{% if c.objectives contains 'confidentiality' %}on{% endif %}">C</i><i class="{% if c.objectives contains 'integrity' %}on{% endif %}">I</i><i class="{% if c.objectives contains 'availability' %}on{% endif %}">A</i>{% endif %}{% if c.marker %}<em>{{ c.marker }}</em>{% endif %}</span>
</button>
{% endif %}{% endfor %}
</div>
</div>
{% endfor %}
</div>

</div>

<div class="ctl-profiles">
{% for c in site.data.controls %}
<div class="ctl-profile lane-{{ c.lane | downcase }}" id="profile-{{ c.id }}" hidden>

<div class="ctl-head">
<h2>{{ c.name }}</h2>
<span class="ctl-lane-tag lane-{{ c.lane | downcase }}">{{ c.lane }}</span>
</div>

<p class="ctl-purpose">{{ c.purpose }}</p>

<div class="ctl-obj">
{% for o in c.objectives %}<span class="ctl-badge">{{ o | capitalize }}</span>{% endfor %}{% if c.marker %}<span class="ctl-badge marker">{{ c.marker }}</span>{% endif %}
</div>

<div class="ctl-map">

<div class="ctl-map-col">
<h4>Protects</h4>

<div class="ctl-tags">

{% for id in c.protects %}
{% assign t = site.data.data_types | where: "id", id | first %}

<a href="{{ t.url | relative_url }}">
  {{ t.name }}
</a>

{% endfor %}

</div>

<div class="ctl-map-col">
<h4>Required or supported by</h4>
<ul class="ctl-laws">
{% for l in c.laws %}<li><span class="ctl-law-name">{% if l.url %}<a href="{{ l.url | relative_url }}">{{ l.name }}</a>{% else %}{{ l.name }}{% endif %}</span> <span class="ctl-ref">{{ l.ref }}</span> <span class="ctl-kind {{ l.kind }}">{% if l.kind == "named" %}Named in the rule{% else %}Supports the rule{% endif %}</span><small>{{ l.note }}</small></li>
{% endfor %}
</ul>
</div>

<div class="ctl-map-col">
<h4>Applied in</h4>
<div class="ctl-tags">{% for p in c.phases %}{% assign idx = p | minus: 1 %}<a href="{{ '/workflow/' | relative_url }}">Phase {{ p }}: {{ phase_names[idx] }}</a>{% endfor %}</div>
</div>

</div>

<div class="ctl-gov">
<h4>Governance considerations</h4>
<p>{{ c.governance }}</p>
</div>

<div class="ctl-refs">
<h4>Authoritative references</h4>
<ul>
{% for r in c.references %}<li><a href="{{ r.url }}" target="_blank" rel="noopener">{{ r.name }}</a><small>{{ r.publisher }}{% if r.detail %} &middot; {{ r.detail }}{% endif %}{% if r.checked %} &middot; Checked {{ r.checked }}{% endif %}</small></li>
{% endfor %}
</ul>
</div>

<div class="ctl-cross">
<h4>Framework cross-references</h4>
<span><b>NIST CSF 2.0</b>{{ c.csf }}</span>
<span><b>NIST SP 800-53</b>{{ c.nist80053 }}</span>
<span><b>CIS Controls v8.1</b>{{ c.cis }}</span>
<span><b>ISO/IEC 27002:2022</b>{{ c.iso }}</span>
</div>

</div>
{% endfor %}
</div>

<p class="ctl-note">This page is an educational mapping for this project, not legal advice. Reference links point to government and standards bodies. CIS and ISO identifiers are shown only as cross-references, and some rules apply only to certain organizations, so check the current text of each provision before relying on it.</p>

<script>

var controls = document.querySelectorAll('.ctl-node, .ctl-card, .ctl-chip');
var nodes = document.querySelectorAll('.ctl-node');
var corners = document.querySelectorAll('.ctl-corner');
var profiles = document.querySelectorAll('.ctl-profile');
var objective = '';
var current = '';

function objectivesOf(id) {

  var found = '';

  controls.forEach(function (c) {
    if (c.dataset.id == id) {
      found = c.dataset.obj;
    }
  });

  return found.split(' ');
}

function refresh() {

  var mine = objectivesOf(current);

  controls.forEach(function (c) {
    c.classList.toggle('active', c.dataset.id == current);
    c.classList.toggle('dim', objective != '' && c.dataset.obj.split(' ').indexOf(objective) == -1);
  });

  corners.forEach(function (corner) {
    corner.classList.toggle('lit', mine.indexOf(corner.dataset.obj) != -1);
    corner.classList.toggle('chosen', corner.dataset.obj == objective);
  });

  profiles.forEach(function (profile) {
    profile.hidden = profile.id != 'profile-' + current;
  });
}

function showControl(id, scroll) {

  var found = false;

  controls.forEach(function (c) {
    if (c.dataset.id == id) {
      found = true;
    }
  });

  if (!found) {
    id = document.querySelector('.ctl-card').dataset.id;
  }

  current = id;
  refresh();

  if (scroll) {
    document.getElementById('profile-' + id).scrollIntoView({ behavior: 'smooth', block: 'start' });
  }
}

controls.forEach(function (c) {
  c.addEventListener('click', function () {
    showControl(c.dataset.id, true);
    history.replaceState(null, '', '#' + c.dataset.id);
  });
});

nodes.forEach(function (node) {
  node.addEventListener('keydown', function (e) {
    if (e.key == 'Enter' || e.key == ' ') {
      e.preventDefault();
      showControl(node.dataset.id, true);
    }
  });
});

corners.forEach(function (corner) {
  corner.addEventListener('click', function () {
    objective = (objective == corner.dataset.obj) ? '' : corner.dataset.obj;
    refresh();
  });
});

showControl(window.location.hash.slice(1), false);

</script>
