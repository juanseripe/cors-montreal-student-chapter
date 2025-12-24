---
layout: default
title: Événements
---

# Événements

---

Nous organisons une série mensuelle d’activités : ateliers techniques, conférences/panels et événements de réseautage.

---

## À venir

{% assign upcoming = site.events | sort: "date" %}
{% for e in upcoming %}
  {% if e.date >= site.time %}
    <div class="event-card">
    <div class="event-title"><strong>{{ e.title }}</strong></div>
    {% assign months = "janvier,février,mars,avril,mai,juin,juillet,août,septembre,octobre,novembre,décembre" | split: "," %}
    {% assign m_index = e.date | date: "%-m" | minus: 1 %}
    {% assign dmy = e.date | date: "%-d" | append: " " | append: months[m_index] | append: " " | append: (e.date | date: "%Y") %}
    <div class="event-meta"><strong>Date :</strong> {{ dmy }} • <strong>Lieu :</strong> {{ e.location }} • <strong>Langue :</strong> {{ e.language }}</div>
    <div class="cta-row">
        <a class="btn primary" href="{{ e.rsvp }}">S’inscrire</a>
        <a class="btn" href="{{ e.url | relative_url }}">Détails</a>
    </div>
    </div>
  {% endif %}
{% endfor %}

---

## Archives

### 2025
- **[Nom]** — [date] — [lieu] — [type] — [lien / supports]
- **[Nom]** — [date] — [lieu] — [type] — [lien / supports]

### 2024
- **[Nom]** — [date] — [lieu] — [type] — [lien / supports]
- **[Nom]** — [date] — [lieu] — [type] — [lien / supports]

---

## Proposer une idée

Vous souhaitez proposer un atelier, un·e invité·e, ou un format ? Écrivez-nous :
<div class="cta-row">
  <a class="btn primary" href="https://forms.gle/HKsmGnPezVEidjKTA">Formulaire</a>
  <a class="btn" href="https://www.linkedin.com/company/cors-montreal-student-chapter">LinkedIn</a>
  <a class="btn" href="mailto:juan-sebastian.riveros-perez@hec.ca">Courriel</a>
</div>