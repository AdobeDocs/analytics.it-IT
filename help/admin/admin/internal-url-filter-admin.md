---
description: I filtri URL interni identificano i referenti considerati interni al sito. Aiutano i rapporti sulle origini del traffico a compilare i dati e a filtrare il traffico interno.
solution: Analytics
title: Filtri URL interni
topic: Admin tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Filtri URL interni

I filtri URL interni identificano i referenti considerati interni al sito. Aiutano i rapporti sulle origini del traffico a compilare i dati e a filtrare il traffico interno.

Un referente, o pagina di provenienza, è in genere la pagina dalla quale un visitatore è entrato nel sito. Per evitare di distorcere i dati, potete filtrare i riferimenti interni. I report escludono i referenti filtrati dal report [](/help/components/c-variables/dimensionslist/reports-referrers.md)Referenti, dal report [Domini di](/help/components/c-variables/dimensionslist/reports-referring-domains.md)riferimento e da altri report Metodi di ricerca.

Il motivo più comune per cui i rapporti sulle origini di traffico non compilano i dati è che l'elenco dei filtri URL interni non è definito. Per verificare quali filtri URL interni sono stati impostati in una suite di rapporti, segui questi passaggi. Per evitare questo problema, rimuovere la regola che elenca un punto (.) come filtro e aggiungete il vostro sito.

Il motivo per cui un punto è il filtro URL interno predefinito è che consente la raccolta dei dati nel rapporto Pagine. Se gli hit non corrispondono ai filtri URL interni, tutte le pagine vengono visualizzate come Altro. Un punto si trova sempre in un punto dell’URL, per garantire che il rapporto Pagine venga popolato.
