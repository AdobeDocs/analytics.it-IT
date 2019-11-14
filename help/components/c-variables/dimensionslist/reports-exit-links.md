---
description: Mostra i collegamenti più comuni sui quali gli utenti fanno clic e che portano a posizioni esterne al sito. Questi collegamenti in genere fanno riferimento a siti partner o affiliati. Tuttavia, possono essere ovunque tu abbia implementato un collegamento esterno. Puoi utilizzare questo rapporto per visualizzare i collegamenti di affiliazione più popolari o per aiutare a convalidare il numero di riferimenti forniti dallo stato dei partner.
solution: Analytics
title: Esci dai collegamenti
topic: Reports
uuid: e1452f04-389d-4aa3-8763-732880284302
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

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
* [Le istanze](/help/components/c-variables/c-metrics/metrics-instance.md) sono le uniche metriche disponibili per impostazione predefinita in questo rapporto, contando il numero di volte in cui il collegamento di uscita è attivato.
* Per questo rapporto è possibile abilitare i visitatori giornalieri, settimanali, mensili e trimestrali. Tuttavia, solo un rappresentante Adobe può attivarli a un costo aggiuntivo. Abilitando visitatori univoci per qualsiasi variabile di tracciamento dei collegamenti personalizzata si aumenta notevolmente la latenza per la suite di rapporti.

