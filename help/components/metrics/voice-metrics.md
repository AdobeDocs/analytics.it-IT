---
title: Metriche di analisi vocale
description: Metriche di analisi vocale
feature: Metrics
exl-id: 3c1b4e4e-d8d2-446f-9582-a2ce5580a8d3
TQID: https://experienceleague.adobe.com/snDtqM3TiX--cjPjKj8cGkaFxMIxRprvD4ia9OnBXJk
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 97
ht-degree: 22%

---

# Metriche di analisi vocale

Quando abiliti [!UICONTROL Voice and Chatbots] su [[!UICONTROL Application reporting]](/help/admin/tools/manage-rs/edit-settings/app-reporting.md), vengono create le metriche seguenti (e [dimensioni](../dimensions/voice-dimensions.md)). È possibile utilizzare [Variabili di dati di contesto](/help/implement/vars/page-vars/contextdata.md) per impostarle su un valore di `1` (o più se applicabile). Se abilitate nelle impostazioni della suite di rapporti, vengono create automaticamente [Regole di elaborazione](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) che mappano le metriche di analisi vocale alla variabile di dati di contesto associata.

| Nome della metrica | Descrizione | Variabile dati contestuali |
| --- | --- | --- |
| Espressioni vocali | Si attiva quando un comando viene inviato a un assistente vocale. | `a.voiceutterances` |
| Fine sessione vocale | Si attiva quando l’app vocale viene chiusa. | `a.voiceendsession` |
| Errore vocale | Si attiva quando l’app vocale rileva un errore. | `a.voiceerror` |

{style="table-layout:auto"}
