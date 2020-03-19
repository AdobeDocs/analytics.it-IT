---
title: Variabili di configurazione
description: Utilizzate le variabili di configurazione per determinare in che modo vengono raccolti i dati.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Panoramica delle variabili di configurazione

Le variabili di configurazione controllano il modo in cui i dati vengono catturati ed elaborati nel reporting. In genere non contengono valori di dimensione o metrica.

## Impostazione delle variabili di configurazione

Nelle implementazioni JavaScript che utilizzano `AppMeasurement.js`, le variabili di configurazione sono generalmente impostate nella parte superiore del file JS.

Nelle implementazioni tramite Adobe Experience Platform Launch, le variabili di configurazione si trovano solitamente configurando l&#39;estensione Adobe Analytics:

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your Adobe ID credentials.
2. Fare clic sulla proprietà che si desidera modificare.
3. Fai clic sulla [!UICONTROL Extensions] scheda, quindi fai clic [!UICONTROL Configure] sotto Adobe Analytics.

> [!IMPORTANT] Assicurati che tutte le variabili di configurazione siano impostate prima di chiamare un metodo di tracciamento ([`t()`](../functions/t-method.md) o [`tl()`](../functions/tl-method.md)). Evitare di impostare le variabili di configurazione nella [`doPlugins()`](../functions/doplugins.md) funzione.
