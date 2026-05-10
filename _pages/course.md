---
layout: single
permalink: /course/
title: "Your LLM feature is live. Now make it actually work."
excerpt: "A paid 4-week live cohort for engineers who shipped a GenAI feature and need to make it reliable."
author_profile: false
classes: wide
---

<style>
.course-subhead {
  font-size: 1.2em;
  color: #555;
  margin: 0.5em 0 1.5em;
  line-height: 1.5;
}
.credibility-bar {
  background: #f2f3f3;
  border-left: 4px solid #6f777d;
  padding: 0.8em 1.25em;
  margin: 1.5em 0 2em;
  font-size: 0.92em;
  color: #444;
}
.audience-block {
  margin: 1.5em 0 2.5em;
}
.audience-block p {
  font-size: 0.95em;
  color: #444;
  margin-bottom: 0.4em;
}
.audience-block ul {
  margin: 0.5em 0 0 1em;
  padding: 0;
}
.audience-block ul li {
  font-size: 0.95em;
  color: #444;
  margin-bottom: 0.3em;
}
.week-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1.5em;
  margin: 2em 0 2.5em;
}
@media (max-width: 680px) {
  .week-grid { grid-template-columns: 1fr; }
}
.week-card {
  border: 1px solid #ddd;
  border-radius: 6px;
  padding: 1.5em;
  background: #fafafa;
}
.week-label {
  font-size: 0.72em;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  color: #888;
  margin-bottom: 0.35em;
}
.week-title {
  font-size: 1.1em;
  font-weight: 700;
  color: #1a1a1a;
  margin: 0 0 0.9em;
}
.week-items {
  list-style: none;
  padding: 0;
  margin: 0;
}
.week-items li {
  padding: 0.25em 0;
  color: #555;
  font-size: 0.88em;
  line-height: 1.4;
}
.week-items li::before {
  content: "→ ";
  color: #6f777d;
  font-weight: 700;
}
.section-divider {
  border: none;
  border-top: 1px solid #e8e8e8;
  margin: 2.5em 0;
}
.signup-section {
  background: #f2f3f3;
  border-radius: 8px;
  padding: 2em 2em 1.5em;
  margin-top: 2em;
  text-align: center;
}
.signup-section h2 {
  margin-top: 0;
  font-size: 1.3em;
}
.signup-section p {
  color: #555;
  font-size: 0.92em;
  margin-bottom: 1.25em;
}
</style>

<p class="course-subhead">A paid 4-week live cohort for engineers who shipped a GenAI feature and own making it reliable.</p>

<div class="credibility-bar">
  From the author of the <a href="https://learning.oreilly.com/library/view/retrieval-augmented-generation/9781098165161/" target="_blank">O'Reilly book on Retrieval Augmented Generation</a> and instructor of the O'Reilly live training on LLMs in Production.
</div>

<div class="audience-block">
  <p><strong>This course is for you if:</strong></p>
  <ul>
    <li>You shipped a GenAI feature in the last year and you own keeping it working</li>
    <li>You're seeing inconsistent outputs, silent failures, or user complaints you can't reproduce</li>
    <li>You want a systematic approach — not another list of prompting tips</li>
  </ul>
</div>

<hr class="section-divider">

<h2>What you'll get</h2>

<p>4 weeks of live sessions with Skanda — small group, real back-and-forth, no lecture theater. Each week targets a specific layer of the reliability problem, in the order you'd actually attack it in production. Drawn from his O'Reilly courses on GenAI in Production and AI Context Engineering.</p>

<div class="week-grid">

  <div class="week-card">
    <div class="week-label">Week 1</div>
    <p class="week-title">Diagnose</p>
    <ul class="week-items">
      <li>Why LLM evals are fundamentally different from traditional ML — and what that means for your system</li>
      <li>The 4 context failure modes: poisoning, distraction, confusion, clash</li>
      <li>Building a representative eval set from real production traffic, not synthetic data</li>
      <li>Calibrating an LLM-as-Judge so you can stop evaluating by vibes</li>
    </ul>
  </div>

  <div class="week-card">
    <div class="week-label">Week 2</div>
    <p class="week-title">Context Engineering</p>
    <ul class="week-items">
      <li>Context as a first-class data layer — retrieve the right evidence, structure it, inject it efficiently</li>
      <li>RAG in production: hybrid search, re-ranking, and query rewriting when basic retrieval breaks</li>
      <li>Memory strategies: when to vectorize, summarize, or use an entity store</li>
      <li>Keeping context fresh and relevant without ballooning token costs</li>
    </ul>
  </div>

  <div class="week-card">
    <div class="week-label">Week 3</div>
    <p class="week-title">Agents</p>
    <ul class="week-items">
      <li>When to go agentic — and when it will make your reliability problem worse</li>
      <li>Tool use, routing, and building loops that fail gracefully</li>
      <li>MCP and the emerging standard for connecting agents to data and tools</li>
      <li>Evaluating agents: testing multi-step systems without gold-standard labels</li>
    </ul>
  </div>

  <div class="week-card">
    <div class="week-label">Week 4</div>
    <p class="week-title">Production</p>
    <ul class="week-items">
      <li>Prompt versioning and model management across iterations</li>
      <li>Monitoring for latency, cost, and quality drift — what to instrument and what to ignore</li>
      <li>Context pruning strategies: when to summarize, truncate, or fix the retrieval</li>
      <li>When to fine-tune vs. prompt-engineer vs. swap the model entirely</li>
    </ul>
  </div>

</div>

<hr class="section-divider">

<div class="signup-section">
  <h2>Get access</h2>
  <p>Sign up and I'll send you a link to enroll. No spam. Unsubscribe any time.</p>
</div>

<script async data-uid="56d2720caf" src="https://skanda-vivek.kit.com/56d2720caf/index.js"></script>
