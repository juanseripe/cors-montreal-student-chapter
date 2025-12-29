---
layout: default
title: Events
---

# {{ page.title }}

---

We organize a monthly series of activities: technical workshops, talks/panels, and networking events.

---

## Upcoming

{% assign upcoming_all = site.events | sort: "date" %}
{% assign upcoming = upcoming_all | where_exp: "e", "e.date >= site.time" %}

{% if upcoming == empty %}
No upcoming events at the moment.
{% else %}
<ul class="event-list">
{% for e in upcoming %}

  <li class="event-item">
    <div class="event-item-title"><strong>{{ e.title }}</strong></div>
    <div class="event-item-meta">{{ e.date | date: "%-d %B %Y" }} • {{ e.location }}</div>
    <div class="event-item-links">
      <a class="event-details-link" href="{{ e.url | relative_url }}">Details</a>
      {% if e.rsvp %} • <a class="event-details-link" href="{{ e.rsvp }}">Register</a>{% endif %}
    </div>
  </li>
{% endfor %}
</ul>
{% endif %}

---

## Archive

{% assign past_all = site.events | sort: "date" | reverse %}
{% assign past = past_all | where_exp: "e", "e.date < site.time" %}

{% if past == empty %}
No archived events yet.
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

  <li class="event-item">
    <div class="event-item-title"><strong>{{ e.title }}</strong></div>
    <div class="event-item-meta">{{ e.date | date: "%-d %B %Y" }} • {{ e.location }} •  <a class="event-details-link" href="{{ e.url | relative_url }}">Details</a></div>
  </li>
{% endfor %}
</ul>
{% endif %}

---

## Suggest an Idea

Would you like to propose a workshop, invite a speaker, or suggest a format? Reach out to us:
<div class="cta-row">
  <a class="btn primary" href="https://forms.gle/HKsmGnPezVEidjKTA">Form</a>
  <a class="btn" href="https://www.linkedin.com/company/cors-montreal-student-chapter">LinkedIn</a>
  <a class="btn" href="mailto:juan-sebastian.riveros-perez@hec.ca">Email</a>
</div>