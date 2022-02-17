---
title: Browser
description: Nome e versione del browser utilizzato.
feature: Dimensions
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 1%

---

# Browser

La dimensione &quot;Browser&quot; indica il nome e la versione del browser che invia l’hit. Questa dimensione è utile per comprendere i browser più comuni utilizzati dai visitatori. Quando sottoponi a test nuove versioni del sito, puoi eseguire tali test sui browser principali di questa dimensione per massimizzare le attività di controllo della qualità.

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento a una tabella di ricerca interna all’Adobe. Il valore di ricerca si basa sul `User-Agent` Intestazione HTTP nelle richieste di immagini. Se utilizzi una libreria AppMeasurement (ad esempio tramite tag in Adobe Experience Platform), questa dimensione funziona automaticamente.

## Elementi Dimension

Gli elementi di Dimension includono i nomi e le versioni del browser utilizzati. Le diverse versioni dello stesso browser sono elementi dimensionali separati.

Alcuni elementi dimensionali contengono `"(unknown version)"` invece del numero di versione. Questo elemento dimensione fa riferimento a una versione recente del browser che Adobe non ha aggiunto alle proprie tabelle di ricerca. Poiché i browser vengono aggiornati frequentemente, la `"(unknown version)"` per un determinato browser è comune e temporaneo. In genere, l’Adobe aggiorna le tabelle di ricerca durante le release di manutenzione mensili.
