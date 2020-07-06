---
title: Variabili di configurazione
description: Utilizzate le variabili di configurazione per determinare in che modo vengono raccolti i dati.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '121'
ht-degree: 5%

---


# Panoramica delle variabili di configurazione

Le variabili di configurazione controllano il modo in cui i dati vengono catturati ed elaborati nel reporting. In genere non contengono valori di dimensione o metrica.

## Impostazione delle variabili di configurazione

Nelle implementazioni JavaScript che utilizzano `AppMeasurement.js`, le variabili di configurazione sono generalmente impostate nella parte superiore del file JS.

Nelle implementazioni che utilizzano  lancio Adobe Experience Platform, le variabili di configurazione si trovano in genere configurando l&#39;estensione Adobe  Analytics:

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your Adobe ID credentials.
2. Fare clic sulla proprietà che si desidera modificare.
3. Fare clic sulla [!UICONTROL Extensions] scheda, quindi su [!UICONTROL Configure] in Adobe  Analytics.

>[!IMPORTANT]
>
>Assicurati che tutte le variabili di configurazione siano impostate prima di chiamare un metodo di tracciamento ([`t()`](../functions/t-method.md) o [`tl()`](../functions/tl-method.md)). Evitare di impostare le variabili di configurazione nella [`doPlugins()`](../functions/doplugins.md) funzione.
