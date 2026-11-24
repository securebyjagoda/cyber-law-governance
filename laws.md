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
<span>People located in</span>
<select id="filter-where">
<option value="all">Anywhere (all laws)</option>
<option value="ma">Massachusetts</option>
<option value="eu">The European Union</option>
<option value="us">Elsewhere in the U.S.</option>
</select>
</label>
<button type="button" id="filter-reset" class="law-reset-btn">Reset</button>
</div>

<p class="law-help">Massachusetts laws apply to Massachusetts residents, and the GDPR to people in the EU. FCRA, GLBA, and OFAC always appear because they depend on what your company does, not on where people live.</p>

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

<div class="law-row" data-where="eu" data-types="identity financial criminal sanctions">
<div class="law-name" data-tip="Applies when individuals are in the EU, or the company operates there.">GDPR</div>
<div class="heat none"></div>
<div class="heat yes"></div>
<div class="heat yes"></div>
<div class="heat yes"></div>
<div class="heat yes"></div>
<div class="heat yes"></div>
</div>

<div class="law-row" data-where="ma" data-types="identity financial criminal sanctions">
<div class="law-name" data-tip="Applies when the company holds personal information of Massachusetts residents.">201 CMR 17.00</div>
<div class="heat yes"></div>
<div class="heat yes"></div>
<div class="heat yes"></div>
<div class="heat yes"></div>
<div class="heat yes"></div>
<div class="heat yes"></div>
</div>

<div class="law-row" data-where="ma" data-types="identity financial criminal sanctions">
<div class="law-name" data-tip="Applies when a breach involves personal information of Massachusetts residents.">M.G.L. c.93H</div>
<div class="heat yes"></div>
<div class="heat yes"></div>
<div class="heat yes"></div>
<div class="heat yes"></div>
<div class="heat yes"></div>
<div class="heat yes"></div>
</div>

<div class="law-row" data-where="any" data-types="criminal financial">
<div class="law-name" data-tip="Applies when consumer reports, such as background checks, are used.">FCRA</div>
<div class="heat none"></div>
<div class="heat none"></div>
<div class="heat yes"></div>
<div class="heat yes"></div>
<div class="heat none"></div>
<div class="heat yes"></div>
</div>

<div class="law-row" data-where="any" data-types="financial">
<div class="law-name" data-tip="Applies when the company is a covered financial institution.">GLBA</div>
<div class="heat none"></div>
<div class="heat none"></div>
<div class="heat none"></div>
<div class="heat yes"></div>
<div class="heat none"></div>
<div class="heat yes"></div>
</div>

<div class="law-row" data-where="any" data-types="sanctions">
<div class="law-name" data-tip="Applies when a U.S. person deals with a sanctioned party or country.">OFAC</div>
<div class="heat none"></div>
<div class="heat none"></div>
<div class="heat none"></div>
<div class="heat none"></div>
<div class="heat yes"></div>
<div class="heat yes"></div>
</div>
</div>

<p class="law-note">Applicability is an educational mapping of this project's workflow, not legal advice. This library covers Massachusetts, U.S. federal, and EU law only.</p>

## Regulatory Reference Library

<div class="law-card-grid">

<a class="law-card j-eu" href="{{ '/laws/gdpr/' | relative_url }}" data-where="eu" data-types="identity financial criminal sanctions">
<span class="law-badge">European Union</span>
<h3>GDPR</h3>
<p>Data protection and privacy requirements.</p>
<p class="law-when"><b>Applies when:</b> individuals are in the EU, or the company operates there.</p>
<div class="law-tags"><span>Identity</span><span>Financial</span><span>Criminal</span><span>Sanctions</span></div>
<p class="law-articles">Key articles: 4, 5, 6, 10, 25, 28, 32, 33, 35, 44-46</p>
</a>

<a class="law-card j-massachusetts" href="{{ '/laws/201-cmr-17/' | relative_url }}" data-where="ma" data-types="identity financial criminal sanctions">
<span class="law-badge">Massachusetts</span>
<h3>201 CMR 17.00</h3>
<p>Massachusetts data security regulation.</p>
<p class="law-when"><b>Applies when:</b> the company holds personal information of Massachusetts residents.</p>
<div class="law-tags"><span>Identity</span><span>Financial</span><span>Criminal</span><span>Sanctions</span></div>
</a>

<a class="law-card j-massachusetts" href="{{ '/laws/mgl-c93h/' | relative_url }}" data-where="ma" data-types="identity financial criminal sanctions">
<span class="law-badge">Massachusetts</span>
<h3>M.G.L. c.93H</h3>
<p>Massachusetts personal information security law.</p>
<p class="law-when"><b>Applies when:</b> a breach involves personal information of Massachusetts residents.</p>
<div class="law-tags"><span>Identity</span><span>Financial</span><span>Criminal</span><span>Sanctions</span></div>
</a>

<a class="law-card j-us" href="{{ '/laws/glba/' | relative_url }}" data-where="any" data-types="financial">
<span class="law-badge">United States</span>
<h3>GLBA</h3>
<p>Financial information safeguards.</p>
<p class="law-when"><b>Applies when:</b> the company is a covered financial institution.</p>
<div class="law-tags"><span>Financial</span></div>
</a>

<a class="law-card j-us" href="{{ '/laws/fcra/' | relative_url }}" data-where="any" data-types="criminal financial">
<span class="law-badge">United States</span>
<h3>FCRA</h3>
<p>Consumer reporting requirements.</p>
<p class="law-when"><b>Applies when:</b> consumer reports, such as background checks, are used.</p>
<div class="law-tags"><span>Criminal</span><span>Financial</span></div>
</a>

<a class="law-card j-us" href="{{ '/laws/ofac/' | relative_url }}" data-where="any" data-types="sanctions">
<span class="law-badge">United States</span>
<h3>OFAC</h3>
<p>Sanctions compliance obligations.</p>
<p class="law-when"><b>Applies when:</b> a U.S. person deals with a sanctioned party or country.</p>
<div class="law-tags"><span>Sanctions</span></div>
</a>

</div>

<p id="law-empty" class="law-empty" hidden>No laws match these filters. Try resetting them.</p>

<script>

var typeSelect = document.getElementById('filter-type');
var whereSelect = document.getElementById('filter-where');
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
  var where = whereSelect.value;
  var itemWhere = item.dataset.where;

  var typeOk = type == 'all' || item.dataset.types.split(' ').indexOf(type) != -1;
  var whereOk = where == 'all' || itemWhere == 'any' || itemWhere == where;

  return typeOk && whereOk;
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
whereSelect.addEventListener('change', applyFilters);

resetButton.addEventListener('click', function () {
  typeSelect.value = 'all';
  whereSelect.value = 'all';
  applyFilters();
});

applyFilters();

</script>