---
title: Tipo di browser
description: Organizzazione che ha creato il browser.
feature: Dimensions
exl-id: 2a88ebc6-879e-4e5b-a8e5-40a32d54ac1b
TQID: https://experienceleague.adobe.com/Qb4g-5RXrK42ui4xG86YEv3ozVqmqHrn9Bj5zqXmzPU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: d2311670-43bd-4c2e-bc98-1da2aaba9cefid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 154
ht-degree: 12%

---

# Tipo di browser

La &#39;dimensione tipo browser&#39; [dimensione](overview.md) elenca le organizzazioni che hanno creato il browser utilizzato dal visitatore. Questa dimensione è utile quando desideri vedere quali browser generali utilizzano i visitatori. Fornisce valore sulla dimensione &quot;Browser&quot; in quanto non elenca diverse versioni dello stesso browser come elementi dimensionali separati.

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento a una tabella di ricerca interna ad Adobe. Il valore di ricerca si basa sull&#39;intestazione HTTP `User-Agent` nelle richieste di immagini. Adobe collabora con [DeviceAtlas](https://deviceatlas.com/) per mantenere le ricerche tra l&#39;agente utente e il browser.

* Per le implementazioni di AppMeasurement, questa dimensione funziona in modo predefinito.
* Per le implementazioni di Web SDK, abilita [!UICONTROL Device Lookup] quando [si configura uno stream di dati](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=it).

## Elementi dimensionali

Gli elementi di Dimension includono le organizzazioni che creano browser. Gli elementi dimensionali comuni includono `"Google"` (i creatori di [!DNL Chrome]), `"Apple"` (i creatori di [!DNL Safari]), `"Microsoft"` (i creatori di [!DNL Edge]) e `"Mozilla"` (i creatori di [!DNL Firefox]).
