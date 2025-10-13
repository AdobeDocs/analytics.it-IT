---
title: Sistema operativo
description: Il sistema operativo del visitatore.
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
source-git-commit: 9c3e65392d6e5929ce1ecefbc460c1fd5576aed8
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 7%

---

# Sistema operativo

La [dimensione](overview.md) del &#39;sistema operativo&#39; mostra il sistema operativo e la versione utilizzati dal visitatore. Se nella proprietà web sono presenti funzioni specifiche per il sistema operativo, questa dimensione ti aiuta a capire quali sistemi operativi sono più comuni.

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento a una tabella di ricerca interna ad Adobe. Il valore di ricerca si basa sull&#39;intestazione HTTP `User-Agent` nelle richieste di immagini. Adobe collabora con [DeviceAtlas](https://deviceatlas.com/) per mantenere le ricerche tra l&#39;agente utente e il sistema operativo.

* Per le implementazioni di AppMeasurement, questa dimensione funziona in modo predefinito.
* Per le implementazioni di Web SDK, abilita [!UICONTROL Device Lookup] quando [si configura uno stream di dati](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=it).

## Elementi dimensionali

Gli elementi di Dimension includono i sistemi operativi utilizzati dai visitatori. Gli esempi includono `"Windows 10"`, `"OS X 10.15.7"` e `"Android 9"`.

## Tracciamento delle versioni precise del sistema operativo

Con l’evoluzione del settore verso gli hint client, alcune versioni dei sistemi operativi sono potenzialmente confuse. Ad esempio, &quot;Windows 10&quot; e &quot;Windows 11&quot; possono essere raggruppati in &quot;Windows 10&quot; se non si raccolgono hint client ad alta entropia. Per informazioni dettagliate, consulta [Client hints](/help/technotes/client-hints.md) nella guida delle note tecniche.
