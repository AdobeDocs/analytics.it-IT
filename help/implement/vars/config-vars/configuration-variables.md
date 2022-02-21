---
title: Variabili di configurazione
description: Utilizza le variabili di configurazione per determinare in che modo vengono raccolti i dati.
feature: Variables
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 4%

---

# Panoramica delle variabili di configurazione

Le variabili di configurazione controllano il modo in cui i dati vengono acquisiti ed elaborati nel reporting. In genere non contengono valori di dimensione o metrica.

## Impostazione delle variabili di configurazione

Nelle implementazioni JavaScript che utilizzano `AppMeasurement.js`, le variabili di configurazione sono solitamente impostate nella parte superiore del file JS.

Nelle implementazioni che utilizzano i tag Adobe Experience Platform, le variabili di configurazione si trovano in genere configurando l&#39;estensione Adobe Analytics:

1. Accedi a [Interfaccia utente per la raccolta dati](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fare clic sulla proprietà che si desidera modificare.
1. Fai clic sul pulsante [!UICONTROL Extensions] scheda , quindi fai clic su [!UICONTROL Configure] in Adobe Analytics.

>[!IMPORTANT]
>
>Assicurati che tutte le variabili di configurazione siano impostate prima di richiamare un metodo di tracciamento ([`t()`](../functions/t-method.md) o [`tl()`](../functions/tl-method.md)). Evita di impostare le variabili di configurazione nel [`doPlugins()`](../functions/doplugins.md) funzione .
