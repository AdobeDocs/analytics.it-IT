---
description: Descrive la collisione con hash e il modo in cui possono essere manifestati.
keywords: Implementazione di Analytics; hash; collisione; prop; evar; hash
seo-description: Descrive la collisione con hash e il modo in cui possono essere manifestati.
seo-title: Collisioni hash
solution: Analytics
title: Collisioni hash
topic: Sviluppatore e implementazione
uuid: 7 dfd 6 e 64-4 a 62-4087-bc 28-fb 867 ec 2 b 1 b 6
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Collisioni hash

Descrive la collisione con hash e il modo in cui possono essere manifestati.

Per impostazione predefinita, Adobe considera i valori prop e evar come stringhe, anche se il valore è un numero. A volte queste stringhe sono centinaia di caratteri, altre volte che sono brevi. Per risparmiare spazio, migliorare le prestazioni e rendere tutte le dimensioni uniformi, le stringhe non vengono utilizzate direttamente nelle tabelle di elaborazione. Al contrario, per ciascun valore viene calcolato un hash a 32 bit o a 64 bit. Tutti i rapporti vengono eseguiti su tali valori con hash fino alla presentazione dei dati, in cui ogni hash viene sostituito dal testo originale. Senza questa compressione, probabilmente i rapporti potrebbero richiedere minuti da eseguire.

Per la maggior parte dei campi, la stringa viene dapprima convertita in minuscolo (riduzione del numero di valori univoci). I valori vengono hash su base mensile (la prima volta che vengono visti ogni mese). Da mese a mese esiste una piccola possibilità che due valori della variabile univoca vengano hash allo stesso valore hash. This is known as a *hash collision*.

Le collisioni hash possono manifestarsi nel reporting come segue:

* Se state ottenendo un valore e visualizzate un picco per un mese, è probabile che un altro valore per tale variabile sia stato aggiunto con hash allo stesso valore del valore che state guardando.
* Lo stesso accade per i segmenti per un valore specifico.

<p class="head"> <b>Esempio di collisione hash</b> </p>

La probabilità di collisioni hash aumenta con il numero di valori univoci di una dimensione (evar). Ad esempio, uno dei valori che entrano in fine mese potrebbe ottenere lo stesso valore di hash di un valore precedente. L'esempio seguente potrebbe spiegare come questo può causare la modifica dei risultati dei segmenti. Supponiamo che evar 62 riceva "value 100" il 18 febbraio. Analytics manterrà una tabella che sarà simile a quella riportata di seguito:

<table id="table_6A49D1D5932E485DB2083154897E5074"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Valore stringa evar 62 </th> 
   <th colname="col2" class="entry"> Hash </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Valore 99 </p> </td> 
   <td colname="col2"> <p> 111 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> Valore 100</b> </p> </td> 
   <td colname="col2"> <p> <b> 123</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Valore 101 </p> </td> 
   <td colname="col2"> <p> 222 </p> </td> 
  </tr> 
 </tbody> 
</table>

Se crei un segmento che cerca visite dove evar 62 = "value 500", Analytics determina se "value 500" contiene un hash. Poiché "value 500" non esiste, Analytics restituisce visite zero. Quindi, il 23 febbraio, evar 62 riceve "value 500" e l'hash per anche il 123. La tabella avrà l'aspetto seguente:

<table id="table_5FCF0BCDA5E740CCA266A822D9084C49"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Valore stringa evar 62 </th> 
   <th colname="col2" class="entry"> Hash </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Valore 99 </p> </td> 
   <td colname="col2"> <p> 111 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> Valore 100</b> </p> </td> 
   <td colname="col2"> <p> <b> 123</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Valore 101 </p> </td> 
   <td colname="col2"> <p> 222 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> Valore 500</b> </p> </td> 
   <td colname="col2"> <p> <b> 123</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

Quando lo stesso segmento viene rieseguito, cerca l'hash di "value 500", trova 123 e il rapporto restituisce tutte le visite contenenti hash 123. Ora, le visite avvenute il 18 febbraio saranno incluse nei risultati.

Questa situazione può creare problemi quando si utilizza Analytics. Adobe continua ad approfondire la probabilità di ridurre la probabilità di tali collisioni hash in futuro. I suggerimenti per evitare questa situazione sono trovare la possibilità di espandere i valori univoci tra le variabili, rimuovere valori non necessari con le regole di elaborazione o ridurre in altro modo il numero di valori per variabili.
