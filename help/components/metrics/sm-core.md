---
title: Metriche principali dei servizi di contenuti multimediali in streaming
description: Metriche disponibili quando abiliti [!UICONTROL Media Core] per una suite di rapporti.
feature: Metrics
exl-id: f4ff5f84-18b6-4e67-b808-133faeaf8605
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 1%

---

# Metriche principali dei servizi di contenuti multimediali in streaming

*In questa pagina sono descritte le metriche disponibili quando si abilita [!UICONTROL Media Core] per una suite di rapporti. Per informazioni sulle dimensioni disponibili, vedere [Dimensioni principali dei servizi multimediali in streaming](../dimensions/sm-core.md).*

Le metriche di base dei servizi multimediali di streaming forniscono funzionalità di reporting di base ai dati raccolti tramite le librerie di raccolta dei servizi multimediali di streaming. L&#39;utilizzo di queste metriche richiede **[!UICONTROL Adobe Analytics for Streaming Media Ad-on]**. Per informazioni, contatta il team del tuo account di Adobe.

Quando abiliti **[!UICONTROL Media Core]** in [Report multimediali](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), sono disponibili le metriche seguenti:

| Nome della metrica | Descrizione | Inviato con | Variabile dati contestuali |
| --- | --- | --- | --- |
| Pubblico medio per minuto | La quantità totale di tempo trascorso su un determinato contenuto, divisa per la lunghezza per tutte le sessioni di riproduzione.<br>`[Time spent] / [Media length]` | Chiusura file multimediale | `a.media.averageMinuteAudience` |
| Completamenti contenuto | Si attiva quando viene completato un contenuto. Questa metrica non significa necessariamente che visualizzasse l’intero contenuto; potrebbe aver saltato alcune parti. Significa solo che hanno raggiunto la fine del contenuto. | `a.media.complete` |
| Flussi interessati in pausa | Valore booleano che viene attivato se si sono verificate una o più pause durante la riproduzione del contenuto. | Chiusura file multimediale | `a.media.pause` |
| Eventi di pausa | Numero di pause che si sono verificate durante una sessione di riproduzione. | Chiusura file multimediale | `a.media.pauseCount` |
| Durata totale pausa | La durata totale di tutti gli eventi di pausa, in secondi. | Chiusura file multimediale | `a.media.pauseTime` |
| Inizio contenuto | Viene utilizzato il primo fotogramma del file multimediale. Se un utente abbandona durante un annuncio o durante il buffering, questo evento non si attiva. | Chiusura file multimediale | `a.media.play` |
| Indicatore di avanzamento al 10% | L&#39;indicatore di riproduzione supera il 10% dell’indicatore del contenuto in base alla lunghezza. Questo marcatore viene conteggiato una sola volta, anche se si torna indietro. Se il contenuto viene mandato avanti, i marcatori saltati non vengono conteggiati. | Chiusura file multimediale | `a.media.progress10` |
| Indicatore di progresso del 25% | L&#39;indicatore di riproduzione supera il 25% dell’indicatore del contenuto in base alla lunghezza. Questo marcatore viene conteggiato una sola volta, anche se si torna indietro. Se il contenuto viene mandato avanti, i marcatori saltati non vengono conteggiati. | Chiusura file multimediale | `a.media.progress25` |
| Indicatore di progresso del 50% | L&#39;indicatore di riproduzione supera il 50% dell’indicatore del contenuto in base alla lunghezza. Questo marcatore viene conteggiato una sola volta, anche se si torna indietro. Se il contenuto viene mandato avanti, i marcatori saltati non vengono conteggiati. | Chiusura file multimediale | `a.media.progress50` |
| Indicatore di progresso del 75% | L&#39;indicatore di riproduzione supera il 75% dell’indicatore del contenuto in base alla lunghezza. Questo marcatore viene conteggiato una sola volta, anche se si torna indietro. Se il contenuto viene mandato avanti, i marcatori saltati non vengono conteggiati. | Chiusura file multimediale | `a.media.progress75` |
| Indicatore di progresso del 95% | L&#39;indicatore di riproduzione supera il 95% dell’indicatore del contenuto in base alla lunghezza. Questo marcatore viene conteggiato una sola volta, anche se si torna indietro. Se il contenuto viene mandato avanti, i marcatori saltati non vengono conteggiati. | Chiusura file multimediale | `a.media.progress95` |
| Riprende il contenuto | Valore booleano che viene attivato quando il contenuto viene ripreso dopo più di 30 minuti di buffer, pausa o periodo di arresto. Viene attivato anche se impostato dal lettore sul trackPlay VideoInfo. | Chiusura file multimediale | `a.media.resume` |
| Visualizzazioni del segmento di contenuto | Valore booleano che viene attivato sul primo fotogramma del segmento visualizzato. | Chiusura file multimediale | `a.media.segmentView` |
| Avvio file multimediale | Valore booleano che viene attivato all’avvio del caricamento del file multimediale. Questo evento include annunci, buffering ed errori. | Avvio file multimediale | `a.media.view` |
| Tempo trascorso dei contenuti | La durata totale dell’evento per tutti gli eventi di tipo PLAY sul contenuto principale, in secondi. | Chiusura file multimediale | `a.media.timePlayed` |
| Tempo di riproduzione univoco | Il tempo totale di riproduzione di contenuti univoci, in secondi. Questa metrica esclude il tempo di riproduzione durante la visualizzazione del contenuto ripetuto, ad esempio la ricerca all’indietro. | Chiusura file multimediale | `a.media.uniqueTimePlayed` |

{style="table-layout:auto"}
