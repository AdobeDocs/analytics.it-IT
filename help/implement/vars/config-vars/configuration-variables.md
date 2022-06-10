---
title: Variabili di configurazione
description: Utilizza le variabili di configurazione per determinare in che modo vengono raccolti i dati.
feature: Variables
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '122'
ht-degree: 4%

---

# Panoramica delle variabili di configurazione

Le variabili di configurazione controllano il modo in cui i dati vengono acquisiti ed elaborati nel reporting. In genere non contengono valori di dimensione o metrica.

## Impostazione delle variabili di configurazione

Nelle implementazioni che utilizzano l&#39;estensione Web SDK o l&#39;estensione Analytics, le variabili di configurazione si trovano in genere nelle impostazioni dell&#39;estensione:

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic sulla proprietà tag desiderata.
1. Fai clic sul pulsante [!UICONTROL Extensions] scheda , quindi fai clic su [!UICONTROL Configure] nell&#39;ambito della proroga.

Nelle implementazioni JavaScript che utilizzano `AppMeasurement.js`, le variabili di configurazione sono solitamente impostate nella parte superiore del file JS.

>[!IMPORTANT]
>
>Assicurati che tutte le variabili di configurazione siano impostate prima di richiamare un metodo di tracciamento ([`t()`](../functions/t-method.md) o [`tl()`](../functions/tl-method.md)). Evita di impostare le variabili di configurazione nel [`doPlugins()`](../functions/doplugins.md) funzione .
