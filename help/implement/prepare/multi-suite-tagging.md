---
description: Scopri come implementare l’assegnazione tag multisuite per inviare richieste di immagini a più suite di rapporti.
title: Implementazione dell’assegnazione tag per più suite
feature: Implementation Basics
exl-id: c7fb0478-97e1-4367-8742-e7539f6f82e7
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 2%

---

# Implementazione dell’assegnazione tag per più suite

[Assegnazione di tag multisuite](/help/admin/admin/c-manage-report-suites/rollup-report-suite.md) consente di inviare richieste di immagini non solo a una suite di rapporti globale, ma anche a suite di rapporti figlio singole, in modo da poter fornire sottoinsiemi dei dati della suite di rapporti globale della tua azienda a utenti finali diversi.

Per implementare l’assegnazione tag multisuite, devi includere l’ID suite di rapporti (RSID) per la suite di rapporti globale e gli RSID per le suite di rapporti figlio applicabili nel codice di tracciamento per le pagine web e le app.

* Per le implementazioni di tag Adobe Experience Platform, specifica ciascuna suite di rapporti per [[!DNL Analytics] estensione](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=it).

* Per le implementazioni legacy di JavaScript e Mobile SDK, separa gli RSID con virgole e senza spazi (`rsid1,rsid2,rsid3` e così via).

* Per altri tipi di implementazione, utilizzare la sintassi richiesta per elencare più RSID.

>[!TIP]
>
> La best practice prevede di elencare prima la suite di rapporti globale o l’ID della suite di rapporti.

L’assegnazione di tag multisuite comporta più chiamate al server per ogni richiesta di immagine: una chiamata primaria alla suite di rapporti globale e una chiamata secondaria per ogni suite di rapporti figlio.

>[!NOTE]
>
> [Suite di rapporti virtuali](/help/components/vrs/vrs-about.md), che consente anche di fornire sottoinsiemi dei dati della suite di rapporti globale della tua azienda a utenti finali diversi, non subiscono chiamate al server secondarie.

## Devo implementare l’assegnazione di tag a più suite o suite di rapporti virtuali?

L’utilizzo di suite di rapporti virtuali invece dell’assegnazione tag per più suite rappresenta spesso una best practice, ma le esigenze aziendali determinano l’approccio migliore per la suite di rapporti nella tua organizzazione.

Per capire se le suite di rapporti virtuali sono l’approccio migliore, consulta &quot;[Considerazioni sulle suite di rapporti virtuali e sull’assegnazione di tag a più suite](/help/components/vrs/vrs-considerations.md).&quot; Vedi anche &quot;[Confronto tra suite di rapporti virtuali e assegnazione di tag a più suite](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78)&quot; per un confronto tra l’assegnazione di tag a più suite e le funzionalità delle suite di rapporti virtuali.
