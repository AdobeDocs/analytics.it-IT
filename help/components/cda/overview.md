---
title: Analytics tra dispositivi
description: Modifica i dati da incentrati sul dispositivo a quelli incentrati sulla persona combinando i dati del dispositivo.
exl-id: e1c0d1e5-399d-45c2-864c-50ef93a77449
source-git-commit: aa4550d7012f76571f7623428d3d4ee08f728f64
workflow-type: tm+mt
source-wordcount: '883'
ht-degree: 17%

---

# Analytics tra dispositivi

Analisi multidispositivo è una funzione che trasforma Analytics da una visualizzazione incentrata sul dispositivo a una visualizzazione incentrata sulla persona. Di conseguenza, gli analisti possono comprendere il comportamento dell&#39;utente che attraversa browser, dispositivi o app. Adobe supporta due flussi di lavoro generali per collegare insieme i dati dei dispositivi:

* [**Unione basata sui campi**](field-based-stitching.md): Opzione di unione consigliata perché utilizza solo la corrispondenza deterministica per collegare i dispositivi insieme.
Consente di scegliere una variabile di Analytics come base per l’unione tra dispositivi in una suite di rapporti virtuale.
* [**Grafico dei dispositivi**](device-graph.md): CDA comunica con un grafico dei dispositivi per unire i dispositivi. Il grafico co-op utilizza sia la corrispondenza deterministica che la corrispondenza probabilistica.

>[!NOTE]
>
>Ulteriori informazioni sulle [Fine del ciclo di vita di Device Co-op](https://experienceleague.adobe.com/docs/device-co-op/using/about/device-co-op-eol.html).

Utilizzando CDA, puoi rispondere a domande quali:

* Quante persone interagiscono con il mio marchio? Quanti e quali tipi di dispositivi usano? Come si sovrappongono?
* Con quale frequenza le persone iniziano un’attività su un dispositivo mobile e successivamente passano a un PC desktop per completare l’attività? I click-through delle campagne che arrivano su un dispositivo portano a una conversione su un altro?
* Quali informazioni aggiuntive sull’efficacia della campagna posso ottenere considerando i passaggi tra i dispositivi? Come cambia la mia analisi funnel?
* Quali sono i percorsi più comuni seguiti dagli utenti per passare da un dispositivo all’altro? Dove decidono di lasciar perdere? Dove hanno successo?
* In che modo gli utenti con più dispositivi differiscono da quelli con un solo dispositivo?

Quando i dispositivi sono uniti, la persistenza della variabile viene riportata su più dispositivi. Ad esempio, un utente visita prima il sito tramite un annuncio pubblicitario sul computer desktop. L’utente trova la tua app mobile, la installa e alla fine effettua un acquisto sul proprio dispositivo mobile. Con Cross-Device Analytics, puoi attribuire i ricavi sul dispositivo mobile all&#39;annuncio che hanno fatto clic sul loro computer desktop.

In uno spirito di collaborazione e trasparenza, vogliamo che i nostri clienti siano consapevoli del nostro utilizzo di Microsoft Azure in associazione con Cross-Device Analytics. Adobe utilizza Azure per memorizzare i dati del grafico dei dispositivi ed eseguire unione tra dispositivi. Di conseguenza, i dati di Adobe Analytics vengono trasmessi avanti e indietro tra il centro di elaborazione dati di Adobe e le istanze di Microsoft Azure fornite da Adobe.

Consulta la sezione [IQ percorso: Pagina di Spark di Analytics tra dispositivi](https://adobe.ly/aacda) per ulteriori informazioni sulle funzionalità di Cross-Device Analytics.

## Prerequisiti 

L’utilizzo di CDA richiede tutti i seguenti elementi. [Unione basata sui campi](field-based-stitching.md) e [Grafico dei dispositivi](device-graph.md) i metodi hanno anche dei prerequisiti specifici.

* È necessario firmare un contratto con un Adobe che includa Adobe Analytics Ultimate.
* Analisi multidispositivo è abilitata per ogni suite di rapporti. Adobe consiglia una suite di rapporti che contiene dati multi-dispositivo, ovvero dati provenienti da più tipi di dispositivi (web, app, ecc.). Alcune organizzazioni fanno riferimento a questo concetto come a una suite di rapporti &quot;globale&quot;, anche se CDA non deve necessariamente essere globale da un punto di vista geografico.

## Limitazioni

Analisi multidispositivo è una funzione innovativa e affidabile, ma presenta limitazioni nel modo in cui può essere utilizzata. [Unione basata sui campi](field-based-stitching.md) e [Grafico dei dispositivi](device-graph.md) i metodi hanno anche le proprie limitazioni specifiche.

* CDA è disponibile solo tramite Analysis Workspace.
* Cross-Device Analytics non funziona tra suite di rapporti, né combina dati provenienti da più suite di rapporti.
* Le suite di rapporti di Adobe Analytics non possono essere mappate su più di un ID organizzazione. Poiché CDA unisce i dispositivi all’interno di una determinata suite di rapporti, non può essere utilizzato per unire i dati tra più ID organizzazione.
* CDA utilizza una pipeline di elaborazione complessa, con più componenti dipendenti. Questo viene eseguito in parallelo con il flusso di lavoro di base di reporting di Analytics. Pertanto, è prevista una mancata corrispondenza dei dati di circa l’1% per il numero totale di hit tra la suite di rapporti originale e la suite di rapporti virtuale CDA.
* Cross-Device Analytics utilizza una suite di rapporti virtuali ed elaborazione dei tempi di report, con le proprie limitazioni. Ad esempio, al momento non supportano le variabili Marketing Channels . Vedi [Suite di rapporti virtuali](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=it) e [Elaborazione dell&#39;ora rapporto](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=en#report-time-processing-limitations) per ulteriori informazioni su queste limitazioni.
* Private Graph sfrutta le stesse sincronizzazioni ID utilizzate dal [Attributi del cliente](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html#customer-attributes) funzionalità trovata in Experience Cloud e Adobe Analytics. Tuttavia, le suite di rapporti virtuali CDA (basate su grafico privato o unione basata su campi) non sono compatibili con il resto della funzionalità Attributi del cliente. In altre parole, le dimensioni basate su Attributi del cliente non sono disponibili per l&#39;uso con le suite di rapporti virtuali CDA.
* CDA non è attualmente compatibile con A4T.
* L’API 1.4 non è supportata. I connettori e il Report Builder Power BI si basano entrambi sull’API 1.4 e non sono quindi compatibili con CDA.
* Il monitoraggio attivo del processo di unione CDA per Adobe è limitato solo alle suite di rapporti di produzione.
* CDA non è attualmente compatibile con Adobe Analytics [API Data Repair](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/data-repair.md)
* I dati storici nella suite di rapporti virtuali cambiano in base all’Adobe che riconosce e unisce i dispositivi. I dati nella suite di rapporti sorgente non cambiano.
* I dati uniti seguono una latenza di 8-12 ore.
* I dati della cronologia di mappatura per un determinato dispositivo vengono memorizzati per un massimo di 1 anno.
* Se un dispositivo raggiunge un numero molto elevato di voci della cronologia di mappatura in un anno, la cronologia di mappatura viene troncata. Il limite esatto dipende dall&#39;opzione di unione utilizzata.
