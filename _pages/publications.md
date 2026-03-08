---
layout: page
permalink: /publications/
title: Publications
description: "* Equal Contribution | † Corresponding Author"
nav: true
nav_order: 1
---
<!-- _pages/publications.md -->
<div class="publications">

<h2 class="topic-title">Cross-modal Retrieval</h2>
{% bibliography -f papers --group_by none --query @*[topic=Cross-modal Retrieval]* %}

<h2 class="topic-title">Omnimodal Large Language Model</h2>
<p class="topic-placeholder"><em>Coming soon...</em></p>

<h2 class="topic-title">Generative Model</h2>
{% bibliography -f papers --group_by none --query @*[topic=Generative Model]* %}

</div>
