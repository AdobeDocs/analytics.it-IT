---
title: Dimensioni di analisi vocale
description: Dimensioni di analisi vocale
feature: Dimensions
exl-id: 6e1275c4-3b17-4c65-a308-d420ea1acdf6
source-git-commit: c2adf6d2e328378332cc290ba2dfd75ee6587ef6
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 4%

---

# Dimensioni di analisi vocale

Quando abiliti [!UICONTROL Voice and Chatbots] su [[!UICONTROL Application reporting]](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/app-reporting.md), vengono create le seguenti dimensioni (e [metriche](../metrics/voice-metrics.md)). È possibile utilizzare [Variabili di dati di contesto](/help/implement/vars/page-vars/contextdata.md) per impostarle sul valore di stringa desiderato. Se abilitate nelle impostazioni della suite di rapporti, vengono create automaticamente [Regole di elaborazione](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-overview.md) che mappano le dimensioni di analisi vocale alla variabile di dati di contesto associata.

| Nome dimensione | Descrizione | Variabile dati contestuali |
| --- | --- | --- |
| Tipo di errore vocale | Tipo di errore riscontrato. | `a.voiceerrortype` |
| Lingua vocale | Linguaggio con cui l’utente interagisce con la tua app vocale. | `a.voicelanguage` |
| Intento vocale | Comando che l&#39;utente intende eseguire. | `a.voiceintent` |
| Risposta app vocali | Risposta restituita dall&#39;app vocale all&#39;utente. | `a.voiceappresponse` |
| Autenticazione vocale | Lo stato di autenticazione dell’utente durante l’interazione con l’app vocale. | `a.voiceauthentication` |
| ID punto di interesse | ID del punto di interesse. | `a.loc.poi.id` |

{style="table-layout:auto"}
