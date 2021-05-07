---
layout: post
title: Esempio di regressione
tags: apprendimento-automatico IA intelligenza-artificiale
description: Un esempio pratico di come le macchine risolvono problemi di rgressione
intro: Caso di studio, in cui verrà trattato un problema reale di regressione
author: Federico Magliani
---

<script async src="https://www.googletagmanager.com/gtag/js?id=G-DKE7V23TS7"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-DKE7V23TS7');
</script>

### Ricapitolando
Nei problemi di regressione, l’obiettivo è quello di determinare un valore continuo avendo a
disposizione solo valori continui. È quindi differente dal problema di classificazione, in cui dobbiamo decidere se ogni istanza appartiene alla classe 1, alla classe 2, .. alla
classe N.

### Problema

In questo articolo voglio proporre un semplice problema di regressione.
Dati in input il vertice sinistro alto e il vertice destro basso di un quadrato, voglio calcolare il centro dello stesso. Il mio dataset è composto da 450 istanze di dimensioni 400x400. Utilizzerò 400 istanze per il training del modello e 50 per il test. In ogni istanza del dataset ho variato randomicamente: dimensioni del quadrato, ascissa del primo punto e ordinata
del secondo punto. 
Ho realizzato una gif con le immagini delle istanze del training set per aiutare nella comprensione del problema.

<figure>
<img src='http://fmaglia.github.io/assets/images/train.gif' style="width:60%">
  <figcaption>Figura 1 - training set. </figcaption>
</figure>

### Procedimento adottato

Per risolvere il problema ho adottato l’algoritmo SVR, che è la versione dell’algoritmo di classificazione SVM idoneo a risolvere i problemi di regressione.
Ho utilizzato la versione dell’algoritmo disponibile nella libreria python sklearn.

Ho quindi testato il mio metodo sulle istanze del test set.
Inserisco l’immagine dei risultati ottenuti. 
Il punto verde indica la predizione svolta dal SVR, mentre il punto blu indica il ground truth calcolato tramite la formula del punto medio.

### Nota bene

Il ground truth indica per ogni istanza del dataset le coordinate del punto da trovare.
Senza queste informazioni non sarebbe possibile allenare e successivamente testare il modello di regressione.

Esempio di groun truth:
* TRAIN - Square 0 Point A 199 112 Point B 273 186 Center point 236 149
* TRAIN - Square 1 Point A 71 135 Point B 123 187 Center point 97 161
* TRAIN - Square 2 Point A 108 205 Point B 189 286 Center point 148 246
* TRAIN - Square 3 Point A 127 96 Point B 196 165 Center point 162 130
* TRAIN - Square 4 Point A 60 134 Point B 147 221 Center point 104 178
* TRAIN - Square 5 Point A 77 40 Point B 135 98 Center point 106 69
* ...

Il punto A è sempre quello in alto a sinistra, mentre il punto B è sempre quello che si trova in basso a destra.


<figure>
<img src='http://fmaglia.github.io/assets/images/test.gif' style="width:60%">
  <figcaption>Figura 2 - test set. </figcaption>
</figure>

Per valutare la qualità del modello proposto ho utilizzato due indicatori comuni: <b>Mean Squared Error</b> e <b>Mean Absolute Error</b>.

### Definizioni

* <b>Mean Squared Error</b>: indica la discrepanza quadratica media fra i valori dei dati osservati ed i valori dei dati stimati (da Wikipedia). Tende ad aumentare
significativamente all’aumentare della differenza fra valore calcolato dall’algoritmo e valore del ground truth.
* <b>Mean Absolute Error</b>: indica la media fra i valori dei dati osservati ed i valori dei dati stimati. Tende a crescere meno significativamente rispetto al MSE all’aumentare della differenza fra valore calcolato e valore del ground truth.


### Risultati

<img src='http://fmaglia.github.io/assets/images/table4.png' style="width:60%">

Visto che devo determinare sia l’ascissa che l’ordinata del punto centrale del quadrato avrò quindi un errore distinto per entrambi i campi.
I risultati ottenuti come si può evincere anche visivamente sono discreti, ma non eccellenti.
Considerando che le immagini hanno dimensione 400x400 e il MAE è di circa 23 pixel allora l'errore medio è circa il 6%.
Nel prossimo post vi spiegherò come fare per migliorare questo risultato, raggiungendo errori che tendono allo zero. Non perdetevi il prossimo post!


[Homepage](../../../index)
 
<div style='border:1px solid white'>
  <table><tr><td style='width:30%'><img src='http://magliani.altervista.org/images/office_round.png' style='width:35%'> 
    <br><b>Federico Magliani</b>
  <td>Sono appassionato di Intelligenza Artificiale e nel 2020 ho ricevuto il Ph.D. in Visione Artificiale presso l'Università degli Studi di Parma.
  <br>Se vuoi ricevere maggiori informazioni sull'articolo o sui progetti che sto svolgendo visita il mio <a href='http://magliani.altervista.org' target='_blank'>sito web</a>.
    
<a href="https://www.iubenda.com/privacy-policy/15191098" class="iubenda-white iubenda-noiframe iubenda-embed iubenda-noiframe " title="Privacy Policy ">Privacy Policy</a><script type="text/javascript">(function (w,d) {var loader = function () {var s = d.createElement("script"), tag = d.getElementsByTagName("script")[0]; s.src="https://cdn.iubenda.com/iubenda.js"; tag.parentNode.insertBefore(s,tag);}; if(w.addEventListener){w.addEventListener("load", loader, false);}else if(w.attachEvent){w.attachEvent("onload", loader);}else{w.onload = loader;}})(window, document);</script>
