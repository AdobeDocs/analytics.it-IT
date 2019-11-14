---
title: Domande frequenti sull'attribuzione
description: Risposte alle domande più frequenti sull'attribuzione.
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Domande frequenti sull'attribuzione

**Qual è l'elemento di riga "None" quando si utilizza l'attribuzione?**

L'elemento di riga 'None' è un elemento catch-all che rappresenta tutte le conversioni che si sono verificate senza punti di contatto all'interno della finestra di lookback. Prova a includere un intervallo di tempo più lungo nella finestra di reporting.

**Perché talvolta si visualizzano date al di fuori della finestra di reporting quando si utilizzano modelli di attribuzione?**

Queste date aggiuntive sono dovute alla finestra di lookback del rapporto sui visitatori. Per ulteriori informazioni, vedi [Dati visualizzati all'esterno della finestra](https://helpx.adobe.com/analytics/kb/data-appearing-outside-reporting-window.html) del rapporto nella KB di Analytics. Adobe pianifica di filtrare queste righe in una prossima release.

**Posso utilizzare una finestra di lookback personalizzata con i miei modelli di attribuzione?**

I modelli di attribuzione si basano attualmente su una finestra di lookback di un visitatore o di una visita. Una di queste finestre di lookback può essere regolata modificando l'intervallo di date del rapporto (per il lookback del visitatore) o utilizzando una definizione di visita personalizzata come parte delle suite di rapporti virtuali. Per ulteriori informazioni, consulta [Elaborazione](../../../../components/vrs/vrs-report-time-processing.md) del tempo del rapporto.

**Quando dovrei usare un lookback di attribuzione visita e attribuzione visitatore?**

La scelta del lookback di attribuzione dipende dal caso di utilizzo. Se le conversioni in genere richiedono più tempo di una singola visita, si consiglia di effettuare un lookback del visitatore. La creazione di una suite di rapporti virtuale con una definizione di visita più lunga è anche una soluzione potenziale.

**Come si confrontano proprietà ed eVar quando si utilizza l'attribuzione?**

L'attribuzione viene ricalcolata in fase di esecuzione dei report, quindi non c'è differenza tra una prop o eVar (o qualsiasi altra dimensione) per la modellazione dell'attribuzione. Le proprietà possono persistere utilizzando qualsiasi finestra di lookback o modello di attribuzione e le impostazioni di allocazione/scadenza eVar vengono ignorate.

**I modelli di attribuzione sono disponibili in altre funzionalità di Analytics, ad esempio feed di dati o Data Warehouse?**

No. I modelli di attribuzione utilizzano l’elaborazione del tempo del rapporto, disponibile solo in Analysis Workspace. Per ulteriori informazioni, consulta [Elaborazione](../../../../components/vrs/vrs-report-time-processing.md) del tempo del rapporto.

**I modelli di attribuzione sono disponibili solo se uso una suite di rapporti virtuali con l'elaborazione dell'ora del rapporto abilitata?**

I modelli di attribuzione sono disponibili al di fuori delle suite di rapporti virtuali. Mentre utilizzano l’elaborazione del tempo del rapporto sul backend, i modelli di attribuzione sono disponibili sia per le suite di rapporti standard che per le suite di rapporti virtuali.

**Quali dimensioni e metriche non sono supportate?**

Il pannello di attribuzione supporta tutte le dimensioni. Le metriche non supportate includono:

* Visitatori unici
* Visite
* Occorrenze
* Visualizzazioni pagina
* Metriche A4T
* Metriche Tempo trascorso
* Bounce
* Percentuale non recapitate
* Voci
* Uscite
* Pagine non trovate
* Ricerche
* Visite a pagina singola
* Accesso singolo

**In che modo l’attribuzione in Analysis Workspace differisce dall’attribuzione in Workbench dati?**

Workbench dati offre in modo incrementale:

* La capacità di assegnare l’attribuzione per più sorgenti dati per visitatore, ad esempio impression di annunci e punto vendita.
* Modellazione algoritmica. L’attribuzione in Analysis Workspace include solo modelli basati su regole. Vedere [Modellazione](https://marketing.adobe.com/resources/help/en_US/insight/client/c_attrib_algorithmic.html) di adattamento ottimale nella guida utente di Workbench dati.
* Visualizzazioni aggiuntive, come ad esempio tabelle di latenza. Vedere Tabelle [di](https://marketing.adobe.com/resources/help/en_US/insight/client/c_lat_tbls.html) latenza nella guida utente di Workbench dati.

**L'attribuzione funziona con le classificazioni?**

Sì, le classificazioni sono completamente supportate.

**L'attribuzione funziona con le origini dati?**

Sì, la maggior parte delle origini dati sono supportate. L’attribuzione non è possibile con origini dati di livello sintetico perché non si collegano a un identificatore visitatore di Analytics. Sono inoltre supportate le origini dati ID transazione, a meno che non siano utilizzate in una suite di rapporti virtuale con l'elaborazione dell'ora del rapporto abilitata.

**L'attribuzione funziona con l'integrazione di Advertising Analytics?**

Le dimensioni dei metadati, come tipo di corrispondenza e parola chiave, funzionano con l’attribuzione. Tuttavia, le metriche (comprese impression, costi, clic, posizione media e valutazione della qualità media) utilizzano origini dati a livello di riepilogo e sono pertanto incompatibili.
