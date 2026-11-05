---
title: Laws & Regulations
permalink: /laws/
layout: single
classes: wide
---

Explore how laws and regulations apply throughout the third-party due diligence workflow.

<div class="law-filter-bar">
<label>
<span>Data type</span>
<select id="filter-type">
<option value="all">All Data Types</option>
<option value="identity">Identity Information</option>
<option value="financial">Financial Information</option>
<option value="criminal">Criminal Background Information</option>
<option value="sanctions">Sanctions Information</option>
</select>
</label>
<label>
<span>Jurisdiction</span>
<select id="filter-jurisdiction">
<option value="all">All Regions</option>
<option value="massachusetts">Massachusetts</option>
<option value="us">United States</option>
<option value="eu">European Union</option>
</select>
</label>
<button type="button" id="filter-reset" class="law-reset-btn">Reset</button>
</div>

<p id="law-count" class="law-count" aria-live="polite"></p>

## Law-to-Workflow Matrix

<div class="law-matrix">
<div class="law-header">
<div>Law</div>
<div>Pre-Screening</div>
<div>Verification</div>
<div>Criminal &amp; Legal</div>
<div>Financial</div>
<div>Sanctions</div>
<div>Monitoring</div>
</div>

<div class="law-row" data-jurisdiction="eu" data-types="identity financial criminal sanctions">
<div class="law-name" data-tip="Data protection and privacy requirements.">GDPR</div>
<div class="heat none"></div>
<div class="heat yes"></div>
<div class="heat yes"></div>
<div class="heat yes"></div>
<div class="heat yes"></div>
<div class="heat yes"></div>
</div>

<div class="law-row" data-jurisdiction="massachusetts" data-types="identity financial criminal sanctions">
<div class="law-name" data-tip="Massachusetts data security regulation.">201 CMR 17.00</div>
<div class="heat yes"></div>
<div class="heat yes"></div>
<div class="heat yes"></div>
<div class="heat yes"></div>
<div class="heat yes"></div>
<div class="heat yes"></div>
</div>

<div class="law-row" data-jurisdiction="massachusetts" data-types="identity financial criminal sanctions">
<div class="law-name" data-tip="Massachusetts personal information security law.">M.G.L. c.93H</div>
<div class="heat yes"></div>
<div class="heat yes"></div>
<div class="heat yes"></div>
<div class="heat yes"></div>
<div class="heat yes"></div>
<div class="heat yes"></div>
</div>

<div class="law-row" data-jurisdiction="us" data-types="criminal financial">
<div class="law-name" data-tip="Consumer reporting requirements.">FCRA</div>
<div class="heat none"></div>
<div class="heat none"></div>
<div class="heat yes"></div>
<div class="heat yes"></div>
<div class="heat none"></div>
<div class="heat yes"></div>
</div>

<div class="law-row" data-jurisdiction="us" data-types="financial">
<div class="law-name" data-tip="Financial information safeguards.">GLBA</div>
<div class="heat none"></div>
<div class="heat none"></div>
<div class="heat none"></div>
<div class="heat yes"></div>
<div class="heat none"></div>
<div class="heat yes"></div>
</div>

<div class="law-row" data-jurisdiction="us" data-types="sanctions">
<div class="law-name" data-tip="Sanctions compliance obligations.">OFAC</div>
<div class="heat none"></div>
<div class="heat none"></div>
<div class="heat none"></div>
<div class="heat none"></div>
<div class="heat yes"></div>
<div class="heat yes"></div>
</div>
</div>

<p class="law-note">Applicability is an educational mapping of this project's workflow, not legal advice.</p>

## Regulatory Reference Library

<div class="law-card-grid">

<a class="law-card j-eu" href="{{ '/laws/gdpr/' | relative_url }}" data-jurisdiction="eu" data-types="identity financial criminal sanctions">
<span class="law-badge">European Union</span>
<h3>GDPR</h3>
<p>Data protection and privacy requirements.</p>
<div class="law-tags"><span>Identity</span><span>Financial</span><span>Criminal</span><span>Sanctions</span></div>
</a>

<a class="law-card j-massachusetts" href="{{ '/laws/201-cmr-17/' | relative_url }}" data-jurisdiction="massachusetts" data-types="identity financial criminal sanctions">
<span class="law-badge">Massachusetts</span>
<h3>201 CMR 17.00</h3>
<p>Massachusetts data security regulation.</p>
<div class="law-tags"><span>Identity</span><span>Financial</span><span>Criminal</span><span>Sanctions</span></div>
</a>

<a class="law-card j-massachusetts" href="{{ '/laws/mgl-c93h/' | relative_url }}" data-jurisdiction="massachusetts" data-types="identity financial criminal sanctions">
<span class="law-badge">Massachusetts</span>
<h3>M.G.L. c.93H</h3>
<p>Massachusetts personal information security law.</p>
<div class="law-tags"><span>Identity</span><span>Financial</span><span>Criminal</span><span>Sanctions</span></div>
</a>

<a class="law-card j-us" href="{{ '/laws/glba/' | relative_url }}" data-jurisdiction="us" data-types="financial">
<span class="law-badge">United States</span>
<h3>GLBA</h3>
<p>Financial information safeguards.</p>
<div class="law-tags"><span>Financial</span></div>
</a>

<a class="law-card j-us" href="{{ '/laws/fcra/' | relative_url }}" data-jurisdiction="us" data-types="criminal financial">
<span class="law-badge">United States</span>
<h3>FCRA</h3>
<p>Consumer reporting requirements.</p>
<div class="law-tags"><span>Criminal</span><span>Financial</span></div>
</a>

<a class="law-card j-us" href="{{ '/laws/ofac/' | relative_url }}" data-jurisdiction="us" data-types="sanctions">
<span class="law-badge">United States</span>
<h3>OFAC</h3>
<p>Sanctions compliance obligations.</p>
<div class="law-tags"><span>Sanctions</span></div>
</a>

</div>

<p id="law-empty" class="law-empty" hidden>No laws match these filters. Try resetting them.</p>

<script>

var typeSelect = document.getElementById('filter-type');
var jurisdictionSelect = document.getElementById('filter-jurisdiction');
var resetButton = document.getElementById('filter-reset');
var count = document.getElementById('law-count');
var empty = document.getElementById('law-empty');
var rows = document.querySelectorAll('.law-row');
var cards = document.querySelectorAll('.law-card');
var phases = document.querySelectorAll('.law-header div');

rows.forEach(function (row) {

  var lawName = row.querySelector('.law-name').textContent;
  var cells = row.querySelectorAll('.heat');

  cells.forEach(function (cell, i) {

    var phase = phases[i + 1].textContent;

    if (cell.classList.contains('yes')) {
      cell.dataset.tip = lawName + ' applies in ' + phase;
    } else {
      cell.dataset.tip = lawName + ' does not apply in ' + phase;
    }
  });
});

function matches(item) {

  var type = typeSelect.value;
  var jurisdiction = jurisdictionSelect.value;

  var typeOk = type == 'all' || item.dataset.types.split(' ').indexOf(type) != -1;
  var jurisdictionOk = jurisdiction == 'all' || item.dataset.jurisdiction == jurisdiction;

  return typeOk && jurisdictionOk;
}

function applyFilters() {

  var shown = 0;

  rows.forEach(function (row) {
    row.hidden = !matches(row);
    if (!row.hidden) {
      shown++;
    }
  });

  cards.forEach(function (card) {
    card.hidden = !matches(card);
  });

  count.textContent = 'Showing ' + shown + ' of ' + rows.length + ' laws';
  empty.hidden = shown != 0;
}

typeSelect.addEventListener('change', applyFilters);
jurisdictionSelect.addEventListener('change', applyFilters);

resetButton.addEventListener('click', function () {
  typeSelect.value = 'all';
  jurisdictionSelect.value = 'all';
  applyFilters();
});

applyFilters();

</script>