---
description: Mostra i collegamenti più comuni che le persone fanno clic per portare all'esterno del sito. Questi collegamenti generalmente puntano a siti partner o affiliati. Tuttavia, possono essere qualsiasi posizione in cui è stato implementato un collegamento esterno. Puoi usare questo rapporto per visualizzare i collegamenti filiali più diffusi, o per convalidare il numero di referenti forniti dai tuoi partner.
seo-description: Mostra i collegamenti più comuni che le persone fanno clic per portare all'esterno del sito. Questi collegamenti generalmente puntano a siti partner o affiliati. Tuttavia, possono essere qualsiasi posizione in cui è stato implementato un collegamento esterno. Puoi usare questo rapporto per visualizzare i collegamenti filiali più diffusi, o per convalidare il numero di referenti forniti dai tuoi partner.
seo-title: Uscita dai collegamenti
solution: Analytics
title: Uscita dai collegamenti
topic: Rapporti
uuid: e 1452 f 04-389 d -4 aa 3-8763-732880284302
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Uscita dai collegamenti

Mostra i collegamenti più comuni che le persone fanno clic per portare all'esterno del sito. Questi collegamenti generalmente puntano a siti partner o affiliati. Tuttavia, possono essere qualsiasi posizione in cui è stato implementato un collegamento esterno. Puoi usare questo rapporto per visualizzare i collegamenti filiali più diffusi, o per convalidare il numero di referenti forniti dai tuoi partner.

Per la compilazione corretta di questa pagina sono necessari diversi requisiti:

* If using manual custom link tracking, an *`s.tl()`* request must be fired with the middle parameter set to *e*.

* Se utilizzate il tracciamento automatico dei collegamenti, tutti i requisiti devono essere soddisfatti:
* 

   * [s. trackexternallinks](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_trackexlinks) deve essere impostato *su true*.

   * The link the user clicked on must not match any values within the [s.linkInternalFilters](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_linkinfilters) variable.
   * If [s.linkInternalFilters](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_linkinfilters) is implemented, the external link must match at least one of the values set in this variable.

* Se uno dei requisiti indicati sopra non viene soddisfatto, l'hit non conterrà il rapporto.

* 
* As with all custom link tracking hits, the [s.pageName](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_pagename) variable is stripped from the image request to prevent page-view inflation.
* Puoi visualizzare questo rapporto nei formati con tendenze e classifica.
* Questo rapporto può utilizzare un filtro di ricerca per individuare elementi di righe specifiche.
* You can create [breakdowns](/help/analyze/reports-analytics/reports-customize/breakdowns.md) with any other variable via Admin Tools.
* [Le istanze](../../../components/c-variables/c-metrics/metrics-instance.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF) sono le uniche metriche disponibili per impostazione predefinita all'interno di questo rapporto, contando quante volte il collegamento di uscita è stato attivato.
* I visitatori giornalieri, settimanali, mensili e trimestrali possono essere abilitati per questo rapporto. Tuttavia, solo un rappresentante Adobe può attivarli a un costo aggiuntivo. L'abilitazione di visitatori unici per qualsiasi variabile di tracciamento dei collegamenti personalizzata aumenta notevolmente la latenza per la suite di rapporti.

