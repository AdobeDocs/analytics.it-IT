---
title: Browser
description: Nome e versione del browser utilizzato.
feature: Dimensions
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
source-git-commit: 206df584deab5f6f9b8eeb09d9c8ad4983424eea
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 2%

---

# Browser

L&#39;&#39;[!UICONTROL Browser]&#39; [dimensione](overview.md) segnala il nome e la versione del browser che invia l’hit. Questa dimensione è utile quando desideri misurare i browser più comuni utilizzati dai visitatori. Quando esegui il test di nuove versioni del sito, puoi eseguirli sui browser principali in questa dimensione per massimizzare le attività di controllo della qualità.

## Popola questa dimensione con i dati

Questa dimensione fa riferimento a una tabella di ricerca interna a Adobe. Il valore di ricerca si basa sul `User-Agent` Intestazione HTTP nelle richieste di immagini. Adobe di partner con [DeviceAtlas](https://deviceatlas.com/) per mantenere le ricerche tra agente utente e browser.

* Ad AppMeasurement, le implementazioni di questa dimensione sono pronte all’uso.
* Per le implementazioni dell’SDK web, abilita [!UICONTROL Device Lookup] quando [configurazione di uno stream di dati](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html).

## Elementi dimensionali

Gli elementi di Dimension includono i nomi e le versioni del browser utilizzati. Versioni diverse dello stesso browser sono elementi dimensionali separati.

Alcuni elementi dimensionali contengono `"(unknown version)"` invece del numero di versione. Questo elemento dimensione fa riferimento a una versione recente del browser che Adobe non ha ancora aggiunto alle proprie tabelle di ricerca. Poiché i browser si aggiornano frequentemente, il `"(unknown version)"` per un determinato browser è comune e temporaneo. Adobe in genere aggiorna le tabelle di ricerca durante le versioni di manutenzione mensili.