---
layout: post
title: Caso di studio su Iris dataset
tags: apprendimento-automatico IA intelligenza-artificiale
description: Un esempio pratico di come le macchine risolvono problemi di classificazioni
intro: Caso di studio, in cui verrà trattato un problema reale di classificazione
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

Ho introdotto nei precedenti post le nozioni necessarie per valutare un primo caso di studio.
Nello specifico analizzerò il problema di classificazione dei fiori fra Iris Setosa, Virginica e Versicolor. Come già accennato, il dataset è composto da 150 istanze. Per ognuna di esse vengono fornite due features utili per la classificazione: la lunghezza e la larghezza del sepalo.

### Suddivisione del dataset

Ho suddiviso il dataset in train e test: l’80% delle istanze le ho inserite nel training set e il rimanente 20% le ho inserite nel test set.
Ho deciso di utilizzare, per trattare il problema di classificazione, l’algoritmo presentato nel post precedente ovvero SVM.

### Risultati

L’<b>accuratezza di classificazione</b> ottenuta è stata pari a 83.33%. Questa metrica misura la percentuale di corrette classificazioni svolte dall’algoritmo utilizzato. Nel caso in esame significa che su 30 immagini presenti nel test set 25 sono classificate correttamente, mentre 5 sono errate. Per incrementare questo valore possono essere necessari:
* maggiori elementi nel training set;
* l’utilizzo di un set diverso di features;
* l’adozione di una strategia più efficace per la risoluzione del problema.

<br>
La <b>matrice di confusione</b> mostra in forma tabellare la suddivisione delle classificazioni per classe. 
Aiuta quindi il data scientist a capire in quali classi l’algoritmo commette errori di classificazione.
La matrice di confusione risultante è stata la seguente:


<br>
Da questa tabella si evince che per la classe Iris Setosa il metodo usato non commette nessun errore di classificazione. Per quanto riguarda la classe Iris Virginica vengono commessi 4 errori perché 4 istanze della classe Iris Virginica vengono classificate come Iris Versicolor. Infine, per l’ultima classe viene commesso un solo errore di classificazione. Da ciò si può quindi evincere che la classe che presenta maggiori difficoltà ad essere correttamente individuata è Iris Virginica.
<br>
Un’interessante analisi è quella che si può fare su come le istanze del dataset siano suddivise in training e test set. La regola aurea è che il numero di istanze di ogni classe dovrebbe essere lo stesso. Serve per evitare problemi in fase di addestramento che si ripercuotono poi in fase di classificazione. Se il metodo di classificazione vede più esempi in fase di addestramento, ci saranno poi maggiori possibilità che classifichi gli elementi del test con l’etichetta della classe più popolosa del training set. In questo caso le istanze sono state suddivise in questa maniera:

TABELLA

<br>
Dalla tabella si evince che relativamente alla classe con meno istanze in fase di training si commettono poi più errori in fase di test.

### Come migliorare le performance?

Avevo utilizzato solo le prime 2 features a disposizione. Ritorna quindi il discorso, fatto qualche post fa, sulla scelta delle features da utilizzare. In questo caso basta utilizzare tutte le features a disposizione, ma non sempre sarà così facile. Un buon data scientist sa valutare quali features utilizzare!
Usando, invece, tutte e 4 le features ottengo risultati nettamente migliori: accuratezza di classificazione pari a 93.33%

ULTIMA TABELLA

Solo due errori nella classificazione dell’Iris Virginica.

[Homepage](../../../index)
 
<div style='border:1px solid white'>
  <table><tr><td style='width:30%'><img src='http://magliani.altervista.org/images/office_round.png' style='width:35%'> 
    <br><b>Federico Magliani</b>
  <td>Sono appassionato di Intelligenza Artificiale e nel 2020 ho ricevuto il Ph.D. in Visione Artificiale presso l'Università degli Studi di Parma.
  <br>Se vuoi ricevere maggiori informazioni sull'articolo o sui progetti che sto svolgendo visita il mio <a href='http://magliani.altervista.org' target='_blank'>sito web</a>.
    
<a href="https://www.iubenda.com/privacy-policy/15191098" class="iubenda-white iubenda-noiframe iubenda-embed iubenda-noiframe " title="Privacy Policy ">Privacy Policy</a><script type="text/javascript">(function (w,d) {var loader = function () {var s = d.createElement("script"), tag = d.getElementsByTagName("script")[0]; s.src="https://cdn.iubenda.com/iubenda.js"; tag.parentNode.insertBefore(s,tag);}; if(w.addEventListener){w.addEventListener("load", loader, false);}else if(w.attachEvent){w.attachEvent("onload", loader);}else{w.onload = loader;}})(window, document);</script>
