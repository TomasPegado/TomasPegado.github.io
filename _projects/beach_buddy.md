---
layout: page
title: BeachBuddy
description: A marketplace and management platform connecting people to beach sports training centers in Rio de Janeiro.
img: assets/img/BB_logo_blue.jpg
importance: 1
category: work
related_publications: false
---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/mock_img_2.jpg" title="BeachBuddy mobile app on the beach" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    BeachBuddy is a two-sided platform for the beach sports scene in Rio de Janeiro.
</div>

Beach sports in Rio move a large informal economy. Beach tennis, futevôlei, and beach volley training centers (<em>centros de treinamento</em>, or CTs) run classes along the coast every day, but almost all of the coordination happens through WhatsApp groups and spreadsheets: schedules, attendance, trial classes, and monthly payments. Athletes looking for a place to train have no reliable way to discover what exists near them, and CT owners spend hours a week on administrative work that does not scale.

BeachBuddy attacks both sides of that problem with a single platform. I co-founded it with two partners and am responsible for the backend and infrastructure.

## For athletes

The consumer side is a discovery and booking product. Athletes onboard through a short preference flow, browse CTs on a map filtered by location, sport, and schedule, and book trial classes or recurring training directly in the app.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Handheld-iPhone-2.jpg" title="BeachBuddy onboarding flow" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Handheld-iPhone-1.jpg" title="BeachBuddy training center profile" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left: Onboarding captures training preferences. 
    Right: a training center profile with schedule, class offerings, and booking.
</div>

Discovery is map-first, since proximity to a specific stretch of beach is the strongest factor in where someone actually trains.

<div class="row justify-content-sm-center">
    <div class="col-sm-5 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/Resultados.jpg" title="BeachBuddy search results" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Map-based search with a results bottom sheet, filtered by location and sport.
</div>

## For training centers

The management side replaces the spreadsheet-and-WhatsApp workflow with class scheduling, student rosters, attendance tracking, plan management, and automated recurring billing. Payments run through an integration with Asaas, a Brazilian payment provider, using webhook-driven reconciliation so subscription state stays consistent without manual intervention.

## Architecture

The mobile app is built in **Flutter**, targeting iOS and Android from one codebase, with TestFlight used for iOS distribution during beta.

The backend is a **Django REST Framework** API.

Running a production system with real users and real money has been a useful counterweight to research work. Constraints that are invisible in a benchmark, such as webhook idempotency, connection pooling against a managed cache, and the cost of a bad migration, become concrete very quickly.

<!--
TODO before publishing:
  - Add launch date and current traction (CTs onboarded, active athletes) if you want them public
  - Add a link to the app stores or landing page once live
  - Consider adding a "Technologies" list or a link to the repo if any part is open source
-->
