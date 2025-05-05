---
title: Implementare Adobe Analytics utilizzando Adobe Experience Platform Web SDK
description: Utilizza l’SDK per web per inviare dati ad Adobe Analytics.
exl-id: 97f8d650-247f-4386-b4d2-699f3dab0467
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: d6c16d8841110e3382248f4c9ce3c2f2e32fe454
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 18%

---

# Implementare Adobe Analytics utilizzando Adobe Experience Platform Web SDK

Puoi utilizzare [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/web-sdk/home.html?lang=it) per inviare dati ad Adobe Analytics. Esistono due metodi principali per implementare l’SDK per web e ogni metodo ha due tipi di implementazione:

| | **Migra da AppMeasurement** | **Implementazione pulita di Web SDK** |
| --- | --- | --- |
| **Usa tag** | [Migrare dall&#39;estensione Analytics all&#39;estensione Web SDK](analytics-extension-to-web-sdk.md) | [Invia dati ad Adobe Analytics tramite l&#39;estensione Web SDK](web-sdk-tag-extension.md) |
| **Usa JavaScript** | [Migrare da AppMeasurement alla libreria JavaScript dell&#39;SDK Web](appmeasurement-to-web-sdk.md) | [Invia dati ad Adobe Analytics utilizzando la libreria JavaScript dell&#39;SDK Web](web-sdk-javascript-library.md) |

Se la tua organizzazione richiede una nuova implementazione dell’SDK web e prevede di utilizzare il Customer Journey Analytics in futuro, l’Adobe consiglia un’implementazione dell’SDK web pulita utilizzando il tuo schema. Consulta [Inserire dati tramite Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) nella guida utente del Customer Journey Analytics.

## Risorse aggiuntive

I tag possono essere altamente personalizzati. Scopri come ottenere il massimo da Adobe Analytics includendo i dati corretti nella tua implementazione.

- [Documentazione sui tag](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=it#): scopri come funziona l&#39;interfaccia e quali estensioni sono disponibili.

- [Documentazione di Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/web-sdk.html?lang=it)
