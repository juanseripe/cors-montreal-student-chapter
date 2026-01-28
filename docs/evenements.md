---
layout: default
title: Événements
---

# {{ page.title }}

---

Nous organisons une série mensuelle d’activités : ateliers techniques, conférences/panels et événements de réseautage.

---

## À venir

{% assign upcoming_all = site.events | sort: "date" %}
{% assign upcoming = upcoming_all | where_exp: "e", "e.date >= site.time" %}

{% if upcoming == empty %}
Aucun événement à venir pour le moment.
{% else %}
<ul class="event-list">
{% for e in upcoming %}
  {% assign months = "janvier,février,mars,avril,mai,juin,juillet,août,septembre,octobre,novembre,décembre" | split: "," %}
  {% assign m_index = e.date | date: "%-m" | minus: 1 %}
  {% capture dmy %}{{ e.date | date: "%-d" }} {{ months[m_index] }} {{ e.date | date: "%Y" }}{% endcapture %}

  <li class="event-item">
    <div class="event-item-title"><strong>{{ e.title }}</strong></div>
    <div class="event-item-meta">{{ dmy }} • {{ e.location }}</div>
    <div class="event-item-links">
      <a class="event-details-link" href="{{ e.url | relative_url }}">Détails</a>
      {% if e.rsvp %} • <a class="event-details-link" href="{{ e.rsvp }}">S’inscrire</a>{% endif %}
    </div>
  </li>
{% endfor %}
</ul>
{% endif %}

---

## Archives

{% assign past_all = site.events | sort: "date" | reverse %}
{% assign past = past_all | where_exp: "e", "e.date < site.time" %}

{% if past == empty %}
Aucun événement archivé pour le moment.
{% else %}
{% assign current_year = "" %}

{% for e in past %}
  {% assign y = e.date | date: "%Y" %}
  {% if y != current_year %}
    {% if current_year != "" %}
</ul>
    {% endif %}
    {% assign current_year = y %}

### {{ current_year }}
<ul class="event-list">
  {% endif %}

  {% assign months = "janvier,février,mars,avril,mai,juin,juillet,août,septembre,octobre,novembre,décembre" | split: "," %}
  {% assign m_index = e.date | date: "%-m" | minus: 1 %}
  {% capture dmy %}{{ e.date | date: "%-d" }} {{ months[m_index] }} {{ e.date | date: "%Y" }}{% endcapture %}

  <li class="event-item">
    <div class="event-item-title"><strong>{{ e.title }}</strong></div>
    <div class="event-item-meta">{{ dmy }} • {{ e.location }} •  <a class="event-details-link" href="{{ e.url | relative_url }}">Détails</a></div>
  </li>
{% endfor %}
</ul>
{% endif %}

---

## Proposer une idée

Vous souhaitez proposer un atelier, un·e invité·e, ou un format ? Écrivez-nous :
<div class="cta-row">
  <a class="btn primary" href="https://forms.gle/HKsmGnPezVEidjKTA">Formulaire</a> • 
  <a class="btn" href="https://www.linkedin.com/company/cors-montreal-student-chapter">LinkedIn</a> • 
  <a class="btn" href="mailto:juan-sebastian.riveros-perez@hec.ca">Courriel</a>
</div>