---
layout: default
title: Accueil
---

# Chapitre étudiant montréalais de la SCRO

---

Le chapitre étudiant montréalais de la SCRO (Société canadienne de recherche opérationnelle) rassemble les étudiantes et étudiants de cycles supérieurs en recherche opérationnelle et en sciences de la décision. Notre mission est de créer une communauté dynamique favorisant l’échange de connaissances, la collaboration interuniversitaire et le développement professionnel.

À travers des conférences, ateliers et événements de réseautage, nous contribuons à la diffusion des travaux de recherche, à la formation en recherche opérationnelle et au rapprochement entre milieux universitaire, industriel et gouvernemental. Nous participons également à la mission de la SCRO en renforçant les liens entre les sections locales, en encourageant la collaboration internationale, et en promouvant la recherche opérationnelle comme discipline essentielle à la prise de décision éclairée et durable.


<div class="cta-row">
  <a class="btn" href="https://www.linkedin.com/company/cors-montreal-student-chapter">Suivez-nous sur LinkedIn</a>
</div>

---

## Série mensuelle

Nous proposons une programmation mensuelle (ateliers, conférences, panels, réseautage) conçue pour être accessible et utile tout au long de l’année universitaire.

<div class="cta-row">
  <a class="btn" href="{{ site.baseurl }}/evenements.html">Voir la programmation complète</a>
</div>

{% assign upcoming = site.events | sort: "date" | where_exp: "e", "e.date >= site.time" %}
{% assign next = upcoming.first %}

{% if next %}
### Prochain événement

**{{ next.title }}**  
{% assign months = "janvier,février,mars,avril,mai,juin,juillet,août,septembre,octobre,novembre,décembre" | split: "," %}
{% assign m_index = next.date | date: "%-m" | minus: 1 %}
{% assign dmy = next.date | date: "%-d" | append: " " | append: months[m_index] | append: " " | append: (next.date | date: "%Y") %}
**Date :** {{ dmy }} • **Lieu :** {{ next.location }} • **Langue :** {{ next.language }}

<div class="cta-row">
  <a class="btn primary" href="{{ next.rsvp }}">S’inscrire</a>
  <a class="btn" href="{{ next.url | relative_url }}">Détails</a>
</div>
{% endif %}

---

## Nous contacter

Pour toute question, proposition d’atelier ou idée d’événement, écrivez-nous :

<div class="cta-row">
  <a class="btn primary" href="https://forms.gle/HKsmGnPezVEidjKTA">Formulaire</a>
  <a class="btn" href="https://www.linkedin.com/company/cors-montreal-student-chapter">LinkedIn</a>
  <a class="btn" href="mailto:juan-sebastian.riveros-perez@hec.ca">Courriel</a>
</div>