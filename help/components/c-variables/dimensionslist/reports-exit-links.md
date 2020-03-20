---
title: Esci dai collegamenti
description: Segnala i collegamenti più comuni su cui gli utenti fanno clic per uscire dal sito.
translation-type: tm+mt
source-git-commit: be4c3ec95b9e93dda7603c0bdb178c0a54d800a0

---


# Esci dai collegamenti

Mostra i collegamenti più comuni ai quali gli utenti possono fare clic per uscire dal sito. Tali collegamenti fanno generalmente riferimento a siti partner o affiliati; tuttavia, possono essere ovunque si disponga di un collegamento esterno. Puoi utilizzare questo rapporto per visualizzare i collegamenti di affiliazione più popolari o per aiutare a convalidare il numero di riferimenti forniti dallo stato dei partner.

Affinché la pagina possa essere compilata correttamente, è necessario soddisfare diversi requisiti:
* Se si utilizza il tracciamento manuale dei collegamenti personalizzato, è necessario avviare una `tl()` richiesta con il parametro centrale impostato su `e`.
* Se si utilizza il tracciamento automatico dei collegamenti personalizzato, tutti i requisiti devono essere soddisfatti:
   * La variabile [trackExternalLinks](/help/implement/vars/config-vars/trackexternallinks.md) deve essere abilitata.
   * Il collegamento su cui l&#39;utente ha fatto clic non deve corrispondere ad alcun valore all&#39;interno della variabile [linkInternalFilters](/help/implement/vars/config-vars/linkinternalfilters.md) .
   * Se la variabile [linkExternalFilters](/help/implement/vars/config-vars/linkexternalfilters.md) esiste, il collegamento esterno deve corrispondere ad almeno uno dei valori impostati in questa variabile.
* Se uno dei requisiti di cui sopra non è soddisfatto, l&#39;hit non compila il rapporto.
* Come per tutti gli hit di tracciamento dei collegamenti personalizzati, la variabile [pageName](/help/implement/vars/page-vars/pagename.md) viene rimossa dalla richiesta di immagine per impedire l’inflazione alla metrica delle visualizzazioni di pagina.
* Puoi visualizzare questo rapporto in formati con tendenze e classifica.
* Questo rapporto può utilizzare un filtro di ricerca per individuare specifici elementi di riga.
* Puoi creare [suddivisioni](/help/analyze/reports-analytics/reports-customize/breakdowns.md) con qualsiasi altra variabile.
