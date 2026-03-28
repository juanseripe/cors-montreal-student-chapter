---
layout: default
title: Events
---

# {{ page.title }}

---

We organize a monthly series of activities: technical workshops, talks/panels, and networking events.

---

## Upcoming

{% assign upcoming_all = site.events_en | sort: "date" %}
{% assign upcoming = upcoming_all | where_exp: "e", "e.date >= site.time" %}

{% if upcoming == empty %}
No upcoming events at the moment.
{% else %}
<ul class="event-list">
{% for e in upcoming %}
  {% assign start_day = e.date | date: "%-d" %}
  {% assign start_month = e.date | date: "%B" %}
  {% assign start_year = e.date | date: "%Y" %}
  {% if e.end %}
    {% assign end_day = e.end | date: "%-d" %}
    {% assign end_month = e.end | date: "%B" %}
    {% assign end_year = e.end | date: "%Y" %}
    {% if start_month == end_month %}
      {% if start_day == end_day %}
        {% capture dmy %}{{ start_month }} {{ start_day }} {{ start_year }}{% endcapture %}
      {% else %}
        {% capture dmy %}{{ start_month }} {{ start_day }}-{{ end_day }} {{ start_year }}{% endcapture %}
      {% endif %}
    {% else %}
      {% capture dmy %}{{ start_month }} {{ start_day }} - {{ end_month }} {{ end_day }} {{ end_year }}{% endcapture %}
    {% endif %}
  {% else %}
    {% capture dmy %}{{ start_month }} {{ start_day }} {{ start_year }}{% endcapture %}
  {% endif %}

  <li class="event-item">
    <div class="event-item-title"><strong>{{ e.title }}</strong></div>
    <div class="event-item-meta">{{ dmy }} • {{ e.location }}</div>
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

{% assign past_all = site.events_en | sort: "date" | reverse %}
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

  {% assign start_day = e.date | date: "%-d" %}
  {% assign start_month = e.date | date: "%B" %}
  {% assign start_year = e.date | date: "%Y" %}
  {% if e.end %}
    {% assign end_day = e.end | date: "%-d" %}
    {% assign end_month = e.end | date: "%B" %}
    {% assign end_year = e.end | date: "%Y" %}
    {% if start_month == end_month %}
      {% if start_day == end_day %}
        {% capture dmy %}{{ start_month }} {{ start_day }} {{ start_year }}{% endcapture %}
      {% else %}
        {% capture dmy %}{{ start_month }} {{ start_day }}-{{ end_day }} {{ start_year }}{% endcapture %}
      {% endif %}
    {% else %}
      {% capture dmy %}{{ start_month }} {{ start_day }} - {{ end_month }} {{ end_day }} {{ end_year }}{% endcapture %}
    {% endif %}
  {% else %}
    {% capture dmy %}{{ start_month }} {{ start_day }} {{ start_year }}{% endcapture %}
  {% endif %}

  <li class="event-item">
    <div class="event-item-title"><strong>{{ e.title }}</strong></div>
    <div class="event-item-meta">{{ dmy }} • {{ e.location }} •  <a class="event-details-link" href="{{ e.url | relative_url }}">Details</a></div>
  </li>
{% endfor %}
</ul>
{% endif %}

---

## Suggest an Idea

Would you like to propose a workshop, invite a speaker, or suggest a format? Reach out to us:
<div class="cta-row">
  <a class="btn primary" href="https://forms.gle/HKsmGnPezVEidjKTA">Form</a> • 
  <a class="btn" href="https://www.linkedin.com/company/cors-montreal-student-chapter">LinkedIn</a> • 
  <a class="btn" href="mailto:juan-sebastian.riveros-perez@hec.ca">Email</a>
</div>