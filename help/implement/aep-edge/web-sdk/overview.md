---
title: Implementare Adobe Analytics utilizzando Adobe Experience Platform Web SDK
description: Utilizza il Web SDK per inviare dati ad Adobe Analytics.
exl-id: 97f8d650-247f-4386-b4d2-699f3dab0467
feature: Implementation Basics
role: Admin, Developer, Leader
TQID: 'https://experienceleague.adobe.com/8p05Bfxo37frjI9pPQOPHPtzt8yxPmFXj-nYW00IYfE'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
subfeature_v2:
  - id: b3e5f43e-2e2f-43c0-810a-044a5f91e31a
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 242
ht-degree: 23%

---

# Implementare Adobe Analytics utilizzando Adobe Experience Platform Web SDK

Puoi utilizzare [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/web-sdk/home.html) per inviare dati ad Adobe Analytics. Esistono due metodi principali per implementare il Web SDK e ogni metodo ha due tipi di implementazione:

| | **Migra da AppMeasurement** | **Implementazione pulita di Web SDK** |
| --- | --- | --- |
| **Usa tag** | [Migrare dall&#39;estensione Analytics all&#39;estensione Web SDK](analytics-extension-to-web-sdk.md) | [Invia dati ad Adobe Analytics tramite l&#39;estensione Web SDK](web-sdk-tag-extension.md) |
| **Usa JavaScript** | [Migrazione da AppMeasurement alla libreria JavaScript di Web SDK](appmeasurement-to-web-sdk.md) | [Invia dati ad Adobe Analytics utilizzando la libreria JavaScript di Web SDK](web-sdk-javascript-library.md) |

Se la tua organizzazione richiede una nuova implementazione di Web SDK e prevede di utilizzare Customer Journey Analytics in futuro, Adobe consiglia un’implementazione pulita di Web SDK utilizzando il tuo schema. Consulta [Inserire dati tramite Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) nella guida utente di Customer Journey Analytics.

## Risorse aggiuntive

I tag possono essere altamente personalizzati. Scopri come ottenere il massimo da Adobe Analytics includendo i dati corretti nella tua implementazione.

- [Documentazione sui tag](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html#): scopri come funziona l&#39;interfaccia e quali estensioni sono disponibili.

- [Documentazione di Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/web-sdk.html?lang=it)
