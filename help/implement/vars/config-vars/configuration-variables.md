---
title: Variabili di configurazione
description: Utilizza le variabili di configurazione per determinare in che modo vengono raccolti i dati.
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 5%

---

# Panoramica delle variabili di configurazione

Le variabili di configurazione controllano il modo in cui i dati vengono acquisiti ed elaborati nel reporting. In genere non contengono valori di dimensione o metrica.

## Impostazione delle variabili di configurazione

Nelle implementazioni JavaScript che utilizzano `AppMeasurement.js`, le variabili di configurazione sono generalmente impostate nella parte superiore del file JS.

Nelle implementazioni che utilizzano i tag Adobe Experience Platform, le variabili di configurazione si trovano in genere configurando l&#39;estensione Adobe Analytics:

1. Vai a `experience.adobe.com` e accedi quando richiesto.
1. Select [!UICONTROL Launch / Data Collection].
1. Fare clic su [!UICONTROL Go to Launch / Data Collection], quindi selezionare [!UICONTROL Tags].
1. Fare clic sulla proprietà che si desidera modificare.
1. Fai clic sulla scheda [!UICONTROL Extensions] , quindi fai clic su [!UICONTROL Configure] in Adobe Analytics.

>[!IMPORTANT]
>
>Assicurati che tutte le variabili di configurazione siano impostate prima di richiamare un metodo di tracciamento ([`t()`](../functions/t-method.md) o [`tl()`](../functions/tl-method.md)). Evita di impostare le variabili di configurazione nella funzione [`doPlugins()`](../functions/doplugins.md) .
