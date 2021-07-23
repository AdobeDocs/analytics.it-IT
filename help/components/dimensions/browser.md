---
title: Browser
description: Nome e versione del browser utilizzato.
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
source-git-commit: e6f3beadfba340cea07f5fd2694105ad31de9751
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 1%

---

# Browser

La dimensione &quot;Browser&quot; indica il nome e la versione del browser che invia l’hit. Questa dimensione è utile per comprendere i browser più comuni utilizzati dai visitatori. Quando sottoponi a test nuove versioni del sito, puoi eseguire tali test sui browser principali di questa dimensione per massimizzare le attività di controllo della qualità.

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento a una tabella di ricerca interna all’Adobe. Il valore di ricerca si basa sull’intestazione HTTP `User-Agent` nelle richieste di immagini. Se utilizzi una libreria AppMeasurement (ad esempio tramite tag in Adobe Experience Platform), questa dimensione funziona automaticamente.

## Elementi Dimension

Gli elementi di Dimension includono i nomi e le versioni del browser utilizzati. Le diverse versioni dello stesso browser sono elementi dimensionali separati.

Alcuni elementi dimensionali contengono `"(unknown version)"` anziché il numero di versione. Questo elemento dimensione fa riferimento a una versione recente del browser che Adobe non ha aggiunto alle proprie tabelle di ricerca. Poiché i browser si aggiornano frequentemente, la sezione `"(unknown version)"` per un determinato browser è comune e temporanea. In genere, l’Adobe aggiorna le tabelle di ricerca durante le release di manutenzione mensili.
