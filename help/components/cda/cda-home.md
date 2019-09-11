---
title: Analisi cross-device
description: Analytics cross-device modifica i tuoi dati da dispositivi incentrati su tipo di dispositivo incentrando insieme i dati dei dispositivi.
translation-type: tm+mt
source-git-commit: 40d8ecae1ac7e0a1df4a2df17f5104bee6ecf336

---


# Analisi cross-device

> [!NOTE] La documentazione Cross-Device Analytics è soggetta a modifiche man mano che la funzione è stata ulteriormente sviluppata. Verificate regolarmente la presenza di aggiornamenti.

Analytics cross-device è una funzione che trasforma Analytics da una vista incentrata su dispositivo a una vista incentrata sulla persona. Questa funzione utilizza il grafico Adobe Experience Platform Identity Co-op Graph o Private Graph per identificare i dispositivi appartenenti a singoli utenti e raggrupparli. Di conseguenza, gli analisti possono comprendere il comportamento dell'utente che attraversa browser, dispositivi o app. Utilizzando CDA potrete rispondere a domande quali:

* Quante persone interagiscono con il mio marchio? Quanti e quali tipi di dispositivi usano? Come si sovrappongono?
* Con quale frequenza le persone iniziano un'attività su un dispositivo mobile e successivamente passano a un PC desktop per completare l'attività? I click-through delle campagne che arrivano su un dispositivo portano a una conversione su un altro?
* Quali informazioni aggiuntive sull'efficacia della campagna posso ottenere considerando i passaggi tra i dispositivi? Come cambia la mia analisi funnel?
* Quali sono i percorsi più comuni seguiti dagli utenti per passare da un dispositivo all'altro? Dove decidono di lasciar perdere? Dove hanno successo?
* In che modo gli utenti con più dispositivi differiscono da quelli con un solo dispositivo?

Quando i dispositivi sono allineati, la persistenza della variabile viene eseguita su più dispositivi. Ad esempio, un utente accede per la prima volta al sito tramite un annuncio sul computer desktop. L'utente trova la tua app mobile, la installa e infine effettua un acquisto sul dispositivo mobile. Con Analytics cross-device, le entrate possono essere attribuite all'annuncio che hanno fatto clic sul computer desktop.

Consulta [IQ di viaggio: Pagina Cross-Device Analytics Spark](http://adobe.ly/aacda) per ulteriori informazioni sulle funzionalità e sulle funzionalità di Analytics cross-device.

## Prerequisiti

A partire da settembre 2019, Analytics Cross-Device richiede quanto segue. Lavora con i team all'interno della tua organizzazione e con il tuo Adobe Account Manager per assicurarti di soddisfare tutte le funzionalità seguenti.

> [!IMPORTANT] Il mancato soddisfacimento di tutti i prerequisiti può comportare l'impossibilità di abilitare Analytics cross-device o di ottenere risultati non soddisfacenti durante l'unione dei dati.

* I dati della tua organizzazione devono risiedere nel centro dati Northwest Occidentale di Adobe. È previsto il supporto per i centri dati in altre aree del mondo.
* Contattate l'Account Manager della vostra organizzazione per stabilire i seguenti punti chiave:
   * Un contratto deve essere firmato con Adobe che include Adobe Analytics Ultimate.
   * L'organizzazione deve utilizzare Adobe Experience Platform Identity Service Co-op Graph o Private Graph. Consulta la [Home Page](https://docs.adobe.com/content/help/en/device-co-op/using/home.html) nella guida utente di Device Co-op.
   * L'organizzazione deve accettare di consentire ad Adobe di elaborare e archiviare i dati di Analytics sui server Microsoft Azure. Adobe utilizza Azure per memorizzare i dati del grafico del dispositivo ed eseguire la stitching dei dispositivi. Di conseguenza, i dati di Adobe Analytics vengono passati tra il centro di elaborazione dati di Adobe e la presenza di Adobe in Microsoft Azure.
* Analytics cross-device è abilitato in base alla suite per report. La suite di rapporti richiede quanto segue:
   * Al momento, una suite di rapporti non può avere più di 100 milioni di hit al giorno. Questa soglia aumenterà nei prossimi mesi.
   * Suite di rapporti «cross-device», che indica che tutti i dati sui dispositivi devono essere inviati alla stessa suite di rapporti. Alcune organizzazioni fanno riferimento a questa suite di rapporti "globale", anche se CDA non deve necessariamente essere globale da una prospettiva geografica. Analisi cross-device non funziona nelle suite per report.
* La vostra implementazione deve soddisfare i seguenti requisiti:
   * La versione più recente del servizio Experience Cloud ID deve essere distribuita. Consulta la [Home Page](https://docs.adobe.com/content/help/en/id-service/using/home.html) nella guida utente del servizio Experience Cloud. La maggior parte delle implementazioni utilizzando Adobe Experience Platform Launch probabilmente già dispone di ECID distribuiti.
   * Chiamare la `setCustomerIDs` funzione ogni volta che un utente può essere identificato, ad esempio quando un utente accede o apre un messaggio e-mail. Questo requisito si applica a tutte le piattaforme, comprese le app mobili, se utilizzate. Consulta [setcustomerids](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html) nella guida utente del servizio Experience Cloud.

## Limitazioni

Analisi cross-device è una funzionalità innovativa e robusta, ma presenta limitazioni in termini di utilizzo.

* CDA è disponibile solo tramite Analysis Workspace.
* Non è possibile applicare stitching tra le organizzazioni IMS. Accertatevi di non usare più organizzazioni IMS nella vostra implementazione.
* Non è possibile applicare stitching nelle suite di rapporti come descritto in Prerequisiti sopra.
* CDA non è attualmente compatibile con gli attributi del cliente. Gli attributi del cliente non possono essere utilizzati per creare una suite di rapporti virtuale CDA, all'interno di segmenti diversi o per rapporti all'interno di un progetto Analysis Workspace basato su una suite di rapporti virtuale CDA.
* CDA richiede un grafico Co-op o un grafico privato. I grafici dei dispositivi 3 rd-party non sono supportati.
* Gli ID Analytics precedenti non sono supportati. Solo i visitatori con Experience Cloud ID sono legati.
* L'Assistenza clienti non supporta ancora completamente questa funzionalità. Il [forum Analisi cross-device](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/cross-device-analytics/overview) può essere utilizzato per supportare questa funzione, che include coinvolgimento diretto e diretto dei manager dei prodotti Adobe.
* Analisi cross-device utilizza una suite di rapporti virtuale e un'elaborazione dei tempi di report, con limitazioni specifiche. Per ulteriori informazioni su queste limitazioni, consultate [Suite di rapporti virtuali](../vrs/vrs-about.md) e [Elaborazione](../vrs/vrs-report-time-processing.md) dei tempi di rapporto.
* I nuovi dispositivi che visitano il sito possono richiedere fino a due settimane per essere elaborati dal grafico Co-op o dal grafico Privato. Il livello di stitching in CDA per le due settimane più recenti è generalmente inferiore a quello degli intervalli di date precedenti a due settimane. Adobe pianifica di migliorare il servizio Identità Adobe Experience Platform per unire nuovi dispositivi in tempo reale.
* I dati storici nella suite di rapporti virtuali cambiano in base al riconoscimento e all'unione dei dispositivi da parte di Adobe. I dati nella suite di rapporti sorgente non cambiano.

Dopo che l'organizzazione ha soddisfatto tutti i requisiti e ha compreso i limiti, potete iniziare [a configurare Analytics cross-device](cda-setup.md).
