---
layout: default
title: Home
permalink: /en/
---

# CORS Montreal Student Chapter

---

The CORS Montreal Student Chapter brings together graduate students in operations research and decision sciences. Our mission is to build a vibrant community that fosters knowledge exchange, inter-university collaboration, and professional development.

Through talks, workshops, and networking events, we contribute to the dissemination of research, the promotion of education and training in operations research, and the connection between academia, industry, and government. We also align with CORS’s broader goals by strengthening collaboration among local sections, encouraging international partnerships, and promoting operations research as a key discipline for informed and sustainable decision-making.


<div class="cta-row">
  <a class="btn" href="https://www.linkedin.com/company/cors-montreal-student-chapter">Follow us on LinkedIn</a>
</div>

---

## Monthly series

We offer a monthly program (workshops, talks, panels, and networking events) designed to be accessible and valuable throughout the academic year.

<div class="cta-row">
  <a class="btn" href="{{ site.baseurl }}/en/evenements.html">View the full schedule</a>
</div>

{% assign upcoming = site.events | sort: "date" | where_exp: "e", "e.date >= site.time" %}
{% assign next = upcoming.first %}

{% if next %}
### Upcoming Event

**{{ next.title }}**  

**Date:** {{ next.date | date: "%-d %B %Y" }} • **Location:** {{ next.location }} • **Language:** {{ next.language }}

<div class="cta-row">
  <a class="btn primary" href="{{ next.rsvp }}">Register</a>
  <a class="btn" href="{{ next.url | relative_url }}">Details</a>
</div>
{% endif %}

---

## Contact Us

For any questions, workshop proposals, or event ideas, feel free to reach out:

<div class="cta-row">
  <a class="btn primary" href="https://forms.gle/HKsmGnPezVEidjKTA">Form</a>
  <a class="btn" href="https://www.linkedin.com/company/cors-montreal-student-chapter">LinkedIn</a>
  <a class="btn" href="mailto:juan-sebastian.riveros-perez@hec.ca">Email</a>
</div>