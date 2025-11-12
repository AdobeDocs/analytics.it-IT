---
title: Metriche principali dei servizi di contenuti multimediali in streaming
description: Metriche disponibili quando abiliti [!UICONTROL Media Core] per una suite di rapporti.
feature: Metrics
exl-id: f4ff5f84-18b6-4e67-b808-133faeaf8605
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 1%

---

# Metriche principali dei servizi di contenuti multimediali in streaming

*In questa pagina sono descritte le metriche disponibili quando si abilita [!UICONTROL Media Core] per una suite di rapporti. Per informazioni sulle dimensioni disponibili, vedere [Dimensioni principali dei servizi multimediali in streaming](../dimensions/sm-core.md).*

Le metriche di base dei servizi multimediali di streaming forniscono funzionalità di reporting di base ai dati raccolti tramite le librerie di raccolta dei servizi multimediali di streaming. L&#39;utilizzo di queste metriche richiede **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Per informazioni, contatta il team del tuo account di Adobe.

Quando abiliti **[!UICONTROL Media Core]** in [Report multimediali](/help/admin/tools/manage-rs/edit-settings/media-management.md), sono disponibili le metriche seguenti:

| Nome della metrica | Descrizione | Inviato con | Variabile dati contestuali | Campo XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Average minute audience]** | La quantità totale di tempo trascorso su un determinato contenuto, divisa per la lunghezza per tutte le sessioni di riproduzione.<br>`[Time spent] / [Media length]` | Chiusura file multimediale | `a.media.`<br>`averageMinuteAudience` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`averageMinuteAudience` |
| **[!UICONTROL Content completes]** | Si attiva quando viene completato un contenuto. Questa metrica non significa necessariamente che visualizzasse l’intero contenuto; potrebbe aver saltato alcune parti. Significa solo che hanno raggiunto la fine del contenuto. | | `a.media.complete` | `xdm.mediaReporting.`<br>`sessionDetails.isCompleted` |
| **[!UICONTROL Paused impacted streams]** | Valore booleano che viene attivato se si sono verificate una o più pause durante la riproduzione del contenuto. | Chiusura file multimediale | `a.media.pause` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`hasPauseImpactedStreams` |
| **[!UICONTROL Pause events]** | Numero di pause che si sono verificate durante una sessione di riproduzione. | Chiusura file multimediale | `a.media.pauseCount` | `xdm.mediaReporting.`<br>`sessionDetails.pauseCount` |
| **[!UICONTROL Total pause duration]** | La durata totale di tutti gli eventi di pausa, in secondi. | Chiusura file multimediale | `a.media.pauseTime` | `xdm.mediaReporting.`<br>`sessionDetails.pauseTime` |
| **[!UICONTROL Content starts]** | Viene utilizzato il primo fotogramma del file multimediale. Se un utente abbandona durante un annuncio o durante il buffering, questo evento non si attiva. | Chiusura file multimediale | `a.media.play` | `xdm.mediaReporting.`<br>`sessionDetails.isPlayed` |
| **[!UICONTROL 10% progress marker]**<br>**[!UICONTROL 25% progress marker]**<br>**[!UICONTROL 50% progress marker]**<br>**[!UICONTROL 75% progress marker]**<br>**[!UICONTROL 95% progress marker]** | L’indicatore di riproduzione passa il marcatore indicato del contenuto in base alla lunghezza. Ogni marcatore viene conteggiato una sola volta, anche se si torna indietro. Se il contenuto viene mandato avanti, i marcatori saltati non vengono conteggiati. | Chiusura file multimediale | `a.media.progress10`<br>`a.media.progress25`<br>`a.media.progress50`<br>`a.media.progress75`<br>`a.media.progress95` | `xdm.mediaReporting.`<br>`sessionDetails.hasProgress10`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress25`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress50`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress75`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress95` |
| **[!UICONTROL Content resumes]** | Valore booleano che viene attivato quando il contenuto viene ripreso dopo più di 30 minuti di buffer, pausa o periodo di arresto. Viene attivato anche se impostato dal lettore sul trackPlay VideoInfo. | Chiusura file multimediale | `a.media.resume` | `xdm.mediaCollection.`<br>`sessionDetails.hasResume`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasResume` |
| **[!UICONTROL Content segment views]** | Valore booleano che viene attivato sul primo fotogramma del segmento visualizzato. | Chiusura file multimediale | `a.media.segmentView` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`hasSegmentView` |
| **[!UICONTROL Media starts]** | Valore booleano che viene attivato all’avvio del caricamento del file multimediale. Questo evento include annunci, buffering ed errori. | Avvio file multimediale | `a.media.view` | `xdm.mediaReporting.`<br>`sessionDetails.isViewed` |
| **[!UICONTROL Content time spent]** | La durata totale dell’evento per tutti gli eventi di tipo PLAY sul contenuto principale, in secondi. | Chiusura file multimediale | `a.media.timePlayed` | `xdm.mediaReporting.`<br>`sessionDetails.timePlayed` |
| **[!UICONTROL Unique time played]** | Il tempo totale di riproduzione di contenuti univoci, in secondi. Questa metrica esclude il tempo di riproduzione durante la visualizzazione del contenuto ripetuto, ad esempio la ricerca all’indietro. | Chiusura file multimediale | `a.media.`<br>`uniqueTimePlayed` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`uniqueTimePlayed` |
