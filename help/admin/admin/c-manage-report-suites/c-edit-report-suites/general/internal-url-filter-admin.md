---
description: I filtri URL interni identificano i referenti considerati interni al sito. Agevolano la compilazione dei dati nei rapporti sulle origini del traffico e aiutano a filtrare il traffico interno.
title: Filtri URL interni
feature: Admin Tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
source-git-commit: 71ff81a0ae67c6f4cc9a8df567e27223cc63f18c
workflow-type: ht
source-wordcount: '203'
ht-degree: 100%

---


# Filtri URL interni

I filtri URL interni identificano i referenti considerati interni al sito. Agevolano la compilazione dei dati nei rapporti sulle origini del traffico e aiutano a filtrare il traffico interno.

**[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Internal URL Filters]**

Un referente o pagina di riferimento è in genere la pagina da cui un visitatore è entrato nel sito. Per evitare alterazioni dei dati, puoi filtrare i referenti interni. I rapporti escludono i referenti filtrati dalla dimensione [Referenti](/help/components/dimensions/referrer.md), dalla dimensione [Domini di riferimento](/help/components/dimensions/referring-domain.md) e da altre dimensioni dell’origine del traffico.

Il motivo più comune per cui i rapporti sulle origini del traffico non compilano i dati è che l’elenco dei filtri URL interni non è definito. Per verificare quali filtri URL interni sono stati impostati in una suite di rapporti, esegui le seguenti operazioni. Per evitare questo problema, rimuovi la regola specificando un punto (.) come filtro e aggiungi il tuo sito.

Il motivo per cui un punto è il filtro URL interno predefinito è quello di consentire la raccolta dei dati nel rapporto Pagine. Se gli hit non corrispondono ai filtri URL interni, tutte le pagine vengono visualizzate come Altro. Un punto si trova sempre all’interno dell’URL, il che garantisce che il rapporto Pagine sia popolato.
