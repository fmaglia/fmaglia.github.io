---
layout: post
title: Esempio di regressione (seconda parte)
tags: apprendimento-automatico IA intelligenza-artificiale
description: Come le reti neurali abbiano migliorato la vita dei data scientist
intro: Come le reti neurali abbiano migliorato la vita dei data scientist
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
Nell’ultimo articolo avevo introdotto un caso di studio sulla regressione. 
Avevo ottenuto risultati discreti utilizzando SVR. 
Ora voglio proporvi un metodo che riesce ad ottenere risultati nettamente migliori.

### Di cosa sto parlando?

Le reti neurali, di tipo MLP (Multi Layer Perceptron).
Per trattare il problema in esame ho quindi usato una rete neurale MLP adatta per la regressione.
<br>
Prima di vedere i risultati ottenuti voglio fare una breve introduzione tecnica sull’uso e sul funzionamento di questo metodo.

### Funzionamento

La tipologia di rete MLP è una sottoclasse delle reti neurali artificiali.
Una rete neurale artificiale cerca di imitare il funzionamento del cervello umano.
È composta da neuroni (come rappresentato in figura 1), il cui numero varia ad ogni livello della rete. 
I neuroni sono inizialmente inizializzati con valori randomici, poi nel corso dell’allenamento del modello variano per adattarsi ai dati dei training.
<br>
In figura 1, la rete rappresentata ha 3 neuroni in input, 4 nel secondo livello (nascosto) e 2 in output.

<figure>
<img src='http://fmaglia.github.io/assets/images/nn.png' style="width:45%">
  <figcaption>Figura 1 - esempio di rete neurale. 
Immagine sotto licenza CC BY-SA 3.0. <a href='https://commons.wikimedia.org/wiki/File:Artificial_neural_network.svg' target='_blank'>URL</a>. </figcaption>
</figure>

Nello specifico, la rete neurale cerca di ridurre l’errore fra *risultato ottenuto* e *valore atteso* (ground truth), modificando i pesi dei vari neuroni.

### Come funziona? 

Tramite il calcolo e l’uso di una _funzione di loss_.
Nel caso di studio analizzato, le loss valutate saranno due: MSE loss e MAE loss.
Ho utilizzato queste due loss perché sto trattando un problema di regressione. Nel caso, avessi trattato un problema di classificazione non le avrei neanche prese in considerazione.

### Come progettare la rete (i vari livelli) e il numero di neuroni?

Anche in questo caso la capacità e l’esperienza del data scientist è di vitale importanza.
<br>In questo caso specifico, ho utilizzato una rete neurale con 4 neuroni per l' input (x1, y1, x2, y2) e 2 neuroni per l'output (xc, yc).
Il numero di neuroni nell'hidden layer è pari a 100.
<br>Ho allenato la rete per 500 epoche.

### Teorema di approssimazione universale

Perché utilizzare le reti neurali per risolvere il problema in esame?
<br>Per via del teorema di approssimazione universale.
<br>“Afferma che una rete con un singolo strato nascosto può approssimare qualsiasi funzione continua, ma non da alcuna indicazione su come ottenerla, come istruirla e se un singolo strato sia la scelta più efficiente.”
<br>
Come sempre ho utilizzato la versione delle artificial neural network proposta da <a href='https://scikit-learn.org/stable/modules/generated/sklearn.neural_network.MLPRegressor.html' target='_blank'>sklearn</a>.



<figure>
<img src='http://fmaglia.github.io/assets/images/test_NN.gif' style="width:45%">
  <figcaption>Figura 2 - immagini del test set. Il punto blu rappresenta il centro del quadrato calcolato tramite la formula del punto medio, mentre il punto verde rappresenta il risultato predetto dalla rete neurale. </figcaption>
</figure>



### Risultati

<img src='http://fmaglia.github.io/assets/images/table5.png' style="width:60%">

Visto? Risultati decisamente interessanti! La rete è riuscita ad imparare a predire correttamente nelle varie situazioni il punto centrale del quadrato.
<br>Come mai, utilizzando le reti neurali, MSE è minore di MAE? 
<br>Essendo le discrepanze molto piccole (minori di 1), il quadrato di questo valore sarà ancora più piccolo.


[Homepage](../../../index)
 
<div style='border:1px solid white'>
  <table><tr><td style='width:30%'><img src='http://magliani.altervista.org/images/office_round.png' style='width:35%'> 
    <br><b>Federico Magliani</b>
  <td>Sono appassionato di Intelligenza Artificiale e nel 2020 ho ricevuto il Ph.D. in Visione Artificiale presso l'Università degli Studi di Parma.
  <br>Se vuoi ricevere maggiori informazioni sull'articolo o sui progetti che sto svolgendo visita il mio <a href='http://magliani.altervista.org' target='_blank'>sito web</a>.
    
<a href="https://www.iubenda.com/privacy-policy/15191098" class="iubenda-white iubenda-noiframe iubenda-embed iubenda-noiframe " title="Privacy Policy ">Privacy Policy</a><script type="text/javascript">(function (w,d) {var loader = function () {var s = d.createElement("script"), tag = d.getElementsByTagName("script")[0]; s.src="https://cdn.iubenda.com/iubenda.js"; tag.parentNode.insertBefore(s,tag);}; if(w.addEventListener){w.addEventListener("load", loader, false);}else if(w.attachEvent){w.attachEvent("onload", loader);}else{w.onload = loader;}})(window, document);</script>
