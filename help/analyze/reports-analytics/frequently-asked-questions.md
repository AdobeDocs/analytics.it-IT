---
description: Fornisce risposte e risoluzione di problemi ad alcune delle domande più frequenti di Analytics.
keywords: Risoluzione dei problemi Analytics
seo-description: Fornisce risposte e risoluzione di problemi ad alcune delle domande più frequenti di Analytics.
seo-title: Domande frequenti
title: Domande frequenti
uuid: 285 b 0 ea 4-aa 07-4 d 39-a 74 f -37 b 1 d 02 d 19 f 1
translation-type: tm+mt
source-git-commit: fd1e2f1789ed9c8c31c89f0e7b6b7b2dd3ee114d

---


# Domande frequenti

Fornisce risposte e risoluzione di problemi ad alcune delle domande di Analytics più frequenti per Reporting e analisi. For frequently asked implementation questions, see the [FAQ](../../implement/faq.md) in the Implement user guide.

**Il mio account è stato bloccato; how do I unlock it?**

Per riattivare un account, contatta un amministratore all'interno dell'organizzazione. See also [Troubleshoot login issues with Adobe Analytics](../../technotes/troubleshoot-login.md) in the Technotes user guide.

**Perché visualizzi un rapporto vuoto anche se so che i dati vengono raccolti?**

Esistono diversi elementi da controllare per risolvere i problemi dei rapporti:

* Controlla le metriche utilizzate: Alcuni report predefiniti sulle Entrate in Reporting e analisi. Assicurati che la metrica che stai visualizzando sia pertinente al rapporto.
* Controlla l'intervallo di date: Gli intervalli di date, soprattutto quelli oltre i criteri di conservazione dei dati aziendali, non possono restituire dati. Verificate che l'intervallo di date sia impostato correttamente.
* Controlla filtri URL interni: Alcuni rapporti di origini traffico non funzionano finché non definiti correttamente i filtri URL interni.

**Perché mancano alcuni rapporti nel menu di navigazione?**

Tutti i report mancanti da un menu sono generalmente originati da autorizzazioni limitate o personalizzazione del menu. Contatta un amministratore di prodotto all'interno della tua organizzazione per verificare di avere accesso a tutte le dimensioni e le metriche necessarie e che la struttura del menu di una suite di rapporti non sia stata personalizzata.

**Perché vengono tagliati alcuni valori lunghi?**

Quasi tutte le variabili in Adobe Analytics hanno un limite di caratteri. Il nome della pagina ha un limite di 100 caratteri, mentre le variabili di conversione personalizzate (evar) hanno un limite di 255 caratteri. Adobe consiglia di garantire che i valori inviati ad Adobe siano concisi per impedire il troncamento.

**Perché trovo un ritardo importante nei rapporti?**

La generazione di rapporti in tempo reale consente di rendere disponibili alcune metriche di traffico entro pochi minuti, mentre la conversione e altri dati ricchi di elaborazione sono generalmente disponibili entro 30-90 minuti. Sebbene la piattaforma Experience Cloud sia affidabile, alcune situazioni potrebbero causare ritardi nei report. Questo ritardo è denominato latenza. See [Latency](../../technotes/latency.md) in the Technotes user guide for more information.

**Perché non riesco a visualizzare la versione del dispositivo sugli iphone?**

I dispositivi Apple segnalano la versione del firmware nella stringa agente utente, non la versione del dispositivo. È difficile determinare la versione del dispositivo iphone utilizzando le informazioni disponibili per Adobe Analytics. See [Comparing iPhone device versions](https://helpx.adobe.com/analytics/kb/comparing-iphone-device-versions.html) in the Analytics KB for more information.

**Perché i totali nella parte inferiore del report non corrispondono quando si somma i valori?**

I valori Dimensione possono spesso essere applicati in più posizioni, ad esempio, visite che si estendono su mezzanotte o più prodotti appartenenti a un unico ordine. Il valore della dimensione viene riportato in tutte le righe applicabili, ma viene deduplicato nel totale del report. See [Compare sum of line items to report total](https://helpx.adobe.com/analytics/kb/sum-line-items-different-from-total.html) in the Analytics KB for more information.

**Come posso escludere i dati da un particolare indirizzo IP nella mia suite di rapporti?**

Dai rapporti potete eliminare i dati delle attività interne del sito Web, ad esempio il testing di siti e l'utilizzo dei dipendenti. Questa funzione consente a voi e ai vostri colleghi di visitare il sito senza distorcere i dati sul traffico. See [Exclude by IP Address](../../admin/admin/exclude-ip.md) in the Admin user guide for more information.

**Posso eliminare una suite di rapporti?**

Non è possibile eliminare una suite di rapporti. Tuttavia, una suite di rapporti può essere nascosta da tutte le visualizzazioni in Adobe Analytics. Tieni presente che le chiamate server inviate a una suite di rapporti nascosta continuano a essere conteggiate al limite contrattuale mensile. See [Hide report suites](../../admin/company/c-hide-report-suites.md) in the Admin user guide for more information.

**Quando utilizzi la segmentazione, che contenitore devo usare? Page view, visit, or visitor?**

Il contenitore di segmenti utilizzato dipende dalla larghezza di acquisizione dei dati. I contenitori di visualizzazione delle pagine portano solo hit che corrispondono ai criteri di segmento, utile per filtrare parti di visite irrilevanti. I contenitori delle visite hanno tutti gli hit di una visita in cui uno o più hit corrispondono ai criteri del segmento, utili per osservare le sessioni in generale. I contenitori dei visitatori portano tutte le visite in cui un hit corrisponde ai criteri di segmento, utile per osservare le persone. È tua scelta come analista determinare il contenitore di segmenti più adatto. See [Segmentation overview](../../components/c-segmentation/seg-overview.md) in the Components user guide for more information.

**Perché il mio segmento non viene visualizzato in Data Warehouse?**

A causa dell'architettura di elaborazione univoca di Data Warehouse, la piattaforma non è ottimizzata per gestire alcuni tipi di dati, come i percorsi. See [Data Warehouse segment compatibility](../../components/c-segmentation/seg-reference/seg-compatibility.md) in the Components user guide for more information.
