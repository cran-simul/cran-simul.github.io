---
layout: page
permalink: /publications/
title: publications
description: 
nav: true
nav_order: 1
---
<!-- _pages/publications.md -->
### Full list of publications from HAL

{% for publi in site.data.publist %}

  {{ publi.title }} <br />
  <em>{{ publi.authors }} </em><br /><a href="{{ publi.link.url }}">{{ publi.link.display }}</a>

{% endfor %}
<div class="row">
<iframe width="100%" frameBorder="0" height="500px" src='https://haltools.archives-ouvertes.fr/Public/afficheRequetePubli.php?auteur_exp=Ricardo%2C+Augusto%2C+Borsoi%3C+David%2C+Brie%3B+El-Hadi%2C+Djermoune%3B+Sebastian%2C+Miron%3B+Konstantin%2C+Usevich%3B+Julien%2C+Flamant%3B&annee_publideb=2016&CB_auteur=oui&CB_titre=oui&CB_article=oui&langue=Anglais&tri_exp=annee_publi&tri_exp2=typdoc&tri_exp3=date_publi&ordre_aff=TA&Fen=Aff&css=../css/VisuCondenseSsCadre.css' ></iframe>
</div>
