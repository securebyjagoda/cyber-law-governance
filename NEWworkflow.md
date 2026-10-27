---
title: "Workflow Explorer"
permalink: /workflow/
layout: single
classes: wide
---

<style>
/* =========================================
   DUE DILIGENCE WORKFLOW
   Minimal Mistakes compatible styling
   ========================================= */

.workflow-page {
  width: 100%;
  margin: 0 auto;
}

/* ---------- Intro ---------- */

.workflow-intro {
  margin: 1.5rem 0 2.5rem;
  padding: 1.5rem 1.75rem;
  border-left: 4px solid #2f7fbd;
  border-radius: 6px;
  background: rgba(47, 127, 189, 0.07);
}

.workflow-intro p:last-child {
  margin-bottom: 0;
}

/* ---------- Workflow ---------- */

.workflow-section {
  margin: 2.5rem 0 3rem;
}

.workflow-flow {
  display: flex;
  width: 100%;
  align-items: center;
  justify-content: center;
  gap: 0;
  margin-top: 1.5rem;
}

.flow-step {
  flex: 1 1 0;
  min-width: 0;
  padding: 1.25rem 0.65rem;
  text-align: center;
  border: 1px solid #d9e2ec;
  border-radius: 10px;
  background: #ffffff;
  box-shadow: 0 3px 10px rgba(0, 0, 0, 0.06);
  transition:
    transform 0.2s ease,
    box-shadow 0.2s ease;
}

.flow-step:hover {
  transform: translateY(-3px);
  box-shadow: 0 7px 18px rgba(0, 0, 0, 0.11);
}

.flow-number {
  display: flex;
  width: 34px;
  height: 34px;
  margin: 0 auto 0.7rem;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  background: #2f7fbd;
  color: #ffffff;
  font-size: 0.85rem;
  font-weight: 700;
}

.flow-title {
  font-size: 0.82rem;
  font-weight: 700;
  line-height: 1.35;
}

.flow-arrow {
  flex: 0 0 auto;
  padding: 0 0.4rem;
  color: #2f7fbd;
  font-size: 1.35rem;
  font-weight: 700;
}

/* ---------- Phase Cards ---------- */

.phase-grid {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 1.5rem;
  margin-top: 2rem;
}

.phase-card {
  overflow: hidden;
  border: 1px solid #d9e2ec;
  border-radius: 10px;
  background: #ffffff;
  box-shadow: 0 3px 12px rgba(0, 0, 0, 0.07);
  transition:
    transform 0.2s ease,
    box-shadow 0.2s ease;
}

.phase-card:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 22px rgba(0, 0, 0, 0.11);
}

/* ---------- Phase header ---------- */

.phase-header {
  padding: 1.2rem 1.4rem;
  background: linear-gradient(135deg, #183b5b, #256b9e);
  color: #ffffff;
}

.phase-header .phase-number {
  display: block;
  margin-bottom: 0.25rem;
  color: #b9dcf5;
  font-size: 0.7rem;
  font-weight: 700;
  letter-spacing: 0.08em;
  text-transform: uppercase;
}

.phase-header h2 {
  margin: 0;
  color: #ffffff;
  font-size: 1.15rem;
  line-height: 1.35;
}

/* ---------- Phase body ---------- */

.phase-body {
  padding: 1.35rem 1.4rem 1.5rem;
}

.phase-purpose {
  margin: 0 0 1.4rem;
  color: #4b5563;
  font-size: 0.92rem;
  line-height: 1.6;
}

/* ---------- Detail sections ---------- */

.detail-section {
  margin-top: 1.2rem;
  padding-top: 1rem;
  border-top: 1px solid #edf0f3;
}

.detail-section:first-of-type {
  margin-top: 0;
}

.detail-section h3 {
  margin: 0 0 0.55rem;
  font-size: 0.9rem;
  line-height: 1.3;
}

.detail-section ul {
  margin: 0;
  padding-left: 1.2rem;
}

.detail-section li {
  margin-bottom: 0.3rem;
  font-size: 0.84rem;
  line-height: 1.45;
}

/* Category color coding */

.data h3 {
  color: #2563eb;
}

.laws h3 {
  color: #7c3aed;
}

.risks h3 {
  color: #c2410c;
}

.governance h3 {
  color: #047857;
}

.controls h3 {
  color: #0369a1;
}

/* ---------- Dark mode ---------- */

@media (prefers-color-scheme: dark) {
  .workflow-intro {
    background: rgba(47, 127, 189, 0.12);
  }

  .flow-step,
  .phase-card {
    background: #1f2428;
    border-color: #3b4248;
  }

  .phase-purpose {
    color: #c9d1d9;
  }

  .detail-section {
    border-top-color: #3b4248;
  }
}

/* ---------- Tablet ---------- */

@media (max-width: 900px) {
  .workflow-flow {
    flex-direction: column;
  }

  .flow-step {
    width: 100%;
  }

  .flow-arrow {
    padding: 0.3rem 0;
    transform: rotate(90deg);
  }

  .phase-grid {
    grid-template-columns: 1fr;
  }
}

/* ---------- Mobile ---------- */

@media (max-width: 600px) {
  .workflow-intro {
    padding: 1.2rem;
  }

  .phase-grid {
    gap: 1rem;
  }

  .phase-body,
  .phase-header {
    padding-right: 1.1rem;
    padding-left: 1.1rem;
  }
}
</style>


<div class="workflow-page">

# Third-Party Due Diligence Workflow

<div class="workflow-intro">

## What is Due Diligence?

Corporate third-party due diligence is a structured process used to **collect, verify, and evaluate information** about a vendor, investor, contractor, supplier, or other third party before entering or maintaining a business relationship.

The process helps organizations **identify, assess, and manage risks** associated with third-party relationships and the data collected throughout the due diligence process.

</div>


<div class="workflow-section">

## Typical Workflow

<div class="workflow-flow">

<div class="flow-step">
<div class="flow-number">1</div>
<div class="flow-title">Pre-Screening</div>
</div>

<div class="flow-arrow">→</div>

<div class="flow-step">
<div class="flow-number">2</div>
<div class="flow-title">Verification</div>
</div>

<div class="flow-arrow">→</div>

<div class="flow-step">
<div class="flow-number">3</div>
<div class="flow-title">Criminal &amp;<br>Legal Checks</div>
</div>

<div class="flow-arrow">→</div>

<div class="flow-step">
<div class="flow-number">4</div>
<div class="flow-title">Financial<br>Checks</div>
</div>

<div class="flow-arrow">→</div>

<div class="flow-step">
<div class="flow-number">5</div>
<div class="flow-title">Sanctions<br>Screening</div>
</div>

<div class="flow-arrow">→</div>

<div class="flow-step">
<div class="flow-number">6</div>
<div class="flow-title">Decision &amp;<br>Monitoring</div>
</div>

</div>

</div>


# Workflow Phases

<div class="phase-grid">


<!-- PHASE 1 -->

<div class="phase-card">

<div class="phase-header">
<span class="phase-number">Phase 1</span>
<h2>Pre-Screening</h2>
</div>

<div class="phase-body">

<p class="phase-purpose">
<strong>Purpose:</strong> Collecting basic information about the entity and establishing an initial risk profile.
</p>

<div class="detail-section data">
<h3>Data Categories</h3>
<ul>
<li>Corporate Information</li>
<li>Identity &amp; Personal Information</li>
</ul>
</div>

<div class="detail-section laws">
<h3>Applicable Laws</h3>
<ul>
<li>GDPR Article 5</li>
<li>GDPR Article 32</li>
<li>Massachusetts General Laws Chapter 93H</li>
<li>201 CMR 17.00</li>
</ul>
</div>

<div class="detail-section risks">
<h3>Privacy &amp; Security Risks</h3>
<ul>
<li>Excessive Data Collection</li>
<li>Unauthorized Access</li>
<li>Unauthorized Disclosure</li>
<li>Inaccurate Records</li>
</ul>
</div>

<div class="detail-section governance">
<h3>Governance Requirements</h3>
<ul>
<li>Written Information Security Program (WISP)</li>
<li>Vendor Management Program</li>
<li>Third-Party Risk Assessment</li>
<li>Data Classification Policy</li>
</ul>
</div>

<div class="detail-section controls">
<h3>Cybersecurity Controls</h3>
<ul>
<li>Access Control</li>
<li>Encryption</li>
<li>Audit Logging</li>
<li>Data Classification &amp; Labeling</li>
</ul>
</div>

</div>
</div>


<!-- PHASE 2 -->

<div class="phase-card">

<div class="phase-header">
<span class="phase-number">Phase 2</span>
<h2>Verification</h2>
</div>

<div class="phase-body">

<p class="phase-purpose">
<strong>Purpose:</strong> Validating information provided by the entity and establishing legitimacy.
</p>

<div class="detail-section data">
<h3>Data Categories</h3>
<ul>
<li>Corporate Information</li>
<li>Identity &amp; Personal Information</li>
<li>Legal &amp; Regulatory Information</li>
</ul>
</div>

<div class="detail-section laws">
<h3>Applicable Laws</h3>
<ul>
<li>Corporate Transparency Act (CTA)</li>
<li>GDPR Article 5</li>
<li>GDPR Article 6</li>
<li>GDPR Article 32</li>
<li>Massachusetts General Laws Chapter 93H</li>
<li>201 CMR 17.00</li>
</ul>
</div>

<div class="detail-section risks">
<h3>Privacy &amp; Security Risks</h3>
<ul>
<li>Identity Theft</li>
<li>Unauthorized Disclosure</li>
<li>Unauthorized Access</li>
<li>Excessive Data Collection</li>
<li>Inaccurate Records</li>
</ul>
</div>

<div class="detail-section governance">
<h3>Governance Requirements</h3>
<ul>
<li>Lawful Basis Assessment</li>
<li>Records of Processing Activities (ROPA)</li>
<li>Vendor Risk Assessment</li>
<li>Data Retention Schedule</li>
</ul>
</div>

<div class="detail-section controls">
<h3>Cybersecurity Controls</h3>
<ul>
<li>Authentication</li>
<li>Access Control</li>
<li>Encryption</li>
<li>Audit Logging</li>
</ul>
</div>

</div>
</div>


<!-- PHASE 3 -->

<div class="phase-card">

<div class="phase-header">
<span class="phase-number">Phase 3</span>
<h2>Criminal &amp; Legal Checks</h2>
</div>

<div class="phase-body">

<p class="phase-purpose">
<strong>Purpose:</strong> Assessing criminal, legal, and regulatory exposure associated with the entity.
</p>

<div class="detail-section data">
<h3>Data Categories</h3>
<ul>
<li>Criminal &amp; Background Information</li>
<li>Legal &amp; Regulatory Information</li>
</ul>
</div>

<div class="detail-section laws">
<h3>Applicable Laws</h3>
<ul>
<li>GDPR Article 10</li>
<li>GDPR Article 5</li>
<li>GDPR Article 32</li>
<li>Fair Credit Reporting Act (FCRA)</li>
<li>Massachusetts General Laws Chapter 93H</li>
<li>201 CMR 17.00</li>
</ul>
</div>

<div class="detail-section risks">
<h3>Privacy &amp; Security Risks</h3>
<ul>
<li>Unauthorized Disclosure</li>
<li>Unauthorized Access</li>
<li>Excessive Retention</li>
<li>Automated Decision-Making</li>
<li>Cross-Border Data Transfers</li>
<li>Inaccurate Records</li>
</ul>
</div>

<div class="detail-section governance">
<h3>Governance Requirements</h3>
<ul>
<li>Data Protection Impact Assessment (DPIA)</li>
<li>Lawful Basis Assessment</li>
<li>Records of Processing Activities (ROPA)</li>
<li>Human Review Procedure</li>
<li>Data Retention Schedule</li>
</ul>
</div>

<div class="detail-section controls">
<h3>Cybersecurity Controls</h3>
<ul>
<li>Encryption</li>
<li>Access Control</li>
<li>Audit Logging</li>
<li>Security Monitoring</li>
<li>Data Loss Prevention (DLP)</li>
</ul>
</div>

</div>
</div>


<!-- PHASE 4 -->

<div class="phase-card">

<div class="phase-header">
<span class="phase-number">Phase 4</span>
<h2>Financial Checks</h2>
</div>

<div class="phase-body">

<p class="phase-purpose">
<strong>Purpose:</strong> Evaluating financial health, stability, and financial risk.
</p>

<div class="detail-section data">
<h3>Data Categories</h3>
<ul>
<li>Financial Information</li>
<li>Corporate Information</li>
</ul>
</div>

<div class="detail-section laws">
<h3>Applicable Laws</h3>
<ul>
<li>Gramm-Leach-Bliley Act (GLBA)</li>
<li>Fair Credit Reporting Act (FCRA)</li>
<li>GDPR Article 5</li>
<li>GDPR Article 32</li>
<li>Massachusetts General Laws Chapter 93H</li>
<li>201 CMR 17.00</li>
</ul>
</div>

<div class="detail-section risks">
<h3>Privacy &amp; Security Risks</h3>
<ul>
<li>Unauthorized Disclosure</li>
<li>Unauthorized Access</li>
<li>Data Breach</li>
<li>Excessive Retention</li>
<li>Inaccurate Financial Records</li>
</ul>
</div>

<div class="detail-section governance">
<h3>Governance Requirements</h3>
<ul>
<li>Data Retention Schedule</li>
<li>Vendor Risk Assessment</li>
<li>Records of Processing Activities (ROPA)</li>
<li>Written Information Security Program (WISP)</li>
</ul>
</div>

<div class="detail-section controls">
<h3>Cybersecurity Controls</h3>
<ul>
<li>Encryption</li>
<li>Access Control</li>
<li>Audit Logging</li>
<li>Security Monitoring</li>
</ul>
</div>

</div>
</div>


<!-- PHASE 5 -->

<div class="phase-card">

<div class="phase-header">
<span class="phase-number">Phase 5</span>
<h2>Sanctions Screening</h2>
</div>

<div class="phase-body">

<p class="phase-purpose">
<strong>Purpose:</strong> Identifying prohibited, restricted, or high-risk relationships.
</p>

<div class="detail-section data">
<h3>Data Categories</h3>
<ul>
<li>Sanctions &amp; Watchlist Information</li>
<li>Criminal &amp; Background Information</li>
</ul>
</div>

<div class="detail-section laws">
<h3>Applicable Laws</h3>
<ul>
<li>OFAC Sanctions Programs</li>
<li>Bank Secrecy Act (BSA)</li>
<li>Anti-Money Laundering (AML) Requirements</li>
<li>GDPR Article 5</li>
<li>GDPR Article 32</li>
</ul>
</div>

<div class="detail-section risks">
<h3>Privacy &amp; Security Risks</h3>
<ul>
<li>Unauthorized Disclosure</li>
<li>Unauthorized Access</li>
<li>Inaccurate Screening Results</li>
<li>Cross-Border Data Transfers</li>
<li>Excessive Retention</li>
</ul>
</div>

<div class="detail-section governance">
<h3>Governance Requirements</h3>
<ul>
<li>Continuous Monitoring Program</li>
<li>Escalation Procedure</li>
<li>Vendor Risk Assessment</li>
<li>Data Retention Schedule</li>
</ul>
</div>

<div class="detail-section controls">
<h3>Cybersecurity Controls</h3>
<ul>
<li>Encryption</li>
<li>Access Control</li>
<li>Audit Logging</li>
<li>Security Monitoring</li>
<li>Third-Party Risk Management</li>
</ul>
</div>

</div>
</div>


<!-- PHASE 6 -->

<div class="phase-card">

<div class="phase-header">
<span class="phase-number">Phase 6</span>
<h2>Decision, Documentation &amp; Monitoring</h2>
</div>

<div class="phase-body">

<p class="phase-purpose">
<strong>Purpose:</strong> Making a risk-based decision, retaining supporting evidence, and maintaining continuous monitoring of third-party risk.
</p>

<div class="detail-section data">
<h3>Data Categories</h3>
<ul>
<li>All collected due diligence information</li>
</ul>
</div>

<div class="detail-section laws">
<h3>Applicable Laws</h3>
<ul>
<li>GDPR Article 5</li>
<li>GDPR Article 30</li>
<li>GDPR Article 32</li>
<li>Massachusetts General Laws Chapter 93H</li>
<li>201 CMR 17.00</li>
</ul>
</div>

<div class="detail-section risks">
<h3>Privacy &amp; Security Risks</h3>
<ul>
<li>Excessive Retention</li>
<li>Failure to Dispose of Data Securely</li>
<li>Unauthorized Access</li>
<li>Unauthorized Disclosure</li>
<li>Incomplete Audit Trails</li>
</ul>
</div>

<div class="detail-section governance">
<h3>Governance Requirements</h3>
<ul>
<li>Written Information Security Program (WISP)</li>
<li>Records of Processing Activities (ROPA)</li>
<li>Data Retention Schedule</li>
<li>Data Disposal Procedure</li>
<li>Incident Response Plan</li>
<li>Continuous Monitoring Program</li>
</ul>
</div>

<div class="detail-section controls">
<h3>Cybersecurity Controls</h3>
<ul>
<li>Audit Logging</li>
<li>Security Monitoring</li>
<li>Secure Data Disposal</li>
<li>Access Control</li>
<li>Encryption</li>
<li>Data Loss Prevention (DLP)</li>
</ul>
</div>

</div>
</div>

</div>

</div>
