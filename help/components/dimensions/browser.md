---
title: Browser
description: Nome e versione del browser utilizzato.
feature: Dimensions
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
source-git-commit: 206df584deab5f6f9b8eeb09d9c8ad4983424eea
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 5%

---

# Browser

La [dimensione](overview.md) &#39;[!UICONTROL Browser]&#39; riporta il nome e la versione del browser che invia l&#39;hit. Questa dimensione è utile quando desideri misurare i browser più comuni utilizzati dai visitatori. Quando esegui il test di nuove versioni del sito, puoi eseguirli sui browser principali in questa dimensione per massimizzare le attività di controllo della qualità.

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento a una tabella di ricerca interna a Adobe. Il valore di ricerca si basa sull&#39;intestazione HTTP `User-Agent` nelle richieste di immagini. Adobe di partner con [DeviceAtlas](https://deviceatlas.com/) per mantenere le ricerche tra l&#39;agente utente e il browser.

* Ad AppMeasurement, le implementazioni di questa dimensione sono pronte all’uso.
* Per le implementazioni Web SDK, abilita [!UICONTROL Device Lookup] quando [si configura uno stream di dati](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=it).

## Elementi dimensionali

Gli elementi di Dimension includono i nomi e le versioni del browser utilizzati. Versioni diverse dello stesso browser sono elementi dimensionali separati.

Alcuni elementi di dimensione contengono `"(unknown version)"` invece del numero di versione. Questo elemento dimensione fa riferimento a una versione recente del browser che Adobe non ha ancora aggiunto alle proprie tabelle di ricerca. Poiché i browser si aggiornano frequentemente, `"(unknown version)"` per un determinato browser è comune e temporaneo. Adobe in genere aggiorna le tabelle di ricerca durante le versioni di manutenzione mensili.