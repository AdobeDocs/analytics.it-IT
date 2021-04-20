---
description: I filtri URL interni identificano i referenti considerati interni al sito. Aiutano i rapporti sulle origini di traffico a popolare i dati e a filtrare il traffico interno.
title: Filtri URL interni
feature: Admin Tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 3%

---

# Filtri URL interni

**[!UICONTROL Admin > Report Suites > Edit Settings > General > Internal URL Filters > Add Filter]**

I filtri URL interni identificano i referenti considerati interni al sito. Aiutano i rapporti sulle origini di traffico a popolare i dati e a filtrare il traffico interno.

Un referente o pagina di riferimento è in genere la pagina da cui un visitatore è entrato nel sito. Per evitare l’inclinazione dei dati, puoi filtrare i riferimenti interni. I report escludono i referenti filtrati dalla dimensione [Referrers](/help/components/dimensions/referrer.md), dalla dimensione [Dominio di riferimento](/help/components/dimensions/referring-domain.md) e da altre dimensioni dell&#39;origine del traffico.

Il motivo più comune per cui i rapporti sulle origini di traffico non compilano i dati è che l’elenco dei filtri URL interni non è definito. Per verificare quali filtri URL interni sono stati impostati in una suite di rapporti, effettua le seguenti operazioni. Per evitare questo problema, rimuovi la regola che elenca un punto (.) come filtro e aggiungi il tuo sito.

Il motivo per cui un punto è il filtro URL interno predefinito è quello di consentire la raccolta dei dati nel rapporto Pagine. Se gli hit non corrispondono ai filtri URL interni, tutte le pagine vengono visualizzate come Altro. Un punto si trova sempre in un punto dell’URL, il che garantisce che il rapporto Pagine sia popolato.
