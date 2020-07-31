---
title: Domande frequenti su Attribution
description: Risposte alle domande più frequenti sull’attribuzione.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 95%

---


# Domande frequenti su Attribution

**Qual è l’elemento di riga “None” quando si utilizza l’attribuzione?**

“None” è un elemento catch-all che rappresenta tutte le conversioni avvenute senza punti di contatto all’interno dell’intervallo di lookback. Per ridurre il numero di conversioni attribuite alla riga “None”, prova a utilizzare un intervallo di lookback personalizzato con un periodo di lookback più lungo.

**Perché talvolta visualizzo date al di fuori del periodo definito per la generazione del rapporto quando utilizzo modelli di attribuzione?**

Queste date aggiuntive sono dovute all’intervallo di lookback inerente al rapporto sui visitatori. Per ulteriori informazioni, vedi [Dati visualizzati all’esterno del periodo definito per la generazione del rapporto](https://helpx.adobe.com/it/analytics/kb/data-appearing-outside-reporting-window.html) nel portale di aiuto di Analytics.

**Quando dovrei usare un lookback di attribuzione basato su visita, visitatore o personalizzato?**

La scelta del lookback di attribuzione dipende dal caso di utilizzo. Se le conversioni in genere richiedono più tempo di una singola visita, si consiglia di effettuare un lookback su visitatore o personalizzato. Per cicli di conversione più lunghi, è consigliabile utilizzare intervalli di lookback personalizzati, in quanto sono l’unico tipo in grado di estrarre i dati precedenti all’intervallo di reporting

**Come si confrontano proprietà e eVar quando si utilizza l’attribuzione?**

L’attribuzione viene ricalcolata in fase di esecuzione dei report, quindi non c’è differenza tra proprietà e eVar (o qualsiasi altra dimensione) per la modellazione dell’attribuzione. Le proprietà possono persistere utilizzando qualsiasi intervallo di lookback o modello di attribuzione e le impostazioni di allocazione/scadenza eVar vengono ignorate.

**I modelli di attribuzione sono disponibili in altre funzionalità di Analytics, ad esempio Feed dati o Data Warehouse?**

No. I modelli di attribuzione utilizzano l’elaborazione dei tempi di report, disponibile solo in Analysis Workspace. Per ulteriori informazioni, vedi [Elaborazione dei tempi di report](/help/components/vrs/vrs-report-time-processing.md).

**I modelli di attribuzione sono disponibili solo se si utilizza una suite di rapporti virtuali ed è abilitata l’elaborazione dei tempi di report?**

I modelli di attribuzione sono disponibili al di fuori delle suite di rapporti virtuali. Sebbene utilizzino l’elaborazione dei tempi di report in back-end, i modelli di attribuzione sono disponibili sia per le suite di rapporti standard che per le suite di rapporti virtuali.

**Quali sono le dimensioni e metriche non supportate?**

Il pannello di attribuzione supporta tutte le dimensioni. Le metriche non supportate includono:

* Visitatori unici
* Visite
* Occorrenze
* Visualizzazioni pagina
* Metriche A4T
* Metriche Tempo trascorso
* Rimbalzi
* Percentuale non recapitate
* Voci
* Uscite
* Pagine non trovate
* Ricerche
* Visite a pagina singola
* Accesso singolo

**L’attribuzione funziona con le classificazioni?**

Sì, le classificazioni sono completamente supportate.

**L’attribuzione funziona con origini di dati?**

Sì, la maggior parte delle origini di dati sono supportate. L’attribuzione non è possibile con origini di dati di livello sintetico perché non si collegano a un identificatore visitatore di Analytics. Sono supportate anche le origini di dati per ID transazione, a meno che sia utilizzata una suite di rapporti virtuali e che sia selezionata l’elaborazione dei tempi di report.

**L’attribuzione funziona con l’integrazione Advertising Analytics?**

Le dimensioni dei metadati, come tipo di corrispondenza e parola chiave, funzionano con l’attribuzione. Tuttavia, le metriche (comprese impressioni, costi, clic, posizione media e valutazione della qualità media) utilizzano origini di dati a livello di riepilogo e sono pertanto incompatibili.

**Come funziona l’attribuzione con i canali di marketing?**

Quando i canali di marketing sono stati introdotti per la prima volta, presentavano solo le dimensioni di primo e ultimo contatto. La versione corrente dell’attribuzione non richiede più dimensioni esplicite di primo/ultimo contatto. Adobe fornisce dimensioni generiche “Marketing Channel” e “Marketing Channel Detail” per consentirti di utilizzarle con il modello di attribuzione desiderato. Queste dimensioni generiche si comportano in modo identico alle dimensioni Last Touch Channel, ma sono etichettate in modo diverso per evitare confusione quando si utilizzano canali di marketing con un modello di attribuzione diverso.

Poiché le dimensioni del canale di marketing dipendono da una definizione di visita tradizionale (come definita dalle relative regole di elaborazione), la definizione della visita non può essere modificata utilizzando le suite di rapporti virtuali.

**In che modo l’attribuzione funziona con variabili con più valori, come le variabili elenco?**

Alcune dimensioni in Analytics possono contenere più valori su un singolo hit. Esempi comuni includono le variabili elenco e prodotti.

Quando l’attribuzione viene applicata a hit con più valori, a tutti i valori dello stesso hit viene assegnato lo stesso credito. Poiché il credito può essere assegnato a molti valori, il totale del rapporto può essere diverso da quello di ogni singolo elemento di riga. Il totale del rapporto è deduplicato, mentre ogni singolo elemento dimensione riceve il credito appropriato.

**Come funziona l’attribuzione con la segmentazione?**

L’attribuzione viene sempre eseguita prima della segmentazione e la segmentazione viene eseguita prima dell’applicazione dei filtri per la generazione del rapporto. Questo concetto si applica anche alle suite di rapporti virtuali che utilizzano segmenti.

Ad esempio, se crei una suite di rapporti virtuali applicando il segmento “hit di visualizzazione”, potresti vedere altri canali sotto forma di tabella utilizzando alcuni modelli di attribuzione.

![Suite di rapporti virtuali di sola visualizzazione](assets/vrs-aiq-example.png)

>[!NOTE]
>
>Se un segmento sopprime gli hit contenenti la metrica, queste istanze di metrica non saranno attribuite ad alcuna dimensione. Tuttavia, un filtro di report simile nasconderà semplicemente alcuni elementi dimensionali, senza alcun impatto sulle metriche elaborate per il modello di attribuzione. Di conseguenza, un segmento può restituire valori inferiori rispetto a un filtro con una definizione comparabile.
