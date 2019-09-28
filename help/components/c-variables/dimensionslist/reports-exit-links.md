---
description: Mostra i collegamenti più comuni sui quali gli utenti fanno clic e che portano a posizioni esterne al sito. Questi collegamenti in genere fanno riferimento a siti partner o affiliati. Tuttavia, possono essere ovunque tu abbia implementato un collegamento esterno. Puoi utilizzare questo rapporto per visualizzare i collegamenti di affiliazione più popolari o per aiutare a convalidare il numero di riferimenti forniti dallo stato dei partner.
seo-description: Mostra i collegamenti più comuni sui quali gli utenti fanno clic e che portano a posizioni esterne al sito. Questi collegamenti in genere fanno riferimento a siti partner o affiliati. Tuttavia, possono essere ovunque tu abbia implementato un collegamento esterno. Puoi utilizzare questo rapporto per visualizzare i collegamenti di affiliazione più popolari o per aiutare a convalidare il numero di riferimenti forniti dallo stato dei partner.
seo-title: Esci dai collegamenti
solution: Analytics
title: Esci dai collegamenti
topic: Rapporti
uuid: e1452f04-389d-4aa3-8763-732880284302
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Esci dai collegamenti

Mostra i collegamenti più comuni sui quali gli utenti fanno clic e che portano a posizioni esterne al sito. Questi collegamenti in genere fanno riferimento a siti partner o affiliati. Tuttavia, possono essere ovunque tu abbia implementato un collegamento esterno. Puoi utilizzare questo rapporto per visualizzare i collegamenti di affiliazione più popolari o per aiutare a convalidare il numero di riferimenti forniti dallo stato dei partner.

Affinché la pagina possa essere compilata correttamente, è necessario soddisfare diversi requisiti:

* Se si utilizza il tracciamento manuale dei collegamenti personalizzato, è necessario avviare una *`s.tl()`* richiesta con il parametro centrale impostato su *e*.

* Se si utilizza il tracciamento automatico dei collegamenti personalizzato, tutti i requisiti devono essere soddisfatti:
* 

   * [s.trackExternalLinks](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_trackexlinks.html) deve essere impostato su *true*.

   * Il collegamento su cui l'utente ha fatto clic non deve corrispondere ad alcun valore all'interno della variabile [s.linkInternalFilters](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_linkinfilters.html) .
   * Se [s.linkInternalFilters](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_linkinfilters.html) è implementato, il collegamento esterno deve corrispondere ad almeno uno dei valori impostati in questa variabile.

* Se uno dei requisiti di cui sopra non è soddisfatto, l'hit non popolerà il report.

* 
* Come per tutti gli hit di tracciamento dei collegamenti personalizzati, la variabile [s.pageName](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_pagename.html) viene rimossa dalla richiesta di immagine per evitare l’inflazione della visualizzazione pagina.
* Puoi visualizzare questo rapporto in formati con tendenze e classifica.
* Questo rapporto può utilizzare un filtro di ricerca per individuare specifici elementi di riga.
* Puoi creare [suddivisioni](/help/analyze/reports-analytics/reports-customize/breakdowns.md) con qualsiasi altra variabile tramite Strumenti di amministrazione.
* [Le istanze](../../../components/c-variables/c-metrics/metrics-instance.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF) sono le uniche metriche disponibili per impostazione predefinita in questo rapporto, contando il numero di volte in cui il collegamento di uscita è attivato.
* Per questo rapporto è possibile abilitare i visitatori giornalieri, settimanali, mensili e trimestrali. Tuttavia, solo un rappresentante Adobe può attivarli a un costo aggiuntivo. Abilitando visitatori univoci per qualsiasi variabile di tracciamento dei collegamenti personalizzata si aumenta notevolmente la latenza per la suite di rapporti.

