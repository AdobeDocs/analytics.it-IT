---
description: Il rilevamento delle anomalie utilizza la modellazione statistica per trovare automaticamente le tendenze impreviste nei dati. Il modello analizza le metriche e determina una serie di valori associati, superiore e prevista. Quando si verifica un picco o una goccia imprevisti, il sistema avverte l'utente nel rapporto.
seo-description: Il rilevamento delle anomalie utilizza la modellazione statistica per trovare automaticamente le tendenze impreviste nei dati. Il modello analizza le metriche e determina una serie di valori associati, superiore e prevista. Quando si verifica un picco o una goccia imprevisti, il sistema avverte l'utente nel rapporto.
seo-title: Rilevamento delle anomalie
solution: Analytics
title: Rilevamento delle anomalie
topic: Generatore di report
uuid: 02 da 21 b 4-3394-471 b -97 b 5-aa 1 bddf 1 f 445
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Rilevamento delle anomalie{#anomaly-detection}

Il rilevamento delle anomalie utilizza la modellazione statistica per trovare automaticamente le tendenze impreviste nei dati. Il modello analizza le metriche e determina una serie di valori associati, superiore e prevista. Quando si verifica un picco o una goccia imprevisti, il sistema avverte l'utente nel rapporto.

Ecco alcuni esempi di anomalie da esaminare:

* Drastico calo nel valore medio degli ordini
* Picchi negli ordini con fatturato basso
* Picchi o calo nelle registrazioni di prova
* Calo nelle visualizzazioni della pagina di destinazione
* Spezia negli eventi buffer video
* Picchi nei valori più bassi di bitrate video

>[!NOTE]
>
>Il rilevamento delle anomalie è disponibile solo quando si seleziona la granularità Giorno.

<p class="head"> <b>Metriche di rilevamento anomalie</b> </p>

Il rilevamento delle anomalie aggiunge nuovi valori di metrica per ogni metrica selezionata, incluso:

<table id="table_BF75FC874634498DB6632C12CBD8D533"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Legatura inferiore </td> 
   <td colname="col2"> <p>Livello inferiore dell'intervallo di stima. I valori sotto questo livello sono considerati anomali. </p> <p>Rappresenta una confidenza del 95% che i valori saranno superiori a questo livello. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Atteso </td> 
   <td colname="col2"> <p>Il valore previsto in base all'analisi dei dati. Questo valore è anche il punto intermedio tra i limiti superiore e inferiore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Upper Bind </td> 
   <td colname="col2"> <p>Livello principale dell'intervallo di stima. I valori superiori a questo livello vengono considerati anomali. </p> <p>Rappresenta una confidenza del 95% che i valori saranno inferiori a questo livello. </p> </td> 
  </tr> 
 </tbody> 
</table>

Il generatore di report applica questi valori alle metriche selezionate. For example, if you select a Page Views metric and apply anomaly detection, a *`Page Views Lower Bound`* metric is used.

**Calcolo del rilevamento delle anomalie**

Il rilevamento delle anomalie utilizza un periodo di formazione per calcolare, apprendere e riportare dati di intervallo di stima al giorno. Il periodo di formazione è il periodo storico che identifica il normale rispetto a quello anomalo e applica ciò che viene appreso al periodo di reporting. Nei rapporti di marketing sono disponibili periodi di formazione di 30, 60 e 90. Nel generatore di report sono disponibili 30 giorni.

Il periodo di formazione non corrisponde necessariamente al periodo di reporting selezionato. Un grafico di report mostra il periodo di intervallo di date specificato nel calendario.

Per calcolare i dati, il totale giornaliero di ogni metrica viene confrontato con il periodo di formazione utilizzando ciascuno dei seguenti algoritmi:

* Holt Winters Multiplicativo (arrotondamento esponenziale triple)
* Holt Winters Addit(Arrotondamento esponenziale triple)
* Tendenza Bozza corretto (doppia arrotondamento esponenziale)

Ogni algoritmo viene applicato per determinare l'algoritmo con la somma minima di Errori quadrati (SSE). L'errore Percentuale assoluta percentuale (MAPE) e l'errore standard corrente vengono quindi calcolate per essere certi che il modello sia statisticamente valido.

Questi algoritmi possono essere estesi per fornire previsioni predittive sulle metriche in periodi futuri.

Poiché il periodo di formazione varia in base all'inizio del periodo di reporting, potresti vedere le differenze nei dati segnalati per la stessa data nell'ambito di due periodi di tempo diversi.

Ad esempio, se esegui un rapporto per gennaio 1-14 e quindi esegui un rapporto per gennaio 7-21, potresti vedere diversi dati di stima per la stessa metrica tra il ° gennaio e i due diversi rapporti. Questo è il risultato della differenza nei periodi di formazione.

| Intervallo di rapporti | Periodo di formazione |
|--- |--- |
| Gennaio 1-14 | Novembre 27 - Dicembre 31 |
| Gennaio 7-21 | 4 dicembre - Gennaio 6 |