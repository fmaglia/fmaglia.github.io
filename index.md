---
title: Il blog di Federico Magliani
description: IA blog
author: Federico Magliani
---
<nav class="main-nav">
  <ul>
    <li><a href="/">Home</a></li>
    <li><a href="/about/">About</a></li>
  </ul>
</nav>

### Chi sono

Mi chiamo Federico Magliani e sono appassionato di intelligenza artificiale. 
<br>Dopo aver ricevuto il Ph.D. in visione artificiale nel 2020, ho continuato a lavorare in questo ambito.
<br>Per maggiori info visita il mio [sito web](http://magliani.altervista.org).

### Posts

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a><br> <b>Data:</b> {{post.date | date: "%B %e, %Y"}} - <b>Descrizione:</b> {{ post.description }} <br><b>Introduzione:</b> {{ post.intro }}<br>
    </li>
  {% endfor %}
</ul>
