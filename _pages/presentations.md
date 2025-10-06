---
layout: page
permalink: /talks/
title: Presentations
description: A list of invited talks, conference presentations, webinars and workshops/tutorials delivered (page in construction).
nav: true
nav_order: 3
---

<style>
/* Talks & Presentations styling for al-folio */

.talks-list {
  margin-top: 1rem;
}

.talk-entry {
  padding: 1.2rem 0;
  border-bottom: 1px solid var(--global-divider-color, #e0e0e0);
  transition: background-color 0.2s ease;
}

.talk-entry:hover {
  background-color: rgba(0, 0, 0, 0.02);
}

.talk-entry h3 {
  font-size: 1.1rem;
  font-weight: 600;
  margin-bottom: 0.2rem;
  color: var(--global-heading-color, #111);
}

.talk-entry p {
  font-size: 0.95rem;
  color: var(--global-text-color-light, #666);
  margin-bottom: 0.3rem;
}

.talk-entry .talk-meta {
  font-style: italic;
  font-size: 0.9rem;
  color: var(--global-text-color-light, #777);
}

/* Year heading style */
.talk-year {
  margin-top: 2rem;
  font-weight: 700;
  color: var(--global-accent-color, #0056b3);
  border-bottom: 2px solid var(--global-accent-color, #0056b3);
  display: inline-block;
  padding-bottom: 0.2rem;
}
</style>

{% assign talks = site.data.talks | sort: "year" | reverse %}

<div class="talks-list">
  {% assign prev_year = nil %}
  {% for talk in talks %}
    {% if talk.year != prev_year %}
      <h2 class="talk-year">{{ talk.year }}</h2>
    {% endif %}
    <div class="talk-entry">
      <h3>{{ talk.title }}</h3>
      <p><em>{{ talk.type }} – {{ talk.event }}, {{ talk.location }}</em></p>
    </div>
    {% assign prev_year = talk.year %}
  {% endfor %}
</div>
