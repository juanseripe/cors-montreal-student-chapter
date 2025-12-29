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

Nous proposons une programmation mensuelle (ateliers, conférences, panels, réseautage) conçue pour être accessible et utile tout au long de l’année universitaire.

<div class="cta-row">
  <a class="btn" href="{{ site.baseurl }}/evenements.html">Voir la programmation complète</a>
</div>

{% assign upcoming = site.events | sort: "date" | where_exp: "e", "e.date >= site.time" %}
{% assign next = upcoming.first %}

{% if next %}
### Prochain événement

**{{ next.title }}**  

**Date :** {{ next.date | date: "%-d %B %Y" }} • **Lieu :** {{ next.location }} • **Langue :** {{ next.language }}

<div class="cta-row">
  <a class="btn primary" href="{{ next.rsvp }}">S’inscrire</a>
  <a class="btn" href="{{ next.url | relative_url }}">Détails</a>
</div>
{% endif %}

---

## Contact us

Pour toute question, proposition d’atelier ou idée d’événement, écrivez-nous :

<div class="cta-row">
  <a class="btn primary" href="https://forms.gle/HKsmGnPezVEidjKTA">Formulaire</a>
  <a class="btn" href="https://www.linkedin.com/company/cors-montreal-student-chapter">LinkedIn</a>
  <a class="btn" href="mailto:juan-sebastian.riveros-perez@hec.ca">Courriel</a>
</div>