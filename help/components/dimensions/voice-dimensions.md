---
title: Dimensioni di analisi vocale
description: Dimensioni di analisi vocale
feature: Dimensions
exl-id: 6e1275c4-3b17-4c65-a308-d420ea1acdf6
TQID: https://experienceleague.adobe.com/OZ-lQkbS8hsv8ywUUa2BQoH40nfklRkJNd9SlEVkmEI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 128
ht-degree: 17%

---

# Dimensioni di analisi vocale

Quando abiliti [!UICONTROL Voice and Chatbots] su [[!UICONTROL Application reporting]](/help/admin/tools/manage-rs/edit-settings/app-reporting.md), vengono create le seguenti dimensioni (e [metriche](../metrics/voice-metrics.md)). È possibile utilizzare [Variabili di dati di contesto](/help/implement/vars/page-vars/contextdata.md) per impostarle sul valore di stringa desiderato. Se abilitate nelle impostazioni della suite di rapporti, vengono create automaticamente [Regole di elaborazione](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) che mappano le dimensioni di analisi vocale alla variabile di dati di contesto associata.

| Nome dimensione | Descrizione | Variabile dati contestuali |
| --- | --- | --- |
| Tipo di errore vocale | Tipo di errore riscontrato. | `a.voiceerrortype` |
| Lingua voce | Linguaggio con cui l’utente interagisce con la tua app vocale. | `a.voicelanguage` |
| Intento vocale | Comando che l&#39;utente intende eseguire. | `a.voiceintent` |
| Risposta app vocale | Risposta restituita dall&#39;app vocale all&#39;utente. | `a.voiceappresponse` |
| Autenticazione vocale | Lo stato di autenticazione dell’utente durante l’interazione con l’app vocale. | `a.voiceauthentication` |
| ID punto di interesse | ID del punto di interesse. | `a.loc.poi.id` |

{style="table-layout:auto"}
