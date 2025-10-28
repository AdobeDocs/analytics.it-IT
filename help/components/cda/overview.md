---
title: Cross-Device Analytics
description: Scopri come trasformare i dati incentrati sul dispositivo in incentrati sulla persona unendo i dati del dispositivo.
exl-id: e1c0d1e5-399d-45c2-864c-50ef93a77449
feature: CDA
role: Admin
source-git-commit: 6c74f4d4c14765742a2aafdfff2a083c6b0a7183
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 57%

---

# Cross-Device Analytics

{{available-existing-customers}}

>[!WARNING]
>
>Il grafico dei dispositivi in Analytics tra dispositivi non sarà più disponibile il **31 dicembre 2025**. Cambiare una VRS abilitata per Device Graph corrente con il [metodo basato sul campo](/help/components/cda/field-based-stitching.md).
>


Cross-Device Analytics (CDA) è una funzione che trasforma Analytics da una visione incentrata sul dispositivo a una incentrata sulla persona. Di conseguenza, gli analisti possono comprendere il comportamento dell’utente su app, browser o dispositivi diversi. Adobe supporta due flussi di lavoro generali per collegare i dati dei dispositivi:

* [**Unione basata sui campi**](field-based-stitching.md): opzione di unione consigliata che utilizza solo la corrispondenza deterministica per collegare i dispositivi.
L’unione basata sui campi consente di scegliere una variabile di Analytics come base per l’unione tra dispositivi diversi in una suite di rapporti virtuale.

* [**Grafico dispositivo**](device-graph.md): Analytics tra dispositivi comunica con un grafico privato per unire i dispositivi.

Utilizzando CDA, potrai rispondere a domande quali:

* Quante persone interagiscono con il mio marchio? Quanti e quali tipi di dispositivi usano? Come si sovrappongono?
* Con quale frequenza le persone iniziano un’attività su un dispositivo mobile e successivamente passano a un PC desktop per completare l’attività? I click-through delle campagne che arrivano su un dispositivo portano a una conversione su un altro?
* Quali informazioni aggiuntive sull’efficacia della campagna posso ottenere considerando i passaggi tra i dispositivi? Come cambia la mia analisi funnel?
* Quali sono i percorsi più comuni seguiti dagli utenti per passare da un dispositivo all’altro? Dove decidono di lasciar perdere? Dove hanno successo?
* In che modo gli utenti con più dispositivi differiscono da quelli con un solo dispositivo?

Quando si uniscono i dispositivi, la persistenza delle variabili viene riportata su tutti i dispositivi. Ad esempio, un utente visita prima il sito tramite un annuncio pubblicitario sul computer desktop. L’utente trova la tua app mobile, la installa e alla fine effettua un acquisto dal proprio dispositivo mobile. Con Analytics tra dispositivi, puoi attribuire l’acquisto dal dispositivo mobile all’annuncio su cui l’utente aveva fatto clic sul suo computer desktop.

Microsoft Azure viene utilizzato per l’analisi tra dispositivi. Adobe utilizza Azure per memorizzare i dati del grafo di dispositivi e per eseguire l’unione tra dispositivi diversi. Di conseguenza, i dati di Adobe Analytics vengono trasmessi avanti e indietro tra il centro di elaborazione dati di Adobe e le istanze di Adobe con provisioning di Microsoft Azure.

Per ulteriori informazioni sulle funzionalità di Analytics tra dispositivi, consulta la [pagina Spark per Analytics tra dispositivi](https://express.adobe.com/page/8ZpjsX6Lp5XTM/).

## Prerequisiti

L&#39;utilizzo di Analytics tra dispositivi richiede i metodi [unione basata sui campi](field-based-stitching.md) e [grafo di dispositivi](device-graph.md) ed entrambi dispongono di prerequisiti specifici.

* È necessario firmare un contratto con Adobe che includa Adobe Analytics Ultimate.
* La tua organizzazione sceglie in quali suite di rapporti abilitare CDA. Adobe consiglia suite di rapporti che contengano dati cross-device, ovvero dati provenienti da più tipi di dispositivi/browser/app. Alcune organizzazioni fanno riferimento a questo concetto come a una suite di rapporti &quot;globale&quot;, anche se Cross-Device Analytics non deve necessariamente essere globale da una prospettiva geografica.

## Limitazioni

Analytics tra dispositivi è una funzione innovativa e affidabile, ma presenta limitazioni sul modo in cui può essere utilizzata. Inoltre, i metodi con [unione basata sui campi](field-based-stitching.md) e [grafo di dispositivi](device-graph.md) presentano limitazioni specifiche.

* Analytics tra dispositivi è disponibile solo tramite Analysis Workspace.
* Analytics tra dispositivi non funziona tra diverse suite di rapporti e non combina dati provenienti da più suite di rapporti.
* Le suite di rapporti di Adobe Analytics non possono essere mappate su più di un ID organizzazione. Poiché Cross-Device Analytics unisce i dispositivi all’interno di una determinata suite di rapporti, non è possibile utilizzare Cross-Device Analytics per unire i dati di più ID organizzazione.
* Analytics tra dispositivi utilizza una pipeline di elaborazione complessa, con più componenti dipendenti. Questa pipeline viene eseguita in parallelo con il flusso di lavoro di base di Analytics per la generazione di rapporti. Per il numero totale di hit tra la suite di rapporti originale e la suite di rapporti virtuale di Analytics tra dispositivi diversi, si può verificare una mancata corrispondenza dei dati di circa l’1%.
* Analytics tra dispositivi utilizza una suite di rapporti virtuale e l’elaborazione al momento del rapporto, con proprie limitazioni. Ad esempio, al momento non supportano le variabili dei canali di marketing. Per ulteriori informazioni su queste limitazioni, consulta [Suite di rapporti virtuali](/help/components/vrs/vrs-about.md) ed [Elaborazione al momento del rapporto](/help/components/vrs/vrs-report-time-processing.md).
* Private Graph sfrutta le stesse sincronizzazioni ID delle sincronizzazioni ID utilizzate dalla funzionalità [Attributi del cliente](https://experienceleague.adobe.com/en/docs/core-services/interface/services/customer-attributes/attributes) disponibile in Experience Cloud e Adobe Analytics. Tuttavia, le suite di rapporti virtuali di Analytics tra dispositivi (basate su Private Graph o unione basata sui campi) non sono compatibili con il resto della funzionalità Attributi del cliente. In altre parole, le dimensioni basate sugli attributi del cliente non sono disponibili per l’utilizzo con le suite di rapporti virtuali di Analytics tra dispositivi.
* Analytics tra dispositivi non è attualmente compatibile con A4T.
* L’API 1.4 non è supportato. Report Builder e i connettori Power BI si basano sull’API 1.4 e non sono quindi compatibili con CDA.
* Il monitoraggio attivo del processo di unione di Analytics tra dispositivi da parte di Adobe è limitato solo alle suite di rapporti di produzione.
* Analytics tra dispositivi non è attualmente compatibile con l&#39;API [Data Repair](https://developer.adobe.com/analytics-apis/docs/2.0/) di Adobe Analytics
* I dati storici nella suite di rapporti virtuali cambiano in base al riconoscimento e all’unione dei dispositivi da parte di Adobe. I dati nella suite dei rapporti di origine non cambiano.
* I dati uniti seguono una latenza di 8-12 ore.
* I dati della cronologia di mappatura per un determinato dispositivo vengono memorizzati per un massimo di 1 anno.
* Se un dispositivo raggiunge in un anno un numero molto elevato di voci nella cronologia di mappatura, questa viene troncata. Il limite esatto dipende dall’opzione di unione utilizzata.
