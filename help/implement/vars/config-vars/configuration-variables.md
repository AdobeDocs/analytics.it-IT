---
title: Variabili di configurazione
description: Utilizza le variabili di configurazione per determinare come vengono raccolti i dati.
feature: Appmeasurement Implementation
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '121'
ht-degree: 17%

---

# Panoramica delle variabili di configurazione

Le variabili di configurazione controllano il modo in cui i dati vengono acquisiti ed elaborati nei rapporti. In genere non contengono valori di dimensioni o metriche.

## Impostazione delle variabili di configurazione

Nelle implementazioni che utilizzano l’estensione Web SDK o Analytics, le variabili di configurazione si trovano in genere nelle impostazioni dell’estensione:

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Fare clic sulla scheda [!UICONTROL Extensions], quindi su [!UICONTROL Configure] sotto l&#39;estensione.

Nelle implementazioni di JavaScript che utilizzano `AppMeasurement.js`, le variabili di configurazione vengono in genere impostate nella parte superiore del file JS.

>[!IMPORTANT]
>
>Assicurarsi che tutte le variabili di configurazione siano impostate prima di chiamare un metodo di tracciamento ([`t()`](../functions/t-method.md) o [`tl()`](../functions/tl-method.md)). Evitare di impostare le variabili di configurazione nella funzione [`doPlugins()`](../functions/doplugins.md).
