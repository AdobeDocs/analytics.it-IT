---
title: Collisioni hash
description: Descrive cos'è una collisione hash e come può manifestarsi.
feature: Validation
exl-id: 693d5c03-4afa-4890-be4f-7dc58a1df553
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 2%

---

# Collisioni hash

In Adobe i valori prop e eVar vengono trattati come stringhe, anche se il valore è un numero. A volte queste stringhe sono lunghe centinaia di caratteri, altre volte sono corte. Per risparmiare spazio, migliorare le prestazioni e ridimensionare tutto in modo uniforme, le stringhe non vengono utilizzate direttamente nell’elaborazione. Invece, per ogni valore viene calcolato un hash a 32 bit o a 64 bit. Tutti i rapporti vengono eseguiti con questi valori con hash, dove ogni hash viene sostituito dal testo originale. Gli hash aumentano drasticamente le prestazioni dei rapporti di Analytics.

Per la maggior parte dei campi, la stringa viene prima convertita in lettere minuscole (riducendo il numero di valori univoci). I valori vengono crittografati mensilmente (la prima volta che vengono visualizzati ogni mese). Da mese a mese c&#39;è una piccola possibilità che due valori di variabile univoci hash allo stesso valore. Questo concetto è noto come *collisione di hash*.

Le collisioni hash possono manifestarsi nel reporting come segue:

* Se stai eseguendo una tendenza di un valore e vedi un picco per un mese, è probabile che un altro valore per quella variabile sia stato dotato di hash allo stesso valore del valore visualizzato.
* Le stesse cose si verificano per i segmenti per un valore specifico.

## Esempio di collisione hash

La probabilità di conflitti hash aumenta con il numero di valori univoci in una dimensione. Ad esempio, uno dei valori che arrivano alla fine del mese potrebbe ottenere lo stesso valore hash di un valore all’inizio del mese. L’esempio seguente può essere utile per spiegare come questo può causare la modifica dei risultati dei segmenti. Supponiamo che eVar62 riceva &quot;valore 100&quot; il 18 febbraio. Analytics manterrà una tabella del seguente aspetto:

<table id="table_6A49D1D5932E485DB2083154897E5074"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Valore stringa eVar62 </th> 
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

Se crei un segmento che cerca le visite in cui eVar62=&quot;value 500&quot;, Analytics determina se &quot;value 500&quot; contiene un hash. Poiché &quot;valore 500&quot; non esiste, Analytics restituisce visite zero. Poi, il 23 febbraio, eVar62 riceve &quot;valore 500&quot;, e l&#39;hash per quello è anche 123. La tabella avrà un aspetto simile al seguente:

<table id="table_5FCF0BCDA5E740CCA266A822D9084C49"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Valore stringa eVar62 </th> 
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

Quando lo stesso segmento viene eseguito di nuovo, cerca l’hash di &quot;valore 500&quot;, trova 123 e il rapporto restituisce tutte le visite che contengono hash 123. Ora, le visite che si sono verificate il 18 febbraio saranno incluse nei risultati.

Questa situazione può creare problemi durante l’utilizzo di Analytics. L’Adobe continua a studiare come ridurre la probabilità che in futuro si verifichino conflitti con hash. Suggerimenti per evitare questa situazione sono trovare il modo di distribuire i valori univoci tra le variabili, rimuovere i valori non necessari con le regole di elaborazione o altrimenti ridurre il numero di valori per variabile.
