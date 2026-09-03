---
description: Scopri come implementare l’assegnazione tag multisuite per inviare richieste di immagini a più suite di rapporti.
title: Implementazione dell’assegnazione tag per più suite
feature: Implementation Basics
exl-id: c7fb0478-97e1-4367-8742-e7539f6f82e7
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/djrzQEjvc--wnh2wR1HNV-LVEn6RPcyiaLKLha5pfSY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c77ba355-6681-41fe-b719-563d3f507fdb
  - id: df312454-73c4-43f6-a90e-18f5043f074c
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 302
ht-degree: 5%

---

# Implementazione dell’assegnazione tag per più suite

[Assegnazione di tag multisuite](/help/admin/tools/manage-rs/rollup-report-suite.md) consente di inviare richieste di immagini non solo a una suite di rapporti globale, ma anche a suite di rapporti figlio singole, in modo da poter fornire sottoinsiemi dei dati della suite di rapporti globale della tua azienda a utenti finali diversi.

Per implementare l’assegnazione tag multisuite, devi includere l’ID suite di rapporti (RSID) per la suite di rapporti globale e gli RSID per le suite di rapporti figlio applicabili nel codice di tracciamento per le pagine web e le app.

* Per le implementazioni di tag Adobe Experience Platform, specifica ciascuna suite di rapporti per l&#39;[[!DNL Analytics] estensione](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=it).

* Per le implementazioni legacy di JavaScript e SDK mobile, separa gli RSID con virgole e senza spazi (`rsid1,rsid2,rsid3` e così via).

* Per altri tipi di implementazione, utilizzare la sintassi richiesta per elencare più RSID.

>[!TIP]
>
> La best practice prevede di elencare prima la suite di rapporti globale o l’ID della suite di rapporti.

L’assegnazione di tag multisuite comporta più chiamate al server per ogni richiesta di immagine: una chiamata primaria alla suite di rapporti globale e una chiamata secondaria per ogni suite di rapporti figlio.

>[!NOTE]
>
> [Le suite di rapporti virtuali](/help/components/vrs/vrs-about.md), che consentono anche di fornire sottoinsiemi dei dati della suite di rapporti globale della tua azienda a utenti finali diversi, non generano chiamate al server secondarie.

## Devo implementare l’assegnazione di tag a più suite o suite di rapporti virtuali?

L’utilizzo di suite di rapporti virtuali invece dell’assegnazione tag per più suite rappresenta spesso una best practice, ma le esigenze aziendali determinano l’approccio migliore per la suite di rapporti nella tua organizzazione.

Per capire se le suite di rapporti virtuali sono l&#39;approccio migliore, consulta &quot;[Considerazioni sulle suite di rapporti virtuali e sull&#39;assegnazione di tag a più suite](/help/components/vrs/vrs-considerations.md).&quot; Vedi anche &quot;[Suite di rapporti virtuali e assegnazione di tag a più suite](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78)&quot; per un confronto tra l&#39;assegnazione di tag a più suite e le funzionalità delle suite di rapporti virtuali.
