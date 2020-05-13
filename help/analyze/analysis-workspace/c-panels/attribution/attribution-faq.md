---
title: Domande frequenti su Attribution
description: Risposte alle domande più frequenti sull’attribuzione.
translation-type: tm+mt
source-git-commit: 06b9ac8ddbfb0398341a2ab5656237e3520a8612
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 88%

---


# Domande frequenti su Attribution

**Qual è l’elemento di riga “None” quando si utilizza l’attribuzione?**

L&#39;elemento di riga &#39;None&#39; è un elemento catch-all che rappresenta tutte le conversioni avvenute senza punti di contatto all&#39;interno della finestra di lookback. Prova a includere un intervallo di tempo più lungo nel periodo definito per la generazione del rapporto.

**Perché talvolta visualizzo date al di fuori del periodo definito per la generazione del rapporto quando utilizzo modelli di attribuzione?**

Queste date aggiuntive sono dovute all’intervallo di lookback inerente al rapporto sui visitatori. Per ulteriori informazioni, vedi [Dati visualizzati all’esterno del periodo definito per la generazione del rapporto](https://helpx.adobe.com/it/analytics/kb/data-appearing-outside-reporting-window.html) nel portale di aiuto di Analytics. Adobe prevede di escludere queste righe aggiuntive in una delle prossime versioni.

**Quando dovrei usare un lookback di attribuzione basato su visita o visitatore?**

La scelta del lookback di attribuzione dipende dal caso di utilizzo. Se le conversioni in genere richiedono più tempo di una singola visita, si consiglia di effettuare un lookback su visitatore. Inoltre, la creazione di una suite di rapporti virtuale con una definizione di visita più lunga rappresenta una soluzione potenziale.

**Come si confrontano proprietà e eVar quando si utilizza l’attribuzione?**

L’attribuzione viene ricalcolata in fase di esecuzione dei report, quindi non c’è differenza tra proprietà e eVar (o qualsiasi altra dimensione) per la modellazione dell’attribuzione. Le proprietà possono persistere utilizzando qualsiasi intervallo di lookback o modello di attribuzione e le impostazioni di allocazione/scadenza eVar vengono ignorate.

**I modelli di attribuzione sono disponibili in altre funzionalità di Analytics, ad esempio Feed dati o Data Warehouse?**

No. I modelli di attribuzione utilizzano l’elaborazione dei tempi di report, disponibile solo in Analysis Workspace. Per ulteriori informazioni, vedi [Elaborazione dei tempi di report](../../../../components/vrs/vrs-report-time-processing.md).

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

**È possibile utilizzare un intervallo di lookback personalizzato con i modelli di attribuzione?**

Sì, utilizzando l&#39;opzione della finestra di lookback personalizzata, le finestre di lookback possono essere configurate in qualsiasi intervallo di date fino a 90 giorni prima della finestra di reporting. Per ulteriori informazioni, vedi [Elaborazione dei tempi di report](https://docs.adobe.com/content/help/en/analytics/components/virtual-report-suites/vrs-report-time-processing.html).

**L’attribuzione funziona con le classificazioni?**

Sì, le classificazioni sono completamente supportate.

**L’attribuzione funziona con origini di dati?**

Sì, la maggior parte delle origini di dati sono supportate. L’attribuzione non è possibile con origini di dati di livello sintetico perché non si collegano a un identificatore visitatore di Analytics. Sono supportate anche le origini di dati per ID transazione, a meno che sia utilizzata una suite di rapporti virtuali e che sia selezionata l’elaborazione dei tempi di report.

**L’attribuzione funziona con l’integrazione Advertising Analytics?**

Le dimensioni dei metadati, come tipo di corrispondenza e parola chiave, funzionano con l’attribuzione. Tuttavia, le metriche (comprese impressioni, costi, clic, posizione media e valutazione della qualità media) utilizzano origini di dati a livello di riepilogo e sono pertanto incompatibili.
