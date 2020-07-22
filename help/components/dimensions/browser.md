---
title: Browser
description: Nome e versione del browser utilizzato.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 1%

---


# Browser

La dimensione &quot;Browser&quot; indica il nome e la versione del browser che invia l’hit. Questa dimensione è utile per comprendere i browser più comuni utilizzati dai visitatori. Quando testate le nuove versioni del sito, potete eseguire tali test sui browser principali di questa dimensione per ottimizzare il controllo della qualità.

## Compilare questa dimensione con i dati

Questa dimensione fa riferimento a una tabella di ricerca interna ad Adobe. Il valore di ricerca è basato sull’intestazione `User-Agent` HTTP nelle richieste di immagini. Se utilizzi una libreria AppMeasurement (ad esempio tramite  lancio del Adobe Experience Platform), questa dimensione non è disponibile.

## Elementi dimensione

Gli elementi dimensione includono i nomi e le versioni del browser utilizzati. Diverse versioni dello stesso browser sono elementi dimensionali separati.

Alcuni elementi dimensionali contengono `"(unknown version)"` invece del numero di versione. Questo elemento dimensione fa riferimento a una versione recente del browser che Adobe non ha aggiunto alle proprie tabelle di ricerca. Poiché i browser si aggiornano frequentemente, il browser utilizzato `"(unknown version)"` per un determinato browser è comune e temporaneo. In genere Adobe aggiorna le tabelle di ricerca durante le versioni di manutenzione mensili.
