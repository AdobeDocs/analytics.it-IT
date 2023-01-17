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

Il[!UICONTROL Browser]La dimensione indica il nome e la versione del browser che invia l’hit. Questa dimensione è utile per comprendere i browser più comuni utilizzati dai visitatori. Quando sottoponi a test nuove versioni del sito, puoi eseguire tali test sui browser principali di questa dimensione per massimizzare le attività di controllo della qualità.

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento a una tabella di ricerca interna all’Adobe. Il valore di ricerca si basa sul `User-Agent` Intestazione HTTP nelle richieste di immagini. Se utilizzi una libreria AppMeasurement (ad esempio tramite tag in Adobe Experience Platform), questa dimensione funziona automaticamente.

## Elementi dimensionali

Gli elementi di Dimension includono i nomi e le versioni del browser utilizzati. Le diverse versioni dello stesso browser sono elementi dimensionali separati.

Alcuni elementi dimensionali contengono `"(unknown version)"` invece del numero di versione. Questo elemento dimensione fa riferimento a una versione recente del browser che Adobe non ha aggiunto alle proprie tabelle di ricerca. Poiché i browser vengono aggiornati frequentemente, la `"(unknown version)"` per un determinato browser è comune e temporaneo. In genere, l’Adobe aggiorna le tabelle di ricerca durante le release di manutenzione mensili.

## Modifiche all&#39;etichettatura e alla definizione

Di seguito è riportato un elenco delle modifiche al modo in cui i browser sono rappresentati nel reporting. Queste modifiche possono influire sul reporting o su qualsiasi logica, ad esempio i segmenti, che dipende da questi valori.

### Rimozione della società dal browser

A partire dalla versione 100 per i browser Chrome, Edge e Firefox, il nome dell’azienda non verrà più visualizzato prima del browser. Questo potrebbe avere un impatto sugli utenti che dispongono di definizioni di segmenti basate sul nome del browser. Ad esempio, un segmento che include una definizione che &quot;browser contiene &quot;Google&quot; non identificherà più i browser Chrome che iniziano con la versione 110.

Esempi:

La versione 109 di Chrome apparirà come &quot;Google Chrome 109&quot;.
La versione 110 di Chrome apparirà come &quot;Chrome 109&quot;.

### Rimozione della distinzione tra mobile e non mobile per Chrome

A partire da Chrome 110, le versioni mobile e non-mobile di Chrome saranno etichettate allo stesso modo. Attualmente, le versioni mobile e non-mobile sono etichettate separatamente. Importante: questo cambia il significato del nome senza &quot;mobile&quot;. &quot;Chrome 109&quot; non è mobile (cioè desktop) &quot;Chrome 110&quot; è mobile e non-mobile. Anche in questo caso, se le definizioni dei segmenti fanno riferimento a &quot;mobile&quot; nel nome del browser, potrebbero non funzionare più come previsto. Puoi utilizzare la segmentazione e le suddivisioni per dispositivi mobili per confrontare il traffico da dispositivi mobili a quello non mobile.

Esempi:

Mobile Chrome 109 apparirà come &quot;Chrome Mobile 109&quot;.
Chrome non mobile 109 verrà visualizzato come &quot;Chrome 109&quot;.

Mobile Chrome 110 verrà visualizzato come &quot;Chrome 110&quot;.
Chrome 110 non mobile verrà visualizzato come &quot;Chrome 110&quot;.
