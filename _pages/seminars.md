---
layout: page
permalink: /seminars
title: seminars
description: 
nav: true
nav_rank: 0
years: [2024, 2023, 2022, 2021, 2020]
---

Our group host seminars on a regular monthly basis, either in person or remotely. 
To get the latest anouncements, you can subscribe to the seminar mailing list [cran-simul-seminars@univ-lorraine.fr](mailto:cran-simul-seminars@univ-lorraine.fr) as follows:

- to subscribe, send a blank email to [sympa@univ-lorraine.fr](mailto:sympa@univ-lorraine.fr) with object **SUBSCRIBE cran-simul-seminars**. A admin will review and validate your request. 
- to unsubscribe, send a blank email to [sympa@univ-lorraine.fr](mailto:sympa@univ-lorraine.fr) with object **UNSUBSCRIBE cran-simul-seminars**. A admin will review and validate your request. 

## Upcoming seminars

{% for seminar in site.data.seminarlist %}
{% if seminar.active == 1%}

  <b>{{ seminar.speaker }}</b> ({{seminar.institution}})<br/>
  {{seminar.date}}<br/>
   <em>{{ seminar.title }}</em><br />

<p>
    <button class="btn btn-primary" type="button" data-toggle="collapse" data-target="#collapse-up-{{forloop.index}}" aria-expanded="false" aria-controls="collapse-u-{{forloop.index}}">
    Abstract
  </button>
</p>
<div class="collapse" id="collapse-up-{{forloop.index}}">
  <div class="card card-body">
{{seminar.abstract}}
  </div>
</div>
{% endif %}
{% endfor %}

## Past seminars


{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
{% assign seminars = site.data.seminarlist | where: "year", {{y}} %}
{% for seminar in seminars %}
{% if seminar.active == 0%}


    

  <b>{{ seminar.speaker }}</b> ({{seminar.institution}})<br/>
  {{seminar.date}}<br/>
   <em>{{ seminar.title }}</em><br />

<p>
    <button class="btn btn-primary" type="button" data-toggle="collapse" data-target="#collapse-past-{{forloop.index}}" aria-expanded="false" aria-controls="collapse-past-{{forloop.index}}">
    Abstract
  </button> {% if seminar.pdf%} <button type="button" class="btn btn-light" onclick="window.location='/assets/seminars/{{seminar.pdf}}';">slides</button> {% endif %}
</p>    
<div class="collapse" id="collapse-past-{{forloop.index}}">
  <div class="card card-body">
{{seminar.abstract}}
  </div>
</div>

{% endif %}
{% endfor %}
{% endfor %}
