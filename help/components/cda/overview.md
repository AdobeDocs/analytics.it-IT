---
title: Analytics tra dispositivi
description: Modifica i dati da incentrati sul dispositivo a quelli incentrati sulla persona combinando i dati del dispositivo.
exl-id: e1c0d1e5-399d-45c2-864c-50ef93a77449
translation-type: tm+mt
source-git-commit: 99fea634dafc5d0992898f8f9f89471b51191fc6
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 16%

---

# Analytics tra dispositivi

Analisi multidispositivo è una funzione che trasforma Analytics da una visualizzazione incentrata sul dispositivo a una visualizzazione incentrata sulla persona. Di conseguenza, gli analisti possono comprendere il comportamento dell&#39;utente che attraversa browser, dispositivi o app. Adobe supporta due flussi di lavoro generali per collegare insieme i dati dei dispositivi:

* [**Unione basata sui campi**](field-based-stitching.md): Consente di scegliere una variabile di Analytics come base per l’unione tra dispositivi in una suite di rapporti virtuale. Utilizza la corrispondenza deterministica per collegare tra loro i dispositivi. Adobe consiglia di utilizzare unioni basate sul campo per la maggior parte dei casi di utilizzo di corrispondenza deterministica.
* [**Grafico**](device-graph.md) del dispositivo: CDA comunica con un grafico dei dispositivi per unire i dispositivi. Il grafico co-op utilizza sia la corrispondenza deterministica che la corrispondenza probabilistica.

Utilizzando CDA, puoi rispondere a domande quali:

* Quante persone interagiscono con il mio marchio? Quanti e quali tipi di dispositivi usano? Come si sovrappongono?
* Con quale frequenza le persone iniziano un’attività su un dispositivo mobile e successivamente passano a un PC desktop per completare l’attività? I click-through delle campagne che arrivano su un dispositivo portano a una conversione su un altro?
* Quali informazioni aggiuntive sull’efficacia della campagna posso ottenere considerando i passaggi tra i dispositivi? Come cambia la mia analisi funnel?
* Quali sono i percorsi più comuni seguiti dagli utenti per passare da un dispositivo all’altro? Dove decidono di lasciar perdere? Dove hanno successo?
* In che modo gli utenti con più dispositivi differiscono da quelli con un solo dispositivo?

Quando i dispositivi sono uniti, la persistenza della variabile viene riportata su più dispositivi. Ad esempio, un utente visita prima il sito tramite un annuncio pubblicitario sul computer desktop. L’utente trova la tua app mobile, la installa e alla fine effettua un acquisto sul proprio dispositivo mobile. Con Cross-Device Analytics, puoi attribuire i ricavi sul dispositivo mobile all&#39;annuncio che hanno fatto clic sul loro computer desktop.

In uno spirito di collaborazione e trasparenza, vogliamo che i nostri clienti siano consapevoli del nostro utilizzo di Microsoft Azure in associazione con Cross-Device Analytics. Adobe utilizza Azure per memorizzare i dati del grafico dei dispositivi ed eseguire unione tra dispositivi. Di conseguenza, i dati di Adobe Analytics vengono trasmessi avanti e indietro tra il centro di elaborazione dati di Adobe e le istanze di Microsoft Azure fornite da Adobe.

Vedi [Percorsi IQ: Pagina di Spark di Analytics tra dispositivi](http://adobe.ly/aacda) per ulteriori informazioni sulle funzionalità e le funzionalità di Cross-Device Analytics.

## Prerequisiti

L’utilizzo di CDA richiede tutti i seguenti elementi. [Anche i metodi di ](field-based-stitching.md) unione basati sul campo e  [i ](device-graph.md) grafici dei dispositivi hanno dei prerequisiti specifici.

* È necessario firmare un contratto con un Adobe che includa Adobe Analytics Ultimate.
* Analisi multidispositivo è abilitata per ogni suite di rapporti. Adobe consiglia una suite di rapporti che contiene dati multi-dispositivo, ovvero dati provenienti da più tipi di dispositivi (web, app, ecc.). Alcune organizzazioni fanno riferimento a questo concetto come a una suite di rapporti &quot;globale&quot;, anche se CDA non deve necessariamente essere globale da un punto di vista geografico.

## Limitazioni

Analisi multidispositivo è una funzione innovativa e affidabile, ma presenta limitazioni nel modo in cui può essere utilizzata. [Anche i metodi di ](field-based-stitching.md) unione basati su campi e  [grafici dei dispositivi ](device-graph.md) presentano limitazioni specifiche.

* CDA è disponibile solo tramite Analysis Workspace.
* Cross-Device Analytics non funziona tra suite di rapporti, né combina dati provenienti da più suite di rapporti.
* Le suite di rapporti di Adobe Analytics non possono essere mappate su più di un’organizzazione IMS. Poiché CDA unisce i dispositivi all’interno di una determinata suite di rapporti, non può essere utilizzato CDA per unire i dati tra più organizzazioni IMS.
* Private Graph sfrutta le stesse sincronizzazioni ID utilizzate dalla funzionalità [Attributi del cliente](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=en#customer-attributes) presente in Experience Cloud e Adobe Analytics. Tuttavia, le suite di rapporti virtuali CDA (basate su grafico privato o unione basata su campi) non sono compatibili con il resto della funzionalità Attributi del cliente. In altre parole, le dimensioni basate su Attributi del cliente non sono disponibili per l&#39;uso all&#39;interno delle suite di rapporti virtuali CDA.
* CDA non è attualmente compatibile con A4T.
* Cross-Device Analytics utilizza una suite di rapporti virtuali ed elaborazione dei tempi di report, con le proprie limitazioni. Per ulteriori informazioni su queste limitazioni, consulta [Suite di rapporti virtuali](../vrs/vrs-about.md) e [Elaborazione dei tempi di report](../vrs/vrs-report-time-processing.md) .
* L’API 1.4 non è supportata. I connettori e il Report Builder Power BI si basano entrambi sull’API 1.4 e non sono quindi compatibili con CDA.
* I dati storici nella suite di rapporti virtuali cambiano in base all’Adobe che riconosce e unisce i dispositivi. I dati nella suite di rapporti sorgente non cambiano.
* Il monitoraggio attivo del processo di unione CDA per Adobe è limitato solo alle suite di rapporti di produzione.
* CDA non è attualmente compatibile con Adobe Analytics [Data Repair API](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/data-repair.md)
