---
title: Dimensioni principali dei servizi di contenuti multimediali in streaming
description: Dimensioni disponibili quando si abilita [!UICONTROL Media Core] per una suite di rapporti.
feature: Dimensions
exl-id: 1316a646-a31a-49a4-a670-d56d90dd462b
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 9%

---

# Dimensioni principali dei servizi di contenuti multimediali in streaming

*In questa pagina sono descritte le dimensioni disponibili quando si abilita [!UICONTROL Media Core] per una suite di rapporti. Per informazioni sulle metriche disponibili, vedere [Metriche di base di Streaming Media Services](../metrics/sm-core.md).*

Le dimensioni principali dei servizi di contenuti multimediali in streaming forniscono funzionalità di reporting di base ai dati raccolti tramite le librerie dei servizi di contenuti multimediali in streaming. L&#39;utilizzo di queste dimensioni richiede **[!UICONTROL Adobe Analytics for Streaming Media Ad-on]**. Per informazioni, contatta il team del tuo account di Adobe.

Quando abiliti **[!UICONTROL Media Core]** in [Generazione rapporti multimediali](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), sono disponibili le seguenti dimensioni:

| Nome dimensione | Descrizione | Inviato con | Variabile dati contestuali |
| --- | --- | --- | --- |
| Contenuto | ID contenuto. | Avvio file multimediale, Chiusura file multimediale | `a.media.name` |
| Canale del contenuto | La stazione di distribuzione o il canale in cui viene riprodotto il contenuto. Qualsiasi valore stringa è valido. | Avvio file multimediale, Chiusura file multimediale | `a.media.channel` |
| Lunghezza del contenuto (variabile) | La lunghezza massima (o durata) del contenuto utilizzato, in secondi. Questa dimensione è necessaria per diverse metriche, tra cui &quot;Pubblico medio per minuto&quot;. Se questa dimensione non è impostata, le metriche dipendenti non sono disponibili.<br><br>È disponibile anche una dimensione di classificazione denominata &quot;Lunghezza video&quot;, che ha uno scopo simile. Questa dimensione e la classificazione sono trattate come due dimensioni distinte. | Avvio file multimediale, Chiusura file multimediale | `a.media.length` |
| Nome contenuto (variabile) | Il nome descrittivo del contenuto. È disponibile anche una classificazione denominata &quot;Nome video&quot;, che fornisce uno scopo simile. Questa dimensione e la classificazione sono trattate come due dimensioni distinte. | Avvio file multimediale, Chiusura file multimediale | `a.media.friendlyName` |
| Nome del lettore di contenuti | Nome del lettore di contenuti. | Avvio file multimediale, Chiusura file multimediale | `a.media.playerName` |
| Segmento di contenuto | L’intervallo che descrive la parte del contenuto visualizzata, in minuti. Il segmento viene calcolato come valori minimo e massimo della testina di riproduzione durante una sessione di riproduzione. | Chiusura file multimediale | `a.media.segment` |
| Content type (Tipo di contenuto) | Il tipo di contenuto. I valori validi includono `song`, `podcast`, `audiobook`, `radio`, `VoD`, `Live`, `Linear`, `UGC`, `DVoD` o un valore personalizzato. | Avvio file multimediale, Chiusura file multimediale | `a.contentType` |
| Percorso file multimediale | Il percorso seguito dal visitatore per raggiungere il contenuto. | Avvio file multimediale | `a.media.path` |
| Tipo di flusso | Il tipo di flusso. I valori validi includono `audio` e `video`. | Avvio file multimediale, Chiusura file multimediale | `a.media.streamType` |

{style="table-layout:auto"}

Oltre alle dimensioni di cui sopra, Adobe crea automaticamente le seguenti dimensioni di classificazione. Per visualizzare i rapporti che utilizzano queste dimensioni, devi caricare i dati di classificazione.

| Nome classificazione | Dimensione principale | Descrizione |
| --- | --- | --- |
| Lunghezza video | Contenuto | La lunghezza massima (o durata) del contenuto utilizzato, in secondi. Le metriche che dipendono dalla lunghezza del contenuto non possono utilizzare questa classificazione; è necessario creare una metrica calcolata per ottenere metriche quali &quot;Pubblico medio per minuto&quot; utilizzando questa classificazione. |
| Nome del video | Contenuto | Il nome descrittivo del contenuto. È l’equivalente di classificazione del Nome contenuto (variabile). |

{style="table-layout:auto"}
