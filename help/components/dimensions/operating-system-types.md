---
title: Tipi di sistemi operativi
description: Il sistema operativo indipendentemente dalla versione.
feature: Dimensions
exl-id: 0afd5261-98e8-4247-865a-1b8844c53ff4
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 5%

---

# Tipi di sistemi operativi

I &#39;tipi di sistemi operativi&#39; [dimensione](overview.md) mostra il sistema operativo generale utilizzato dal visitatore, indipendentemente dalle versioni specifiche. Questa dimensione è utile per capire non solo quali sistemi operativi e versioni specifiche sono più comuni, ma anche quali sono utilizzate dai visitatori tipici della piattaforma del sistema operativo.

## Popola questa dimensione con i dati

Questa dimensione fa riferimento a una tabella di ricerca interna a Adobe. Il valore di ricerca si basa sul `User-Agent` Intestazione HTTP nelle richieste di immagini. Adobe di partner con [DeviceAtlas](https://deviceatlas.com/) per mantenere le ricerche tra agente utente e tipo di sistema operativo.

* Ad AppMeasurement, le implementazioni di questa dimensione sono pronte all’uso.
* Per le implementazioni dell’SDK web, abilita [!UICONTROL Device Lookup] quando [configurazione di uno stream di dati](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html).

## Elementi dimensionali

Gli elementi di Dimension includono il tipo di sistema operativo utilizzato. Alcuni esempi includono `"Microsoft Windows"`, `"Apple Macintosh"`, `"Google Android"`, e `"Apple iOS"`.
