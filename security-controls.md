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
{% assign fws = "soc2,iso27001" | split: "," %}

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

<div class="ctl-legend">
<span class="lane-protect">Protect</span>
<span class="lane-monitor">Monitor</span>
<span class="lane-govern">Govern</span>
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
</div>

<p class="ctl-purpose">{{ c.purpose }}</p>

<div class="ctl-obj">
{% for o in c.objectives %}<span class="ctl-badge">{{ o | capitalize }}</span>{% endfor %}{% if c.marker %}<span class="ctl-badge marker">{{ c.marker }}</span>{% endif %}
</div>

<div class="ctl-map">

<div class="ctl-map-col">
<h4>{{ c.protects_label | default: "Protects" }}</h4>
<div class="ctl-tags">
{% if c.protects == "all" %}{% for t in site.data.data_types %}<a href="{{ t.url | relative_url }}">{{ t.name }}</a>{% endfor %}{% else %}{% for did in c.protects %}{% assign t = site.data.data_types | where: "id", did | first %}<a href="{{ t.url | relative_url }}">{{ t.name }}</a>{% endfor %}{% endif %}
</div>
</div>

<div class="ctl-map-col">
<h4>Applied in</h4>
<div class="ctl-tags">{% for p in c.phases %}{% assign idx = p | minus: 1 %}<a href="{{ '/workflow/' | relative_url }}">Phase {{ p }}: {{ phase_names[idx] }}</a>{% endfor %}</div>
</div>

</div>

<div class="ctl-block">
<h4>Required or supported by</h4>
<ul class="ctl-laws">
{% for l in c.laws %}<li>
<div class="ctl-law-top"><span class="ctl-law-name">{% if l.url %}<a href="{{ l.url | relative_url }}">{{ l.name }}</a>{% else %}{{ l.name }}{% endif %}</span><span class="ctl-ref">{{ l.ref }}</span></div>
<small>{{ l.note }}</small>
</li>
{% endfor %}
</ul>
</div>

<div class="ctl-block ctl-gov">
<h4>Governance considerations</h4>
<p>{{ c.governance }}</p>
</div>

<div class="ctl-block ctl-refs">
<h4>Authoritative references</h4>
<ul>
{% for r in c.references %}<li><a href="{{ r.url }}" target="_blank" rel="noopener">{{ r.name }}</a><small>{{ r.publisher }}{% if r.detail %} &middot; {{ r.detail }}{% endif %}{% if r.checked %} &middot; Checked {{ r.checked }}{% endif %}</small></li>
{% endfor %}
</ul>
</div>


{% endfor %}
</div>

<section class="asr" id="assurance">

<h2 class="asr-title">How vendors prove their controls: SOC 2 and ISO 27001</h2>

<p class="asr-intro">In due diligence, a vendor saying that it uses encryption is not enough. Two frameworks are requested most often: SOC 2, an independent auditor's report, and ISO 27001, a certified management system. Select a framework, then a criterion or theme, to see which controls from this page it covers.</p>

<div class="asr-tabs">
<button type="button" class="asr-tab active" data-tab="soc2">SOC 2</button>
<button type="button" class="asr-tab" data-tab="iso27001">ISO/IEC 27001</button>
</div>

{% for fw in fws %}{% assign f = site.data.assurance[fw] %}
<div class="asr-panel" id="asr-{{ fw }}"{% unless forloop.first %} hidden{% endunless %}>

<div class="asr-grid">
<div class="asr-box"><h4>What it is</h4><p>{{ f.what }}</p></div>
<div class="asr-box"><h4>Who it applies to</h4><p>{{ f.applies }}</p></div>
<div class="asr-box"><h4>What it shows</h4><p>{{ f.shows }}</p></div>
</div>

<div class="asr-grid">
{% for x in f.facts %}<div class="asr-box"><h4>{{ x.title }}</h4><p>{{ x.text }}</p></div>
{% endfor %}
</div>

<h3 class="asr-sub">{{ f.items_title }}</h3>

<div class="asr-chips">
{% for it in f.items %}<button type="button" class="asr-chip{% if forloop.first %} active{% endif %}" data-fw="{{ fw }}" data-id="{{ it.id }}"><b>{{ it.name }}</b><span>{{ it.tag }}</span></button>
{% endfor %}
</div>

{% for it in f.items %}<div class="asr-detail" data-fw="{{ fw }}" data-id="{{ it.id }}"{% unless forloop.first %} hidden{% endunless %}>
<p>{{ it.summary }}</p>
<p><b>Examples:</b> {{ it.examples }}</p>
{% if it.controls.size > 0 %}<h4>Controls on this page</h4>
<div class="asr-tags">{% for cid in it.controls %}{% assign ctl = site.data.controls | where: "id", cid | first %}<a href="#{{ cid }}">{{ ctl.name }}</a>{% endfor %}</div>{% endif %}
{% if it.gap %}<p class="asr-gap">{{ it.gap }}</p>{% endif %}
{% if it.links %}<h4>Related GDPR articles</h4>
<div class="asr-tags">{% for l in it.links %}<a href="{{ l.url | relative_url }}">{{ l.name }}</a>{% endfor %}</div>{% endif %}
</div>
{% endfor %}

<div class="asr-grid">
<div class="asr-box"><h4>Why it matters in due diligence</h4><p>{{ f.why }}</p></div>
<div class="asr-box"><h4>What to check</h4>
<ul>
{% for ck in f.check %}<li>{{ ck }}</li>
{% endfor %}
</ul>
</div>
<div class="asr-box"><h4>Official sources</h4>
<ul>
{% for r in f.references %}<li><a href="{{ r.url }}" target="_blank" rel="noopener">{{ r.name }}</a><small>{{ r.publisher }}{% if r.detail %} &middot; {{ r.detail }}{% endif %}</small></li>
{% endfor %}
</ul>
</div>
</div>

</div>
{% endfor %}

</section>

<p class="ctl-note">This page is an educational mapping for this project, not legal advice. Reference links point to government and standards bodies. CIS, ISO, and SOC 2 identifiers are shown only as cross-references, and some rules apply only to certain organizations, so check the current text of each provision before relying on it.</p>

<script>

var controls = document.querySelectorAll('.ctl-node, .ctl-card');
var nodes = document.querySelectorAll('.ctl-node');
var corners = document.querySelectorAll('.ctl-corner');
var profiles = document.querySelectorAll('.ctl-profile');
var objective = '';
var current = '';

function hasControl(id) {

  var found = false;

  controls.forEach(function (c) {
    if (c.dataset.id == id) {
      found = true;
    }
  });

  return found;
}

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

  if (!hasControl(id)) {
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

window.addEventListener('hashchange', function () {
  var h = window.location.hash.slice(1);
  if (hasControl(h)) {
    showControl(h, true);
  }
});

showControl(window.location.hash.slice(1), false);

var asrTabs = document.querySelectorAll('.asr-tab');
var asrPanels = document.querySelectorAll('.asr-panel');
var asrChips = document.querySelectorAll('.asr-chip');
var asrDetails = document.querySelectorAll('.asr-detail');

asrTabs.forEach(function (tab) {
  tab.addEventListener('click', function () {
    asrTabs.forEach(function (t) {
      t.classList.toggle('active', t == tab);
    });
    asrPanels.forEach(function (p) {
      p.hidden = p.id != 'asr-' + tab.dataset.tab;
    });
  });
});

asrChips.forEach(function (chip) {
  chip.addEventListener('click', function () {
    asrChips.forEach(function (c) {
      if (c.dataset.fw == chip.dataset.fw) {
        c.classList.toggle('active', c == chip);
      }
    });
    asrDetails.forEach(function (d) {
      if (d.dataset.fw == chip.dataset.fw) {
        d.hidden = d.dataset.id != chip.dataset.id;
      }
    });
  });
});

</script>