---
description: Descrive cosa è una collisione hash e come può manifestarsi.
keywords: Analytics Implementation;hash;collision;prop;evar;hash
solution: Analytics
title: Collisioni hash
topic: Developer and implementation
uuid: 7dfd6e64-4a62-4087-bc28-fb867ec2b1b6
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Collisioni hash

Descrive cosa è una collisione hash e come può manifestarsi.

Per impostazione predefinita, Adobe tratta i valori prop ed eVar come stringhe, anche se il valore è un numero. A volte queste stringhe sono lunghe centinaia di caratteri, altre sono corte. Per risparmiare spazio, migliorare le prestazioni e ridurre le dimensioni uniformemente, le stringhe non vengono utilizzate direttamente nelle tabelle di elaborazione. Per ciascun valore viene invece calcolato un hash a 32 bit o a 64 bit. Tutti i rapporti vengono eseguiti su tali valori con hash fino alla presentazione dei dati, dove ogni hash viene sostituito dal testo originale. Senza questa compressione, i report potrebbero richiedere alcuni minuti.

Per la maggior parte dei campi, la stringa viene prima convertita in lettere minuscole (riducendo il numero di valori univoci). I valori vengono impostati su base mensile (la prima volta che vengono visualizzati ogni mese). Da mese a mese esiste una piccola possibilità che due valori di variabili univoche siano associati allo stesso valore hash. Questa operazione è nota come *collisione* hash.

Le collisioni hash possono manifestarsi nel reporting come segue:

* Se si tenta di ottenere un valore e si visualizza un picco per un mese, è probabile che altri valori per tale variabile siano stati crittografati con lo stesso valore del valore visualizzato.
* Le stesse cose si verificano per i segmenti per un valore specifico.

<p class="head"> <b>Esempio di collisione hash</b> </p>

La probabilità di collisioni hash aumenta con il numero di valori univoci in una dimensione (eVar). Ad esempio, uno dei valori immessi alla fine del mese potrebbe avere lo stesso valore hash di un valore presente all'inizio del mese. L'esempio seguente spiega in che modo ciò può causare la modifica dei risultati dei segmenti. Supponiamo che eVar62 riceva "valore 100" il 18 febbraio. Analytics manterrà una tabella con il seguente aspetto:

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

Se create un segmento che cerca le visite in cui eVar62="valore 500", Analytics determina se "valore 500" contiene un hash. Poiché "valore 500" non esiste, Analytics restituisce zero visite. Quindi, il 23 febbraio, eVar62 riceve "valore 500", e l'hash per questo è anche 123. La tabella sarà così:

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

Quando lo stesso segmento viene eseguito di nuovo, cerca l'hash "value 500", trova 123 e il rapporto restituisce tutte le visite che contengono hash 123. Ora, le visite che si sono verificate il 18 febbraio saranno incluse nei risultati.

Questa situazione può creare problemi quando si utilizza Analytics. Adobe continua a studiare come ridurre la probabilità che in futuro si verifichino collisioni hash. Suggerimenti per evitare questa situazione sono di trovare il modo di distribuire i valori univoci tra le variabili, rimuovere i valori non necessari con le regole di elaborazione o altrimenti ridurre il numero di valori per variabile.
