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

<!-- ## Upcoming seminars

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
{% endfor %} -->

<!-- ## Past seminars


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
{% endfor %} -->



## Upcoming seminars

{% assign upcoming_seminars = site.data.seminarlist | where: "active", 1 %}
{% if upcoming_seminars.size > 0 %}
  {% for seminar in upcoming_seminars %}
    <b>{{ seminar.speaker }}</b> ({{seminar.institution}})<br/>
    {{seminar.date}}<br/>
    <em>{{ seminar.title }}</em><br /><br />
  {% endfor %}
{% else %}
  <p>There are no upcoming seminars at the moment. Please check back later.</p>
{% endif %}


## Past seminars

<ul class="nav nav-tabs" id="myTab" role="tablist">
  {%- for y in page.years %}
    <li class="nav-item">
      <a class="nav-link {% if forloop.first %}active{% endif %}" id="tab-{{y}}" data-toggle="tab" href="#year-{{y}}" role="tab" aria-controls="year-{{y}}" aria-selected="{% if forloop.first %}true{% else %}false{% endif %}">{{y}}</a>
    </li>
  {%- endfor %}
</ul>

<div class="tab-content" id="myTabContent">
  {%- for y in page.years %}
    <div class="tab-pane fade {% if forloop.first %}show active{% endif %}" id="year-{{y}}" role="tabpanel" aria-labelledby="tab-{{y}}">
      <!-- <h3>{{y}}</h3> -->
      {% assign seminars = site.data.seminarlist | where: "year", y %}
      {% for seminar in seminars %}
        {% if seminar.active == 0 %}
          <br />
          <b>{{ seminar.speaker }}</b> ({{seminar.institution}})<br/>
          {{seminar.date}}<br/>
          <em>{{ seminar.title }}</em><br />
    <button class="btn btn-primary" type="button" data-toggle="collapse" data-target="#collapse-past-{{forloop.index}}" aria-expanded="false" aria-controls="collapse-past-{{forloop.index}}">
    Abstract
  </button> {% if seminar.pdf%} <button type="button" class="btn btn-light" onclick="window.location='/assets/seminars/{{seminar.pdf}}';">slides</button> {% endif %}
<div class="collapse" id="collapse-past-{{forloop.index}}">
  <div class="card card-body">
{{seminar.abstract}}
  </div>
</div>
<br/>
        {% endif %}
      {% endfor %}
    </div>
  {%- endfor %}
</div>