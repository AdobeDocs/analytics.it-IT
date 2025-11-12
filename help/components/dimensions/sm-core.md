---
title: Dimensioni principali dei servizi di contenuti multimediali in streaming
description: Dimensioni disponibili quando si abilita [!UICONTROL Media Core] per una suite di rapporti.
feature: Dimensions
exl-id: 1316a646-a31a-49a4-a670-d56d90dd462b
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 7%

---

# Dimensioni principali dei servizi di contenuti multimediali in streaming

*In questa pagina sono descritte le dimensioni disponibili quando si abilita [!UICONTROL Media Core] per una suite di rapporti. Per informazioni sulle metriche disponibili, vedere [Metriche di base di Streaming Media Services](../metrics/sm-core.md).*

Le dimensioni principali dei servizi di contenuti multimediali in streaming forniscono funzionalità di reporting di base ai dati raccolti tramite le librerie dei servizi di contenuti multimediali in streaming. L&#39;utilizzo di queste dimensioni richiede **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Per informazioni, contatta il team del tuo account di Adobe.

Quando abiliti **[!UICONTROL Media Core]** in [Generazione rapporti multimediali](/help/admin/tools/manage-rs/edit-settings/media-management.md), sono disponibili le seguenti dimensioni:

| Nome dimensione | Descrizione | Inviato con | Variabile dati contestuali | Campo XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Content]** | ID contenuto. | Avvio file multimediale, Chiusura file multimediale | `a.media.`<br>`name` | `xdm.mediaCollection.`<br>`sessionDetails.name`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.name` |
| **[!UICONTROL Content channel]** | La stazione di distribuzione o il canale in cui viene riprodotto il contenuto. Qualsiasi valore stringa è valido. | Avvio file multimediale, Chiusura file multimediale | `a.media.`<br>`channel` | `xdm.mediaCollection.`<br>`sessionDetails.channel`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.channel` |
| **[!UICONTROL Content length (variable)]** | La lunghezza massima (o durata) del contenuto utilizzato, in secondi. Questa dimensione è necessaria per diverse metriche, tra cui &#39;[!UICONTROL Average minute audience]&#39;. Se questa dimensione non è impostata, le metriche dipendenti non sono disponibili.<br><br>È disponibile anche una dimensione di classificazione denominata &#39;[!UICONTROL Video length]&#39;, che fornisce uno scopo simile. Questa dimensione e la classificazione sono trattate come due dimensioni distinte. | Avvio file multimediale, Chiusura file multimediale | `a.media.`<br>`length` | `xdm.mediaCollection.`<br>`sessionDetails.length`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.length` |
| **[!UICONTROL Content name (variable)]** | Il nome descrittivo del contenuto. È disponibile anche una classificazione denominata &#39;[!UICONTROL Video name]&#39;, che fornisce uno scopo simile. Questa dimensione e la classificazione sono trattate come due dimensioni distinte. | Avvio file multimediale, Chiusura file multimediale | `a.media.`<br>`friendlyName` | `xdm.mediaCollection.`<br>`sessionDetails.friendlyName`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.friendlyName` |
| **[!UICONTROL Content player name]** | Nome del lettore di contenuti. | Avvio file multimediale, Chiusura file multimediale | `a.media.`<br>`playerName` | `xdm.mediaCollection.`<br>`sessionDetails.playerName`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.playerName` |
| **[!UICONTROL Content segment]** | L’intervallo che descrive la parte del contenuto visualizzata, in minuti. Il segmento viene calcolato come valori minimo e massimo della testina di riproduzione durante una sessione di riproduzione. | Chiusura file multimediale | `a.media.`<br>`segment` | `xdm.mediaReporting.`<br>`sessionDetails.segment` |
| **[!UICONTROL Content type]** | Il tipo di contenuto. I valori validi includono `song`, `podcast`, `audiobook`, `radio`, `VoD`, `Live`, `Linear`, `UGC`, `DVoD` o un valore personalizzato. | Avvio file multimediale, Chiusura file multimediale | `a.contentType` | `xdm.mediaCollection.`<br>`sessionDetails.contentType`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.contentType` |
| **[!UICONTROL Media path]** | Il percorso seguito dal visitatore per raggiungere il contenuto. | Avvio file multimediale | `a.media.path` | |
| **[!UICONTROL Stream type]** | Il tipo di flusso. I valori validi includono `audio` e `video`. | Avvio file multimediale, Chiusura file multimediale | `a.media.`<br>`streamType` | `xdm.mediaCollection.`<br>`sessionDetails.streamType`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.streamType` |

Oltre alle dimensioni di cui sopra, Adobe crea automaticamente le seguenti dimensioni di classificazione. Per visualizzare i rapporti che utilizzano queste dimensioni, devi caricare i dati di classificazione.

| Nome classificazione | Dimensione principale | Descrizione |
| --- | --- | --- |
| **[!UICONTROL Video length]** | [!UICONTROL Content] | La lunghezza massima (o durata) del contenuto utilizzato, in secondi. Le metriche che dipendono dalla lunghezza del contenuto non possono utilizzare questa classificazione. È necessario creare una metrica calcolata per ottenere metriche quali &#39;[!UICONTROL Average minute audience]&#39; utilizzando questa classificazione. |
| **[!UICONTROL Video name]** | [!UICONTROL Content] | Il nome descrittivo del contenuto. Equivalente di classificazione di &#39;[!UICONTROL Content name (variable)]&#39;. |
