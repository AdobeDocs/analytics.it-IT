---
description: Scopri Rilevamento delle anomalie e come viene calcolato.
title: Come viene utilizzato il rilevamento delle anomalie per trovare automaticamente le tendenze
uuid: 02da21b4-3394-471b-97b5-aa1bddf1f445
feature: Report Builder
role: User, Admin
exl-id: 6e3881c8-3e1c-4df8-ba38-e8bc84cfc3d4
TQID: https://experienceleague.adobe.com/P2dvU8YgWcjCZ6h4oTxK-2-z1X3-wl-oMp70UIJGeXo
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: ac8a38fa-dec3-4581-8f64-178fde9f64e8id: c67272a6-888e-425e-9e97-a87304637eedid: e93b8c4c-c5f7-45f8-9abe-9b710f53f502id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 511
ht-degree: 6%

---

# Rilevamento delle anomalie{#anomaly-detection}

{{legacy-arb}}

Il rilevamento delle anomalie utilizza la modellazione statistica per trovare automaticamente tendenze impreviste nei dati. Il modello analizza le metriche e determina un limite inferiore, un limite superiore e un intervallo di valori previsto. Quando si verifica un picco o un calo imprevisto, il sistema ti avvisa nel rapporto.

Di seguito sono riportati alcuni esempi di anomalie che è possibile analizzare:

* Cali drastici nel valore medio dell’ordine
* Picchi negli ordini con ricavi bassi
* Picchi o cadute nelle registrazioni di prova
* Cadute nelle visualizzazioni della pagina di destinazione
* Spezie negli eventi buffer video
* Picchi di bit rate video ridotti

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
