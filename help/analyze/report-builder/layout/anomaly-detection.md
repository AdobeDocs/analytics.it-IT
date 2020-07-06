---
description: Il rilevamento delle anomalie utilizza la modellazione statistica per individuare automaticamente tendenze impreviste nei dati. Il modello analizza le metriche e determina un limite inferiore, un limite superiore e un intervallo di valori previsto. Quando si verifica un picco o un rilascio imprevisto, il sistema ti avvisa nel report.
title: Rilevamento delle anomalie
topic: Report builder
uuid: 02da21b4-3394-471b-97b5-aa1bddf1f445
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 7%

---


# Detección de anomalías{#anomaly-detection}

Il rilevamento delle anomalie utilizza la modellazione statistica per individuare automaticamente tendenze impreviste nei dati. Il modello analizza le metriche e determina un limite inferiore, un limite superiore e un intervallo di valori previsto. Quando si verifica un picco o un rilascio imprevisto, il sistema ti avvisa nel report.

Ecco alcuni esempi di anomalie da esaminare:

* Drastico calo nel valore medio degli ordini
* Picchi negli ordini con fatturato basso
* Picchi o calo nelle registrazioni di prova
* Calo nelle visualizzazioni della pagina di destinazione
* Spezie negli eventi del buffer video
* Picchi nei valori più bassi di bitrate video

>[!NOTE]
>
>Il rilevamento delle anomalie è disponibile solo quando si seleziona la granularità Giorno.

<p class="head"> <b>Metriche di rilevamento delle anomalie</b> </p>

Il rilevamento delle anomalie aggiunge nuovi valori di metrica per ogni metrica selezionata, tra cui:

<table id="table_BF75FC874634498DB6632C12CBD8D533"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Limite inferiore </td> 
   <td colname="col2"> <p>Livello inferiore dell'intervallo di previsione. I valori al di sotto di questo livello vengono considerati anomali. </p> <p>Rappresenta una confidenza del 95% che i valori saranno superiori a questo livello. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Previsto </td> 
   <td colname="col2"> <p>Il valore previsto basato sull'analisi dei dati. Questo valore è anche il punto centrale tra i limiti superiore e inferiore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Limite superiore </td> 
   <td colname="col2"> <p>Livello superiore dell'intervallo di previsione. I valori superiori a questo livello vengono considerati anomali. </p> <p>Rappresenta una confidenza del 95% che i valori saranno inferiori a questo livello. </p> </td> 
  </tr> 
 </tbody> 
</table>

Generatore di report applica questi valori alle metriche selezionate. Ad esempio, se selezionate una metrica Visualizzazioni di pagina e applicate il rilevamento delle anomalie, viene utilizzata una *`Page Views Lower Bound`* metrica.

**Modalità di calcolo del rilevamento delle anomalie**

Il rilevamento delle anomalie utilizza un periodo di formazione per calcolare, apprendere e riportare i dati dell&#39;intervallo di previsione al giorno. Il periodo di formazione è il periodo storico che identifica ciò che è normale e ciò che è anomalo e applica ciò che viene appreso al periodo di reporting. Nei rapporti di marketing sono disponibili periodi di formazione di 30, 60 e 90. Nel generatore di report sono disponibili 30 giorni.

Il periodo di formazione non è necessariamente lo stesso del periodo di reporting selezionato. Un grafico del rapporto mostra l&#39;intervallo di date specificato nel calendario.

Per calcolare i dati, il totale giornaliero di ciascuna metrica viene confrontato con il periodo di formazione utilizzando ciascuno dei seguenti algoritmi:

* Occhiali Voli Multiplicativi (Triplo Smussamento Esponenziale)
* Additivo per inverni Holt (triplo arrotondamento esponenziale)
* Tendenza fori corretta (doppio arrotondamento esponenziale)

Ogni algoritmo viene applicato per determinare l’algoritmo con la somma minima di errori al quadrato (SSE). L&#39;errore percentuale assoluta media (MAPE) e l&#39;errore standard corrente vengono quindi calcolati per verificare che il modello sia statisticamente valido.

Questi algoritmi possono essere estesi per fornire previsioni predittive delle metriche nei periodi futuri.

Poiché il periodo di formazione varia in base all’inizio del periodo di reporting, è possibile che i dati segnalati per la stessa data vengano visualizzati in modo diverso nell’arco di due periodi di tempo diversi.

Ad esempio, se esegui un rapporto per il 1-14 gennaio e quindi esegui un rapporto per il 7-21 gennaio, potresti visualizzare dati di previsione diversi per la stessa metrica tra il 7 e il 14 gennaio nei due rapporti diversi. Questo è il risultato della differenza nei periodi di formazione.

| Intervallo di rapporti | Periodo di formazione |
|--- |--- |
| 1-14 gennaio | 27 novembre - 31 dicembre |
| 7-21 gennaio | 4 dicembre - 6 gennaio |
