---
description: Scopri Rilevamento delle anomalie e come viene calcolato.
title: Come viene utilizzato il rilevamento delle anomalie per trovare automaticamente le tendenze
uuid: 02da21b4-3394-471b-97b5-aa1bddf1f445
feature: Report Builder
role: User, Admin
exl-id: 6e3881c8-3e1c-4df8-ba38-e8bc84cfc3d4
source-git-commit: bb908f8dd21f7f11d93eb2e3cc843f107b99950d
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 13%

---

# Rilevamento delle anomalie{#anomaly-detection}

Il rilevamento delle anomalie utilizza la modellazione statistica per trovare automaticamente tendenze impreviste nei dati. Il modello analizza le metriche e determina un limite inferiore, un limite superiore e un intervallo di valori previsto. Quando si verifica un picco o un calo imprevisto, il sistema ti avvisa nel rapporto.

Ecco alcuni esempi di anomalie da esaminare:

* Drastico calo nel valore medio degli ordini
* Picchi negli ordini con fatturato basso
* Picchi o calo nelle registrazioni di prova
* Calo nelle visualizzazioni della pagina di destinazione
* Spezie negli eventi buffer video
* Picchi nei valori più bassi di bitrate video

>[!NOTE]
>
>Il rilevamento delle anomalie è disponibile solo quando si seleziona la granularità Day.

<p class="head"> <b>Metriche rilevamento anomalie</b> </p>

Il rilevamento delle anomalie aggiunge nuovi valori di metrica per ogni metrica selezionata, inclusi:

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
   <td colname="col2"> <p>Livello inferiore dell’intervallo di previsione. I valori al di sotto di questo livello sono considerati anomali. </p> <p>Rappresenta un’affidabilità del 95% che i valori saranno al di sopra di questo livello. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Previsto </td> 
   <td colname="col2"> <p>Il valore previsto in base all’analisi dei dati. Questo valore rappresenta anche il punto centrale tra i limiti superiore e inferiore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Limite superiore </td> 
   <td colname="col2"> <p>Livello superiore dell'intervallo di previsione. I valori superiori a questo livello sono considerati anomali. </p> <p>Rappresenta un’affidabilità del 95% che i valori saranno al di sotto di questo livello. </p> </td> 
  </tr> 
 </tbody> 
</table>

Report Builder applica questi valori alle metriche selezionate. Ad esempio, se selezioni una metrica Visualizzazioni pagina e applichi il rilevamento delle anomalie, viene utilizzata una metrica *`Page Views Lower Bound`*.

**Calcolo Del Rilevamento Delle Anomalie**

Il rilevamento delle anomalie utilizza un periodo di formazione per calcolare, apprendere e riportare i dati dell’intervallo di previsione al giorno. Il periodo di formazione è il periodo storico che identifica ciò che è normale rispetto a ciò che è anomalo e applica ciò che è appreso al periodo di reporting. Nei rapporti di marketing sono disponibili periodi di formazione di 30, 60 e 90. In Report Builder sono disponibili 30 giorni.

Il periodo di formazione non corrisponde necessariamente al periodo di reporting selezionato. Un grafico report visualizza il periodo di intervallo di date specificato nel calendario.

Per calcolare i dati, il totale giornaliero per ciascuna metrica viene confrontato con il periodo di formazione utilizzando ciascuno dei seguenti algoritmi:

* Moltiplicativo di Holt Winters (Uniformità esponenziale tripla)
* Additivo Holt Winters (arrotondamento esponenziale triplo)
* Tendenza dei blocchi corretta (arrotondamento esponenziale doppio)

Ogni algoritmo viene applicato per determinare l’algoritmo con la somma più piccola di errori al quadrato (SSE). Vengono quindi calcolati l&#39;errore percentuale assoluto medio (MAPE) e l&#39;errore standard corrente per assicurarsi che il modello sia statisticamente valido.

Questi algoritmi possono essere estesi per fornire previsioni predittive delle metriche nei periodi futuri.

Poiché il periodo di formazione varia in base all&#39;inizio del periodo di reporting, è possibile che vengano rilevate differenze nei dati riportati per la stessa data come parte di due periodi di tempo diversi.

Ad esempio, se esegui un rapporto per il periodo 1-14 gennaio e successivamente un rapporto per il periodo 7-21 gennaio, i dati di previsione per la stessa metrica potrebbero essere diversi tra il 7 e il 14 gennaio nei due diversi rapporti. Ciò è dovuto alla differenza dei periodi di formazione.

| Intervallo di reporting | Periodo di formazione |
|--- |--- |
| Gennaio 1-14 | 27 novembre - 31 dicembre |
| 7-21 gennaio | 4 dicembre - 6 gennaio |
