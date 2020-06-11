---
description: I filtri URL interni identificano i referenti considerati interni al sito. Aiutano i rapporti sulle origini del traffico a compilare i dati e a filtrare il traffico interno.
title: Filtri URL interni
topic: Admin tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
translation-type: tm+mt
source-git-commit: 6fc8145d9a94427ec942d55776b6029f7dd6f79c
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 2%

---


# Filtri URL interni

I filtri URL interni identificano i referenti considerati interni al sito. Aiutano i rapporti sulle origini del traffico a compilare i dati e a filtrare il traffico interno.

Un referente, o pagina di provenienza, è in genere la pagina dalla quale un visitatore è entrato nel sito. Per evitare di distorcere i dati, potete filtrare i riferimenti interni. I report escludono i referenti filtrati dalla dimensione [Referenti](/help/components/dimensions/referrer.md) , dalla dimensione Dominio [di](/help/components/dimensions/referring-domain.md) riferimento e da altre dimensioni dell&#39;origine del traffico.

Il motivo più comune per cui i rapporti sulle origini di traffico non compilano i dati è che l&#39;elenco dei filtri URL interni non è definito. Per verificare quali filtri URL interni sono stati impostati in una suite di rapporti, segui questi passaggi. Per evitare questo problema, rimuovere la regola che elenca un punto (.) come filtro e aggiungete il vostro sito.

Il motivo per cui un punto è il filtro URL interno predefinito è che consente la raccolta dei dati nel rapporto Pagine. Se gli hit non corrispondono ai filtri URL interni, tutte le pagine vengono visualizzate come Altro. Un punto si trova sempre in un punto dell’URL, per garantire che il rapporto Pagine venga popolato.
