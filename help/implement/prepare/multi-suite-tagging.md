---
description: Scopri come implementare l’assegnazione tag a più suite per inviare una richiesta di immagine a più suite di rapporti.
title: Implementazione dell’assegnazione tag per più suite
feature: Implementation Basics
exl-id: c7fb0478-97e1-4367-8742-e7539f6f82e7
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 2%

---

# Implementazione dell’assegnazione tag per più suite

[Assegnazione di tag a più suite](/help/admin/c-manage-report-suites/rollup-report-suite.md) consente di inviare richieste di immagini non solo a una suite di rapporti globale, ma anche a suite di rapporti figlio individuali, in modo da poter fornire sottoinsiemi dei dati della suite di rapporti globale della tua azienda a utenti finali diversi.

Per implementare l’assegnazione tag a più suite, devi includere nel codice di tracciamento delle pagine web e delle app l’ID suite di rapporti (RSID) per la suite di rapporti globale e gli RSID per le suite di rapporti figlio applicabili.

* Per le implementazioni di tag Adobe Experience Platform, specifica ciascuna suite di rapporti per [[!DNL Analytics] estensione](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html).

* Per le implementazioni JavaScript e SDK per dispositivi mobili legacy, separa gli RSID con virgole e senza spazi (`rsid1,rsid2,rsid3` e così via).

* Per altri tipi di implementazione, utilizza la sintassi richiesta per elencare più RSID.

>[!TIP]
>
> La best practice prevede di elencare prima la suite di rapporti globale o l’ID suite di rapporti.

L’assegnazione tag a più suite esegue più chiamate server per ogni richiesta di immagine: una chiamata principale alla suite di rapporti globale e una chiamata secondaria per ogni suite di rapporti figlio.

>[!NOTE]
>
> [Suite di rapporti virtuali](/help/components/vrs/vrs-about.md), che consentono anche di fornire sottoinsiemi dei dati della suite di rapporti globale della tua azienda a utenti finali diversi, non devono effettuare chiamate server secondarie.

## Devo implementare l’assegnazione tag a più suite o suite di rapporti virtuali?

Spesso è consigliabile utilizzare suite di rapporti virtuali invece di assegnare tag a più suite, ma è necessario determinare l’approccio migliore per le suite di rapporti per l’organizzazione.

Per capire se le suite di rapporti virtuali sono il tuo approccio migliore, vedi &quot;[Suite di rapporti virtuali e considerazioni sull’assegnazione di tag a più suite](/help/components/vrs/vrs-considerations.md).&quot; Vedi anche &quot;[Suite di rapporti virtuali e assegnazione di tag a più siti](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78)&quot; per un confronto tra l’assegnazione di tag a più suite e la funzionalità della suite di rapporti virtuali.
