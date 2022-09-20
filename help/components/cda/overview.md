---
title: Analytics tra dispositivi
description: Unisci i dati dei dispositivi, per renderli incentrati sulla persona invece che incentrati sul dispositivo.
exl-id: e1c0d1e5-399d-45c2-864c-50ef93a77449
source-git-commit: 9c9322647145832503e4a5875789e9cf7e9a2397
workflow-type: ht
source-wordcount: '860'
ht-degree: 100%

---

# Analytics tra dispositivi

Cross-Device Analytics (CDA) è una funzione che trasforma Analytics da una visione incentrata sul dispositivo a una incentrata sulla persona. Di conseguenza, gli analisti possono comprendere il comportamento dell’utente su app, browser o dispositivi diversi. Adobe supporta due flussi di lavoro generali per collegare i dati dei dispositivi:

* [**Unione basata sui campi**](field-based-stitching.md): opzione di unione consigliata che utilizza solo la corrispondenza deterministica per collegare i dispositivi.
Consente di scegliere una variabile di Analytics come base per l’unione tra dispositivi diversi in una suite di rapporti virtuali.

* [**Grafo di dispositivi**](device-graph.md): CDA comunica con un grafo privato per unire i dispositivi.

Utilizzando CDA, potrai rispondere a domande quali:

* Quante persone interagiscono con il mio marchio? Quanti e quali tipi di dispositivi usano? Come si sovrappongono?
* Con quale frequenza le persone iniziano un’attività su un dispositivo mobile e successivamente passano a un PC desktop per completare l’attività? I click-through delle campagne che arrivano su un dispositivo portano a una conversione su un altro?
* Quali informazioni aggiuntive sull’efficacia della campagna posso ottenere considerando i passaggi tra i dispositivi? Come cambia la mia analisi funnel?
* Quali sono i percorsi più comuni seguiti dagli utenti per passare da un dispositivo all’altro? Dove decidono di lasciar perdere? Dove hanno successo?
* In che modo gli utenti con più dispositivi differiscono da quelli con un solo dispositivo?

Quando si uniscono i dispositivi, la persistenza delle variabili viene riportata su tutti i dispositivi. Ad esempio, un utente visita prima il sito tramite un annuncio pubblicitario sul computer desktop. L’utente trova la tua app mobile, la installa e alla fine effettua un acquisto dal proprio dispositivo mobile. Con Analytics tra dispositivi, puoi attribuire l’acquisto dal dispositivo mobile all’annuncio su cui l’utente aveva fatto clic sul suo computer desktop.

All’insegna della collaborazione e della trasparenza, i nostri clienti devono essere consapevoli che utilizziamo Microsoft Azure in associazione con Analytics tra dispositivi. Adobe utilizza Azure per memorizzare i dati del grafo di dispositivi e per eseguire l’unione tra dispositivi diversi. I dati di Adobe Analytics vengono quindi trasmessi avanti e indietro tra il centro di elaborazione dati di Adobe e le istanze di Microsoft Azure utilizzate da Adobe.

Per ulteriori informazioni sulle funzionalità di Analytics tra dispositivi, consulta la [pagina Spark “Journey IQ: Analytics tra dispositivi”](https://adobe.ly/aacda).

## Prerequisiti 

L’utilizzo di CDA richiede tutti i seguenti elementi. Inoltre, i metodi con [unione basata sui campi](field-based-stitching.md) e [grafo di dispositivi](device-graph.md) presentano prerequisiti specifici.

* È necessario firmare un contratto con Adobe che includa Adobe Analytics Ultimate.
* La tua organizzazione sceglie in quali suite di rapporti abilitare CDA. Adobe consiglia suite di rapporti che contengano dati cross-device, ovvero dati provenienti da più tipi di dispositivi/browser/app. Alcune organizzazioni fanno riferimento a questo concetto come a una suite di rapporti “globale”, anche se CDA non deve necessariamente essere globale da un punto di vista geografico.

## Limitazioni

Analytics tra dispositivi è una funzione innovativa e affidabile, ma presenta limitazioni sul modo in cui può essere utilizzata. Inoltre, i metodi con [unione basata sui campi](field-based-stitching.md) e [grafo di dispositivi](device-graph.md) presentano limitazioni specifiche.

* CDA è disponibile solo tramite Analysis Workspace.
* Analytics tra dispositivi non funziona tra diverse suite di rapporti e non combina dati provenienti da più suite di rapporti.
* Le suite di rapporti di Adobe Analytics non possono essere mappate su più di un ID organizzazione. Poiché CDA unisce i dispositivi all’interno di una determinata suite di rapporti, non può essere utilizzato per unire dati da più ID organizzazione.
* CDA utilizza una pipeline di elaborazione complessa, con più componenti dipendenti. Questo viene eseguito in parallelo con il flusso di lavoro di base di Analytics per la reportistica. Pertanto, è previsto uno scostamento di circa 1% per il numero totale di hit tra la suite di rapporti originale e la suite di rapporti virtuale di CDA.
* Analytics tra dispositivi utilizza una suite di rapporti virtuale e l’elaborazione al momento del rapporto, con proprie limitazioni. Ad esempio, al momento non supportano le variabili dei canali di marketing. Per ulteriori informazioni su queste limitazioni, consulta [Suite di rapporti virtuali](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=it) ed [Elaborazione al momento del rapporto](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=it).
* Private Graph sfrutta le stesse sincronizzazioni ID utilizzate dalla funzionalità [Attributi del cliente](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=it#customer-attributes) disponibile in Experience Cloud e Adobe Analytics. Tuttavia, le suite di rapporti virtuali di CDA (basate su Private Graph o unione basata sui campi) non sono compatibili con il resto della funzionalità Attributi del cliente. In altre parole, le dimensioni basate su Attributi del cliente non possono essere utilizzate con le suite di rapporti virtuali di CDA.
* CDA non è attualmente compatibile con A4T.
* L’API 1.4 non è supportato. Report Builder e i connettori Power BI si basano sull’API 1.4 e non sono quindi compatibili con CDA.
* Il monitoraggio attivo del processo di unione di CDA da parte di Adobe è limitato solo alle suite di rapporti di produzione.
* CDA non è attualmente compatibile con l’[API Data Repair](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/data-repair.md) di Adobe Analytics.
* I dati storici nella suite di rapporti virtuali cambiano in base al riconoscimento e all’unione dei dispositivi da parte di Adobe. I dati nella suite dei rapporti di origine non cambiano.
* I dati uniti seguono una latenza di 8-12 ore.
* I dati della cronologia di mappatura per un determinato dispositivo vengono memorizzati per un massimo di 1 anno.
* Se un dispositivo raggiunge in un anno un numero molto elevato di voci nella cronologia di mappatura, questa viene troncata. Il limite esatto dipende dall’opzione di unione utilizzata.
