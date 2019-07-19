---
description: I filtri interni degli URL identificano i referenti considerati interni al sito. Essi aiutano i rapporti sulle origini del traffico a compilare i dati e a filtrare il traffico interno.
seo-description: I filtri interni degli URL identificano i referenti considerati interni al sito. Essi aiutano i rapporti sulle origini del traffico a compilare i dati e a filtrare il traffico interno.
seo-title: Filtri URL interni
solution: Analytics
title: Filtri URL interni
topic: Strumenti di amministrazione
uuid: 70868 edb -208 d -4 dad -9401-70967468 d 40 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Filtri URL interni

I filtri interni degli URL identificano i referenti considerati interni al sito. Essi aiutano i rapporti sulle origini del traffico a compilare i dati e a filtrare il traffico interno.

Un referente, o pagina di provenienza, è in genere la pagina da cui un visitatore è entrato nel sito. Per evitare di inclinare i dati, potete filtrare i riferimenti interni. Reports exclude filtered referrers from the [Referrers Report](/help/components/c-variables/dimensionslist/reports-referrers.md), the [Referring Domains Report](/help/components/c-variables/dimensionslist/reports-referring-domains.md), and other Finding Methods reports.

I rapporti più comuni relativi alle origini di traffico non sono i dati che l'elenco filtro URL interno non è definito. Per verificare quali filtri URL interni sono stati configurati in una suite di rapporti, segui questi passaggi. Per evitare questa situazione, rimuovete la regola di un punto (.) come filtro e aggiungete il vostro sito.

Il motivo per cui un punto è il filtro URL interno predefinito è consentire la raccolta dei dati nel rapporto Pagine. Se gli hit non corrispondono a filtri URL interni, tutte le pagine vengono visualizzate come Altro. Un punto è sempre in un punto dell'URL, che garantisce la compilazione del rapporto Pagine.
