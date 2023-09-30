---
title: Tipo di browser
description: Organizzazione che ha creato il browser.
feature: Dimensions
exl-id: 2a88ebc6-879e-4e5b-a8e5-40a32d54ac1b
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 3%

---

# Tipo di browser

Il &quot;tipo di browser&quot; [dimensione](overview.md) elenca le organizzazioni che hanno creato il browser utilizzato dal visitatore. Questa dimensione è utile quando desideri vedere quali browser generali utilizzano i visitatori. Fornisce valore sulla dimensione &quot;Browser&quot; in quanto non elenca diverse versioni dello stesso browser come elementi dimensionali separati.

## Popola questa dimensione con i dati

Questa dimensione fa riferimento a una tabella di ricerca interna a Adobe. Il valore di ricerca si basa sul `User-Agent` Intestazione HTTP nelle richieste di immagini. Adobe di partner con [DeviceAtlas](https://deviceatlas.com/) per mantenere le ricerche tra agente utente e browser.

* Ad AppMeasurement, le implementazioni di questa dimensione sono pronte all’uso.
* Per le implementazioni dell’SDK web, abilita [!UICONTROL Device Lookup] quando [configurazione di uno stream di dati](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html).

## Elementi dimensionali

Gli elementi di Dimension includono le organizzazioni che creano browser. Gli elementi dimensionali comuni includono `"Google"` (i creatori di [!DNL Chrome]), `"Apple"` (i creatori di [!DNL Safari]), `"Microsoft"` (i creatori di [!DNL Edge]), e `"Mozilla"` (i creatori di [!DNL Firefox]).
