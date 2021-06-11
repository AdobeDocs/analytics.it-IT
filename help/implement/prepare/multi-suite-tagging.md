---
description: Scopri come implementare l’assegnazione tag a più suite per inviare una richiesta di immagine a più suite di rapporti.
title: Implementazione di tag per più suite
exl-id: null
source-git-commit: 81da9ff9b00a69c49c028fc7f006c161d8ff21d4
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 0%

---


# Implementazione di tag per più suite

[Il ](/help/admin/c-manage-report-suites/rollup-report-suite.md) tag per più suite consente di inviare richieste di immagini non solo a una suite di rapporti globale, ma anche a suite di rapporti figlio individuali, in modo da poter fornire sottoinsiemi dei dati della suite di rapporti globale della tua azienda a utenti finali diversi.

Per implementare l’assegnazione tag a più suite, devi includere nel codice di tracciamento delle pagine web e delle app l’ID suite di rapporti (RSID) per la suite di rapporti globale e gli RSID per le suite di rapporti figlio applicabili.

* Per le implementazioni di Adobe Experience Platform Launch, specifica ciascuna suite di rapporti per l&#39; [[!DNL Analytics] estensione](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html).

* Per le implementazioni JavaScript e SDK per dispositivi mobili legacy, separa gli RSID con virgole e senza spazi (`rsid1,rsid2,rsid3` e così via).

* Per altri tipi di implementazione, utilizza la sintassi richiesta per elencare più RSID.

>[!TIP]
>
> La best practice prevede di elencare prima la suite di rapporti globale o l’ID suite di rapporti.

L’assegnazione tag a più suite esegue più chiamate server per ogni richiesta di immagine: una chiamata principale alla suite di rapporti globale e una chiamata secondaria per ogni suite di rapporti figlio.

>[!NOTE]
>
> [Le suite di rapporti virtuali](/help/components/vrs/vrs-about.md), che consentono anche di fornire sottoinsiemi dei dati della suite di rapporti globale della tua azienda a utenti finali diversi, non eseguono chiamate al server secondario.

## Devo implementare l’assegnazione tag a più suite o suite di rapporti virtuali?

Spesso è consigliabile utilizzare suite di rapporti virtuali invece di assegnare tag a più suite, ma è necessario determinare l’approccio migliore per le suite di rapporti per l’organizzazione.

Per capire se le suite di rapporti virtuali sono l’approccio migliore, consulta &quot;[Suite di rapporti virtuali e considerazioni sull’assegnazione di tag a più suite](/help/components/vrs/vrs-considerations.md)&quot;. Consulta anche &quot;[Suite di rapporti virtuali vs. Tagging multisuite](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78)&quot; per un confronto tra l’assegnazione di tag a più suite e le funzionalità della suite di rapporti virtuali.
