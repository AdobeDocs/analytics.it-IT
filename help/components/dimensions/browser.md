---
title: Browser
description: Nome e versione del browser utilizzato.
feature: Dimensions
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
source-git-commit: 39f1ac66fb6374c62f790f9a38a52fba3bf9bda1
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 1%

---

# Browser

L&#39;&#39;[!UICONTROL Browser]La dimensione &#39; riporta il nome e la versione del browser che invia l’hit. Questa dimensione è utile per comprendere i browser più comuni utilizzati dai visitatori. Quando esegui il test di nuove versioni del sito, puoi eseguirli sui browser principali in questa dimensione per massimizzare le attività di controllo della qualità.

## Popola questa dimensione con i dati

Questa dimensione fa riferimento a una tabella di ricerca interna a Adobe. Il valore di ricerca si basa sul `User-Agent` Intestazione HTTP nelle richieste di immagini. Se utilizzi una libreria AppMeasurement (ad esempio tramite i tag in Adobe Experience Platform), questa dimensione funziona in modo predefinito.

## Elementi dimensionali

Gli elementi di Dimension includono i nomi e le versioni del browser utilizzati. Versioni diverse dello stesso browser sono elementi dimensionali separati.

Alcuni elementi dimensionali contengono `"(unknown version)"` invece del numero di versione. Questo elemento dimensione fa riferimento a una versione recente del browser che Adobe non ha aggiunto alle proprie tabelle di ricerca. Poiché i browser si aggiornano frequentemente, il `"(unknown version)"` per un determinato browser è comune e temporaneo. Adobe in genere aggiorna le tabelle di ricerca durante le versioni di manutenzione mensili.

## Modifiche dell&#39;etichettatura e della definizione

Di seguito è riportato un elenco di modifiche alla modalità di rappresentazione dei browser nei rapporti. Queste modifiche possono influire sul reporting o su qualsiasi logica, ad esempio i segmenti, che dipende da questi valori.

### Rimozione della società dal browser

A partire dalla versione 100 per i browser Chrome, Edge e Firefox, il nome della società non verrà più visualizzato prima del browser. Questo potrebbe interessare gli utenti se dispongono di definizioni di segmenti basate sul nome del browser. Ad esempio, un segmento con una definizione che &quot;il browser contiene &quot;Google&quot; non identificherà più i browser Chrome a partire dalla versione 110.

Esempi:

La versione 109 di Chrome verrà visualizzata come &quot;Google Chrome 109&quot;.
La versione 110 di Chrome verrà visualizzata come &quot;Chrome 109&quot;.

### Eliminazione della distinzione tra dispositivi mobili e non mobili per Chrome

A partire da Chrome 110, le versioni mobile e non mobile di Chrome saranno etichettate allo stesso modo. Attualmente, le versioni per dispositivi mobili e non mobili sono etichettate separatamente. È importante sottolineare che questo cambia il significato del nome senza &quot;mobile&quot;. &quot;Chrome 109&quot; non è un dispositivo mobile (ovvero desktop) &quot;Chrome 110&quot; è un dispositivo mobile e non mobile. Anche in questo caso, se nel nome del browser sono presenti definizioni di segmenti che fanno riferimento a &quot;mobile&quot;, queste potrebbero non funzionare più come previsto. Puoi utilizzare la segmentazione mobile e i raggruppamenti per confrontare il traffico mobile con quello non mobile.

Esempi:

Mobile Chrome 109 apparirà come &quot;Chrome Mobile 109&quot;.
Chrome 109 non mobile verrà visualizzato come &quot;Chrome 109&quot;.

Mobile Chrome 110 verrà visualizzato come &quot;Chrome 110&quot;.
Chrome 110 non mobile verrà visualizzato come &quot;Chrome 110&quot;.
