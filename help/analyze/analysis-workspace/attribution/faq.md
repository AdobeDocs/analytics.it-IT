---
title: Domande Frequenti Sull’Attribuzione
description: Risposte alle domande più frequenti sull’attribuzione.
feature: Attribution
role: User, Admin
exl-id: 8e05957a-f954-4e61-aeed-cd2bd2fe11f8
source-git-commit: 35f2812c1a1a4eed090e04d67014fcebf88a80ec
workflow-type: tm+mt
source-wordcount: '1179'
ht-degree: 85%

---

# Domande frequenti

Di seguito sono riportate le risposte alle domande più frequenti sull’attribuzione.

+++## Qual è l&#39;elemento riga **[!UICONTROL None]** quando si utilizza l&#39;attribuzione?

“None” è un elemento catch-all che rappresenta tutte le conversioni avvenute senza punti di contatto all’interno dell’intervallo di lookback. Per ridurre il numero di conversioni attribuite alla riga &quot;None&quot;, prova a utilizzare un intervallo di lookback personalizzato con un periodo di lookback più lungo.

+++


+++## Perché talvolta visualizzo date al di fuori della mia finestra di reporting quando utilizzo modelli di attribuzione?

Alcune metriche basate sulle visite, come [Voci](/help/components/metrics/entries.md) o [Percentuale non recapitate](/help/components/metrics/bounce-rate.md), possono attribuire i dati a un periodo prima dell’intervallo di date di inizio della finestra di generazione rapporti. Questa situazione è dovuta ai modelli di attribuzione che utilizzano una finestra di lookback, che determina il periodo di tempo precedente da considerare per l’attribuzione del credito alle metriche. Lo scenario più comune è quando le visite attraversano la mezzanotte. Ad esempio:

1. Un utente visita la pagina principale alle 23:55 del 7 settembre.
1. Poi visita diverse pagine, l’ultima delle quali alle 00:05 dell’8 settembre.
1. Una settimana dopo, esegui un rapporto del trend giornaliero, con intervallo di date 8 settembre - 14 settembre.

Le metriche basate sugli hit, come [Visualizzazioni pagina](/help/components/metrics/page-views.md), produrrebbero l’output previsto; dati con tendenze giornaliere dall’8 settembre al 14 settembre. Tuttavia, le metriche basate sulle visite mostreranno anche la visita di cui sopra, del 7 settembre. L’entrata attribuita alla visita è avvenuta il 7 settembre e la finestra di lookback per impostazione predefinita è 1 settembre - 31 settembre.

In questo esempio, la Percentuale non recapitate è sempre 0% per il 7 settembre. Questa metrica è definita come `Bounces divided by Entries` ed è una metrica basata sugli hit divisa per una metrica basata sulle visite. I mancati recapiti sono costituiti da una singola richiesta di immagine, per cui non possono estendersi su più giorni. Eventuali mancati recapiti effettuati il 7 settembre si sono verificati oltre la finestra di reporting, causando la percentuale di mancato recapito garantita dello 0% per quel giorno. In questo rapporto, anche altre metriche basate sugli hit mostrerebbero 0 per il 7 settembre, in quanto anche tali hit non si trovano nella finestra di reporting.

Considera un altro esempio simile. L’unica differenza tra l’esempio seguente e quello precedente sono le date:

1. Un utente visita la pagina principale alle 23:55 del 31 agosto.
1. Poi visita diverse pagine, l’ultima delle quali alle 00:05 del 1° settembre.
1. Una settimana dopo, esegui un rapporto delle tendenze giornaliere compreso tra il 1° settembre e il 7 settembre.

In questo esempio, Voci e Percentuale non recapitate non presenterebbero alcun dato del 31 agosto. La finestra di lookback e la finestra di reporting iniziano il 1° settembre, quindi i dati non possono essere attribuiti a partire dal 31 agosto.

+++


<!-- not relevant anymore due to introduction of separation of container and lookback window 
+++## When should I use a visit, visitor, or custom attribution lookback?

The choice of attribution lookback depends on your use case. If conversions typically take longer than a single visit, a visitor or custom lookback is recommended. For longer conversion cycles, custom lookback windows are best as they are the only type that can pull in data from prior to the reporting window.

+++
-->

+++## Come si confrontano proprietà ed eVar quando si utilizza l’attribuzione?

L’attribuzione viene ricalcolata in fase di esecuzione dei report, quindi non c’è differenza tra proprietà e eVar (o qualsiasi altra dimensione) per la modellazione dell’attribuzione. Le proprietà possono persistere utilizzando qualsiasi intervallo di lookback o modello di attribuzione e le impostazioni di allocazione/scadenza eVar vengono ignorate.

+++


I modelli di attribuzione sono disponibili in altre funzionalità di Analytics, ad esempio Feed dati o Data Warehouse?

No. I modelli di attribuzione utilizzano l’elaborazione dei tempi di report, disponibile solo in Analysis Workspace. Per ulteriori informazioni, vedi [Elaborazione dei tempi di report](/help/components/vrs/vrs-report-time-processing.md).

+++


+++## I modelli di attribuzione sono disponibili solo se si utilizza una suite di rapporti virtuali con abilitata l’elaborazione nel momento del report?

I modelli di attribuzione sono disponibili al di fuori delle suite di rapporti virtuali. Sebbene utilizzino l’elaborazione dei tempi di report in back-end, i modelli di attribuzione sono disponibili sia per le suite di rapporti standard che per le suite di rapporti virtuali.

+++


+++## Quali sono le dimensioni e metriche non supportate?

Il pannello di attribuzione supporta tutte le dimensioni. Le metriche non supportate includono:

* Tutte le metriche calcolate
* Visitatori univoci
* Visite
* Occorrenze
* Visualizzazioni pagina
* Metriche A4T
* Metriche Tempo trascorso
* Rimbalzi
* Percentuale mancati recapiti
* Voci
* Uscite
* Pagine non trovate
* Ricerche
* Visite a pagina singola
* Accesso singolo

+++


+++## L’attribuzione funziona con le classificazioni?

Sì, le classificazioni sono completamente supportate.

+++


+++## L’attribuzione funziona con le origini di dati?

Sì, la maggior parte delle origini di dati sono supportate. L’attribuzione non è possibile con origini di dati di livello sintetico perché non si collegano a un identificatore visitatore di Analytics.

Le origini dati ID transazione sono trattate come qualsiasi altro hit. Le origini dati ID transazione non utilizzano l’elaborazione speciale normalmente utilizzata nei rapporti tradizionali. In altre parole, quando si utilizza l’elaborazione al momento del rapporto, gli hit per l’ID transazione presentano valori eVar propagati da hit che si verificano vicino alla marca temporale dell’hit per l’ID transazione. I valori non vengono propagati dagli hit che si sono verificati in prossimità della transazione originale.

Quando possibile, l’attribuzione si basa sul valore della colonna MID inviato all’interno di un evento nell’origine dati, anziché su un valore persistente. Il modello di attribuzione viene applicato durante l’elaborazione ai valori della colonna MID nell’origine dati. Ad esempio, quando utilizzi l&#39;[attribuzione Ultimo contatto](models.md) il modello inizia da ogni istanza di una metrica. E torna indietro sequenzialmente negli hit fino a quando il modello raggiunge l’ultimo valore osservato nella colonna MID.

Quando non è possibile, l&#39;attribuzione utilizza il valore MID nel *record precedente* nell&#39;origine dati per la valutazione. Tale record precedente potrebbe non essere ordinato in sequenza per marca temporale, dato che AA non supporta dati fuori ordine.

Poiché i record non sono ordinati in sequenza, i valori previsti dall’applicazione della persistenza possono influire sul periodo di tempo che intercorre tra la marca temporale dell’ID transazione fornito e la transazione originale.

+++


+++## L’attribuzione funziona con l’integrazione Advertising Analytics?

Le dimensioni dei metadati, come tipo di corrispondenza e parola chiave, funzionano con l’attribuzione. Tuttavia, le metriche (comprese impressioni, costi, clic, posizione media e valutazione della qualità media) utilizzano origini di dati a livello di riepilogo e sono pertanto incompatibili.

+++


+++## Come funziona l’attribuzione con i canali di marketing?

Quando i canali di marketing sono stati introdotti per la prima volta, presentavano solo le dimensioni di primo e ultimo contatto. La versione corrente dell’attribuzione non richiede più dimensioni esplicite di primo/ultimo contatto. Adobe fornisce dimensioni generiche [!UICONTROL Marketing Channel] e [!UICONTROL Marketing Channel Detail] per consentirti di utilizzarle con il modello di attribuzione desiderato. Queste dimensioni generiche si comportano in modo identico alle dimensioni [!UICONTROL Last Touch Channel], ma sono etichettate in modo diverso per evitare confusione quando si utilizzano canali di marketing con un modello di attribuzione diverso.

Poiché le dimensioni del canale di marketing dipendono da una definizione di visita tradizionale (come definita dalle relative regole di elaborazione), la definizione della visita non può essere modificata utilizzando le suite di rapporti virtuali.

+++


+++## In che modo l’attribuzione funziona con variabili con più valori, come le variabili elenco?

Alcune dimensioni in Analytics possono contenere più valori su un singolo hit. Esempi comuni includono le variabili elenco e prodotti.

Quando l’attribuzione viene applicata a hit con più valori, a tutti i valori dello stesso hit viene assegnato lo stesso credito. Poiché il credito può essere assegnato a molti valori, il totale del rapporto può essere diverso da quello di ogni singolo elemento di riga. Il totale del rapporto è deduplicato, mentre ogni singolo elemento di dimensione ottiene il giusto credito.

+++


+++## Come funziona l’attribuzione con la segmentazione?

L’attribuzione viene sempre eseguita prima della segmentazione e la segmentazione viene eseguita prima dell’applicazione dei filtri per la generazione del rapporto. Questo concetto si applica anche alle suite di rapporti virtuali che utilizzano segmenti.

Ad esempio, se crei una suite di rapporti virtuali applicando il segmento “hit di visualizzazione”, potresti vedere altri canali sotto forma di tabella che utilizza alcuni modelli di attribuzione.

![Suite di rapporti virtuali di sola visualizzazione](assets/vrs-aiq-example.png)

>[!NOTE]
>
>Se un segmento sopprime gli hit contenenti la metrica, queste istanze di metrica non sono attribuite ad alcuna dimensione. Tuttavia, un filtro di questo tipo per la generazione di rapporti si limita a nascondere alcuni elementi di dimensione senza alcun impatto sulle metriche elaborate secondo il modello di attribuzione. Di conseguenza, un segmento può restituire valori inferiori rispetto a un filtro con una definizione comparabile.

+++
