---
title: Metriche di analisi vocale
description: Metriche di analisi vocale
feature: Metrics
exl-id: 3c1b4e4e-d8d2-446f-9582-a2ce5580a8d3
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '97'
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
