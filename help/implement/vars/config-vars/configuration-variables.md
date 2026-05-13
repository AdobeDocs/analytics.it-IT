---
title: Variabili di configurazione
description: Utilizza le variabili di configurazione per determinare come vengono raccolti i dati.
feature: Appmeasurement Implementation
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
role: Admin, Developer
TQID: https://experienceleague.adobe.com/amtLWIgyADqWBOv38xdJ6AF4IjhJ0aGVrvYqXLckfkI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c069c44e-5426-4c1a-accc-8028662f2fdeid: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 124
ht-degree: 19%

---

# Panoramica delle variabili di configurazione

Le variabili di configurazione controllano il modo in cui i dati vengono acquisiti ed elaborati nei rapporti. In genere non contengono valori di dimensioni o metriche.

## Impostazione delle variabili di configurazione

Nelle implementazioni che utilizzano l’estensione Web SDK o Analytics, le variabili di configurazione si trovano in genere nelle impostazioni dell’estensione:

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Fare clic sulla scheda [!UICONTROL Extensions], quindi su [!UICONTROL Configure] sotto l&#39;estensione.

Nelle implementazioni di JavaScript che utilizzano `AppMeasurement.js`, le variabili di configurazione vengono in genere impostate nella parte superiore del file JS.

>[!IMPORTANT]
>
>Assicurarsi che tutte le variabili di configurazione siano impostate prima di chiamare un metodo di tracciamento ([`t()`](../functions/t-method.md) o [`tl()`](../functions/tl-method.md)). Evitare di impostare le variabili di configurazione nella funzione [`doPlugins()`](../functions/doplugins.md).
