---
description: Un rapporto con tendenze che mostra il numero di volte in cui le pagine del sito Web sono state visualizzate per il periodo di tempo selezionato (ora, giorno, settimana, mese, trimestre o anno). Questo rapporto consente di tenere traccia delle visualizzazioni di pagina per ogni pagina del sito, nonché di un insieme di visualizzazioni di pagina per l’intero sito.
title: Visualizzazioni pagina
topic: Reports
uuid: c78260c6-9ad4-4b85-84fd-763627392e44
translation-type: tm+mt
source-git-commit: 707b61d853a8ec68b3f77a35a1aa5f0c7dd8a1fd

---


# Visualizzazioni pagina

Un rapporto con tendenze che mostra il numero di volte in cui le pagine del sito Web sono state visualizzate per il periodo di tempo selezionato (ora, giorno, settimana, mese, trimestre o anno). Questo rapporto consente di tenere traccia delle visualizzazioni di pagina per ogni pagina del sito, nonché di un insieme di visualizzazioni di pagina per l’intero sito.

La visualizzazione [](/help/components/c-variables/c-metrics/metrics-page-view.md) pagina è una richiesta per un documento a pagina intera anziché per un elemento di una pagina, ad esempio un’immagine o un video. Ad esempio, se un singolo visitatore visualizza 15 pagine durante una visita, vengono conteggiate 15 visualizzazioni di pagina. Se un visitatore visualizza la stessa pagina tre volte durante una visita, vengono conteggiate tre visualizzazioni di pagina.

## Proprietà report

* Questo rapporto fa riferimento al numero di volte in cui il [`t()`](/help/implement/vars/functions/t-method.md) metodo viene chiamato sul sito.
* Le chiamate di tracciamento dei collegamenti che utilizzano il [`tl()`](/help/implement/vars/functions/tl-method.md) metodo non vengono conteggiate in questo rapporto.
* Poiché le richieste di immagini vengono inviate quando l&#39;utente aggiorna la pagina o fa clic sul pulsante Indietro, il rapporto include anche queste azioni.
* Le suddivisioni orari si basano sul fuso orario della suite di rapporti.
* Questo rapporto non contiene elementi di riga. Di conseguenza, il rapporto può essere visualizzato solo nel formato con tendenze.
* È possibile applicare la granularità di ora, giorno, settimana, mese, trimestre e anno. Tale granularità è disponibile a seconda dell&#39;intervallo di date del rapporto.

## Informazioni specifiche per il prodotto

<table id="table_61F964F47D1D43508B271999F495F7F9"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Reports &amp; Analytics </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Contenuto</span> del sito &gt; Visualizzazioni di <span class="uicontrol"> pagina</span> </p> <p>Questo rapporto può usare segmenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Analisi ad hoc </p> </td> 
   <td colname="col2"> 
    <ul id="ul_DB66B8F9F6BF473A83EC7668F59776D0"> 
     <li id="li_D1CB486058F040859560D5BFDF3972EE"> Suddivide ogni elemento del rapporto in base a tutti gli altri rapporti e variabili, consentendo di visualizzare le suddivisioni in base a qualsiasi granularità. </li> 
     <li id="li_BAADA9ADDD6F47B08D129FD30CD8EF2E">Puoi utilizzare tutte le metriche di conversione e traffico in questo rapporto, nonché diverse allocazioni per tutte le metriche di conversione. </li> 
     <li id="li_3696CA6E0BD54305B3609CCC80F851BA">Questo rapporto può utilizzare più segmenti altamente avanzati. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

