---
description: Abilita dimensioni e metriche da utilizzare nel tracciamento delle app mobili.
title: Rapporti sulle app
feature: Admin Tools
exl-id: ec19695a-2961-45e4-bf44-434f0ff9e3c9
TQID: https://experienceleague.adobe.com/oF-tETs2-MWjSLoo5bVUmrr2nS4N1o2shD4DkMDAVLU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7aid: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2id: c77ba355-6681-41fe-b719-563d3f507fdbid: ef60b66e-5984-4336-ba72-6d978b1b6f87id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 385
ht-degree: 3%

---

# Rapporti sulle app

L’interfaccia di App Reporting ti consente di abilitare dimensioni e metriche del ciclo di vita dedicate per l’utilizzo nel tracciamento delle app mobili.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL App Management]** > **[!UICONTROL App Reporting]**

>[!IMPORTANT]
>
>Una volta attivate, queste funzioni non possono essere disattivate. L’abilitazione di una determinata funzione rende le relative dimensioni e metriche definitivamente disponibili in Analysis Workspace.

## [!UICONTROL App Reports]

Le dimensioni e le metriche di [!UICONTROL App Reports] vengono utilizzate per le seguenti finalità:

* **Acquisizione**: tieni traccia degli URL di riferimento per le campagne di download di app.
* **Ciclo di vita**: livello base di reporting fornito dalla misurazione inviata a ogni avvio dell&#39;app.
* **Azioni app**: report e percorsi basati sulle azioni in-app.
* **Valore del ciclo di vita**: scopri in che modo gli utenti maturano valore nel tempo utilizzando i KPI dell&#39;app (come acquisti, visualizzazioni di annunci pubblicitari, riproduzioni video completate, condivisioni social, caricamenti di foto).
* **Eventi temporizzati**: misura quanto tempo (in-app e totale) intercorre tra le azioni in-app principali, ad esempio il tempo che precede il primo acquisto.

Quando abiliti [!UICONTROL App Reports], sono disponibili le seguenti dimensioni:

* [!UICONTROL Action Name] (con [Entry](/help/components/dimensions/entry-dimensions.md) e [Exit](/help/components/dimensions/exit-dimensions.md) dimensioni)
* [!UICONTROL App Id]
* [!UICONTROL Acquisition Content]
* [!UICONTROL Acquisition Medium]
* [!UICONTROL Acquisition Name]
* [!UICONTROL Acquisition Source]
* [!UICONTROL Acquisition Term]
* [!UICONTROL Day of Week (SDK)]
* [!UICONTROL Days Since First Use]
* [!UICONTROL Days Since Last Use]
* [!UICONTROL Device Name (SDK)]
* [!UICONTROL Hour of Day (SDK)]
* [!UICONTROL First Launch Date]
* [!UICONTROL Launch Number]
* [!UICONTROL Lifetime Value (evar)]
* [!UICONTROL Operating System Version (SDK)]
* [!UICONTROL Resolution (SDK)]

Sono disponibili le seguenti metriche:

* [!UICONTROL Action Time In App]
* [!UICONTROL Action Time Total]
* [!UICONTROL Crashes]
* [!UICONTROL First Launches]
* [!UICONTROL Launches]
* [!UICONTROL Lifetime Value (event)]
* [!UICONTROL Total Session Length]
* [!UICONTROL Upgrades]

## [!UICONTROL Location Tracking]

Le dimensioni [!UICONTROL Location Tracking] vengono utilizzate per i seguenti scopi:

* Tracciamento dei dati di latitudine e longitudine
* Identifica, crea e visualizza punti di interesse specifici. I punti di interesse devono essere definiti nel file di configurazione del SDK per dispositivi mobili.
* Tracciare i beacon Bluetooth (UUID, principale, secondario e prossimità).

Quando abiliti [!UICONTROL Location Tracking], sono disponibili le seguenti dimensioni:

* [!UICONTROL Beacon Major] (con [Entry](/help/components/dimensions/entry-dimensions.md) e [Exit](/help/components/dimensions/exit-dimensions.md) dimensioni)
* [!UICONTROL Beacon Minor] (con [Entry](/help/components/dimensions/entry-dimensions.md) e [Exit](/help/components/dimensions/exit-dimensions.md) dimensioni)
* [!UICONTROL Beacon Proximity] (con [Entry](/help/components/dimensions/entry-dimensions.md) e [Exit](/help/components/dimensions/exit-dimensions.md) dimensioni)
* [!UICONTROL Beacon UUID] (con [Entry](/help/components/dimensions/entry-dimensions.md) e [Exit](/help/components/dimensions/exit-dimensions.md) dimensioni)
* [!UICONTROL Location (down to 10 km)]
* [!UICONTROL Location (down to 100 m)]
* [!UICONTROL Location (down to 1 m)]
* [!UICONTROL Point of Interest Name]
* [!UICONTROL Distance to Point of Interest Center]
* [!UICONTROL Point of Interest ID]

## [!UICONTROL Voice and Chatbots]

Le dimensioni e le metriche di [!UICONTROL Voice and Chatbots] consentono di misurare gli assistenti vocali come Alexa o Google Home. Consente inoltre di misurare i bot di chat cresciuti in casa. Le proprietà di misurazione includono:

* **Ciclo di vita**: livello base di reporting per qualsiasi app, ad esempio il numero di avvii e il tipo di piattaforma.
* **Conversazioni**: misura gli intenti, le risposte e altre metriche e dimensioni correlate alla conversazione.

Quando abiliti [!UICONTROL Voice and Chatbots], sono disponibili le seguenti dimensioni:

* [!UICONTROL Voice Device Capabilities] (con [Entry](/help/components/dimensions/entry-dimensions.md) e [Exit](/help/components/dimensions/exit-dimensions.md) dimensioni)
* [!UICONTROL Voice Authentication]
* [!UICONTROL Voice Error Type]
* [!UICONTROL Voice Intent]
* [!UICONTROL Voice App Response]
* [!UICONTROL Voice Language]

Sono disponibili le seguenti metriche:

* [!UICONTROL Voice End Session]
* [!UICONTROL Voice Error]
* [!UICONTROL Voice Utterances]

## Reporting e attribuzione legacy per hit in background

I rapporti legacy indicano che gli hit generati quando un’app è in background vengono trattati come normali hit in primo piano. Vengono visualizzati nei rapporti e influiscono sull’attribuzione. Questa configurazione legacy è in genere utile per mantenere la coerenza con le implementazioni legacy.

Adobe consiglia di disabilitare la generazione rapporti legacy in modo che gli hit in background non siano visibili. Se desideri includere gli hit in background nell&#39;analisi, puoi abilitare l&#39;impostazione **[!UICONTROL Include background hits]** della [Suite di rapporti virtuale](/help/components/vrs/vrs-about.md).
