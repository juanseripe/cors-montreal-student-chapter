---
layout: default
title: Événements
---

# Événements

---
Collections: {{ site.collections | map: "label" | join: ", " }} — events count: {{ site.events | size }}

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
  {% capture dmy %}{{ e.date | date: "%-d" }} {{ months[m_index] }} {{ e.date | date: "%Y" }}{% endcapture %}
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

{% assign past = site.events | sort: "date" | reverse %}

{% assign any_past = false %}
{% for e in past %}
  {% if e.date < site.time %}
    {% assign any_past = true %}
  {% endif %}
{% endfor %}

{% if any_past == false %}
Aucun événement archivé pour le moment.
{% else %}

{% assign current_year = "" %}

{% for e in past %}
  {% if e.date < site.time %}

    {% assign y = e.date | date: "%Y" %}
    {% if y != current_year %}
      {% assign current_year = y %}
### {{ current_year }}
    {% endif %}

    {% assign months = "janvier,février,mars,avril,mai,juin,juillet,août,septembre,octobre,novembre,décembre" | split: "," %}
    {% assign m_index = e.date | date: "%-m" | minus: 1 %}
    {% capture dmy %}{{ e.date | date: "%-d" }} {{ months[m_index] }} {{ e.date | date: "%Y" }}{% endcapture %}

<div class="event-card">
  <div class="event-title"><strong>{{ e.title }}</strong></div>
  <div class="event-meta">
    <strong>Date :</strong> {{ dmy }} • <strong>Lieu :</strong> {{ e.location }} • <strong>Détails :</strong>
    <a class="event-details-link" href="{{ e.url | relative_url }}">Voir</a>
  </div>


</div>

  {% endif %}
{% endfor %}

{% endif %}

---

## Proposer une idée

Vous souhaitez proposer un atelier, un·e invité·e, ou un format ? Écrivez-nous :
<div class="cta-row">
  <a class="btn primary" href="https://forms.gle/HKsmGnPezVEidjKTA">Formulaire</a>
  <a class="btn" href="https://www.linkedin.com/company/cors-montreal-student-chapter">LinkedIn</a>
  <a class="btn" href="mailto:juan-sebastian.riveros-perez@hec.ca">Courriel</a>
</div>