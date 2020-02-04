---
title: Collisioni hash
description: Descrive cosa è una collisione hash e come può manifestarsi.
translation-type: tm+mt
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# Collisioni hash

Adobe tratta i valori prop ed eVar come stringhe, anche se il valore è un numero. A volte queste stringhe sono lunghe centinaia di caratteri, altre sono corte. Per risparmiare spazio, migliorare le prestazioni e ridimensionare tutto in modo uniforme, le stringhe non vengono utilizzate direttamente nell&#39;elaborazione. Per ciascun valore viene invece calcolato un hash a 32 bit o a 64 bit. Tutti i report vengono eseguiti con questi valori con hash, dove ogni hash viene sostituito dal testo originale. Gli hash aumentano drasticamente le prestazioni dei report di Analytics.

Per la maggior parte dei campi, la stringa viene convertita in lettere maiuscole e minuscole (riducendo il numero di valori univoci). I valori vengono impostati su base mensile (la prima volta che vengono visualizzati ogni mese). Da mese a mese esiste una piccola possibilità che due valori di variabile univoci hash allo stesso valore. Questo concetto è noto come *collisione* hash.

Le collisioni hash possono manifestarsi nel reporting come segue:

* Se si tenta di ottenere un valore e si visualizza un picco per un mese, è probabile che altri valori per tale variabile siano stati crittografati con lo stesso valore del valore visualizzato.
* Le stesse cose si verificano per i segmenti per un valore specifico.

## Esempio di collisione hash

La probabilità di collisioni hash aumenta con il numero di valori univoci in una dimensione. Ad esempio, uno dei valori immessi alla fine del mese potrebbe avere lo stesso valore hash di un valore presente all&#39;inizio del mese. L&#39;esempio seguente spiega in che modo ciò può causare la modifica dei risultati dei segmenti. Supponiamo che eVar62 riceva &quot;valore 100&quot; il 18 febbraio. Analytics manterrà una tabella con il seguente aspetto:

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

Se create un segmento che cerca le visite in cui eVar62=&quot;valore 500&quot;, Analytics determina se &quot;valore 500&quot; contiene un hash. Poiché &quot;valore 500&quot; non esiste, Analytics restituisce zero visite. Quindi, il 23 febbraio, eVar62 riceve &quot;valore 500&quot;, e l&#39;hash per questo è anche 123. La tabella sarà così:

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

Quando lo stesso segmento viene eseguito di nuovo, cerca l&#39;hash &quot;value 500&quot;, trova 123 e il rapporto restituisce tutte le visite che contengono hash 123. Ora, le visite che si sono verificate il 18 febbraio saranno incluse nei risultati.

Questa situazione può creare problemi quando si utilizza Analytics. Adobe continua a studiare come ridurre la probabilità che in futuro si verifichino collisioni hash. Suggerimenti per evitare questa situazione sono di trovare il modo di distribuire i valori univoci tra le variabili, rimuovere i valori non necessari con le regole di elaborazione o altrimenti ridurre il numero di valori per variabile.
