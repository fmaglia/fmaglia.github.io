---
title: Il blog di Federico Magliani
description: IA blog
author: Federico Magliani
---
<!-- Global site tag (gtag.js) - Google Analytics -->
<head>
<script async src="https://www.googletagmanager.com/gtag/js?id=G-DKE7V23TS7"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-DKE7V23TS7');
</script>
</head>
<!--Mi chiamo Federico Magliani e sono appassionato di intelligenza artificiale. 
<br>Dopo aver ricevuto il Ph.D. in visione artificiale nel 2020, ho continuato a lavorare in questo ambito.
<br>Per maggiori info visita il mio [sito web](http://magliani.altervista.org).-->

### Posts

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a><br> <b>Data:</b> {{post.date | date: "%B %e, %Y"}} <!--- <b>Descrizione:</b> {{ post.description }}--> - <b>Introduzione:</b> {{ post.intro }}<br><br>
    </li>
  {% endfor %}
</ul>
