---
title: Tipi di sistemi operativi
description: Il sistema operativo indipendentemente dalla versione.
feature: Dimensions
exl-id: 0afd5261-98e8-4247-865a-1b8844c53ff4
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 11%

---

# Tipi di sistemi operativi

La [dimensione](overview.md) dei &#39;tipi di sistema operativo&#39; mostra il sistema operativo generale utilizzato dal visitatore, indipendentemente da specifiche versioni. Questa dimensione è utile per capire non solo quali sistemi operativi e versioni specifiche sono più comuni, ma anche quali sono utilizzate dai visitatori tipici della piattaforma del sistema operativo.

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento a una tabella di ricerca interna ad Adobe. Il valore di ricerca si basa sull&#39;intestazione HTTP `User-Agent` nelle richieste di immagini. Adobe collabora con [DeviceAtlas](https://deviceatlas.com/) per mantenere le ricerche tra l&#39;agente utente e il tipo di sistema operativo.

* Per le implementazioni di AppMeasurement, questa dimensione funziona in modo predefinito.
* Per le implementazioni di Web SDK, abilita [!UICONTROL Device Lookup] quando [si configura uno stream di dati](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=it).

## Elementi dimensionali

Gli elementi di Dimension includono il tipo di sistema operativo utilizzato. Gli esempi includono `"Microsoft Windows"`, `"Apple Macintosh"`, `"Google Android"` e `"Apple iOS"`.
