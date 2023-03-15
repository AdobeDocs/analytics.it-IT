---
title: Variabili di configurazione
description: Utilizza le variabili di configurazione per determinare come vengono raccolti i dati.
feature: Variables
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '122'
ht-degree: 20%

---

# Panoramica delle variabili di configurazione

Le variabili di configurazione controllano il modo in cui i dati vengono acquisiti ed elaborati nei rapporti. In genere non contengono valori di dimensioni o metriche.

## Impostazione delle variabili di configurazione

Nelle implementazioni che utilizzano l’estensione Web SDK o l’estensione Analytics, le variabili di configurazione si trovano in genere nelle impostazioni dell’estensione:

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Fai clic su [!UICONTROL Extensions] , quindi fai clic su [!UICONTROL Configure] nell’estensione.

Nelle implementazioni JavaScript con `AppMeasurement.js`, le variabili di configurazione sono in genere impostate nella parte superiore del file JS.

>[!IMPORTANT]
>
>Assicurati che tutte le variabili di configurazione siano impostate prima di chiamare un metodo di tracciamento ([`t()`](../functions/t-method.md) o [`tl()`](../functions/tl-method.md)). Evita di impostare le variabili di configurazione in [`doPlugins()`](../functions/doplugins.md) funzione.
