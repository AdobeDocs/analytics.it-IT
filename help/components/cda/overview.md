---
title: Analytics tra dispositivi
description: Modificate i dati da dispositivo a persona focalizzata, impilando insieme i dati del dispositivo.
translation-type: tm+mt
source-git-commit: eb2bee26dd58dcff13b4ddf41c6f6ab337d8d374
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 17%

---


# Analytics tra dispositivi

Cross-Device  Analytics è una funzione che trasforma  Analytics da una vista incentrata sui dispositivi a una vista incentrata sulle persone. Di conseguenza, gli analisti possono comprendere il comportamento degli utenti che utilizza browser, dispositivi o app diversi. Adobe supporta due flussi di lavoro generali per collegare insieme i dati dei dispositivi:

* [**Cuciture **](field-based-stitching.md)basate sul campo: Consente di scegliere una variabile Analytics  come base per l&#39;unione tra dispositivi in una suite di rapporti virtuale. Utilizza la corrispondenza deterministica per collegare insieme i dispositivi. Per la maggior parte dei casi di utilizzo con corrispondenza deterministica, Adobe consiglia di utilizzare la cucitura basata sui campi.
* [**Grafico **](device-graph.md)dispositivo: CDA comunica con un grafico del dispositivo per unire più dispositivi. Il grafico della cooperativa utilizza sia la corrispondenza deterministica che quella probabistica.

Con CDA potete rispondere a domande come:

* Quante persone interagiscono con il mio marchio? Quanti e quali tipi di dispositivi usano? Come si sovrappongono?
* Con quale frequenza le persone iniziano un’attività su un dispositivo mobile e successivamente passano a un PC desktop per completare l’attività? I click-through delle campagne che arrivano su un dispositivo portano a una conversione su un altro?
* Quali informazioni aggiuntive sull’efficacia della campagna posso ottenere considerando i passaggi tra i dispositivi? Come cambia la mia analisi funnel?
* Quali sono i percorsi più comuni seguiti dagli utenti per passare da un dispositivo all’altro? Dove decidono di lasciar perdere? Dove hanno successo?
* In che modo gli utenti con più dispositivi differiscono da quelli con un solo dispositivo?

Quando i dispositivi vengono cuciti, la persistenza variabile viene mantenuta su tutti i dispositivi. Ad esempio, un utente visita prima il sito tramite un annuncio pubblicitario sul computer desktop. L’utente trova l’app mobile, la installa e alla fine effettua un acquisto sul proprio dispositivo mobile. Con i dispositivi  Analytics, i ricavi possono essere attribuiti all&#39;annuncio che hanno fatto clic sul computer desktop.

In uno spirito di collaborazione e trasparenza, vogliamo che i nostri clienti siano consapevoli del nostro uso di Microsoft Azure in associazione con i dispositivi  Analytics. Adobe utilizza Azure per memorizzare i dati del grafico del dispositivo e per eseguire l&#39;unione tra dispositivi. Di conseguenza, i dati di Adobe  Analytics vengono trasmessi avanti e indietro tra il centro di elaborazione dati di Adobe e le istanze di Microsoft Azure con provisioning di Adobe.

Consulta le [Domande frequenti sul viaggio: Pagina](http://adobe.ly/aacda) di Analytics Spark  dispositivi per saperne di più sulle funzionalità e le funzionalità di Analytics  dispositivi diversi.

## Prerequisiti

L’utilizzo di CDA richiede tutte le seguenti operazioni. [Anche i metodi di cucitura](field-based-stitching.md) e grafico [](device-graph.md) del dispositivo basati sul campo hanno i propri prerequisiti specifici.

* È necessario firmare un contratto con Adobe che includa Adobe  Analytics Ultimate.
* Cross-Device  Analytics è abilitato a livello di suite per report. Adobe consiglia una suite di rapporti che contiene dati per dispositivi diversi, ossia dati provenienti da più tipi di dispositivi (Web, app, ecc.). Alcune organizzazioni fanno riferimento a questo concetto come a una suite di rapporti &quot;globale&quot;, anche se CDA non deve necessariamente essere rigorosamente globale da una prospettiva geografica.

## Limitazioni

Cross-Device  Analytics è una funzionalità innovativa e robusta, ma presenta dei limiti nelle modalità di utilizzo. [Anche i metodi di cucitura](field-based-stitching.md) e grafico [](device-graph.md) del dispositivo basati su campi presentano limitazioni specifiche.

* CDA è disponibile solo tramite  Analysis Workspace.
* I dispositivi  Analytics non funzionano tra suite di rapporti, né combinano i dati di più suite di rapporti.
* Le suite di rapporti Adobe  Analytics non possono mappare più di una organizzazione IMS. Poiché CDA blocca i dispositivi all’interno di una determinata suite di rapporti, non è possibile utilizzare CDA per unire i dati tra più organizzazioni IMS.
* CDA non è attualmente compatibile con gli attributi cliente. Queste due funzioni possono coincidere in suite di rapporti virtuali separate che fanno riferimento alla stessa suite di rapporti di origine.
*  Analytics utilizza una suite di rapporti virtuale e un&#39;elaborazione del tempo di rapporto, con le proprie limitazioni. Per ulteriori informazioni su queste limitazioni, consulta Suite [di rapporti](../vrs/vrs-about.md) virtuali ed elaborazione [dei tempi di](../vrs/vrs-report-time-processing.md) rapporto.
* L&#39;API 1.4 non è supportata. I connettori Power BI e Generatore di report si basano entrambi sull&#39;API 1.4 e non sono quindi compatibili con CDA.
* I dati storici nella suite di rapporti virtuali vengono modificati in base al riconoscimento e all&#39;unione dei dispositivi da parte di Adobe. I dati nella suite di rapporti di origine non vengono modificati.
