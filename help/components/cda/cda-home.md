---
title: Analytics tra dispositivi
description: Analisi cross-Device (Analisi multi-dispositivo) modifica i dati dall'essere incentrati sul dispositivo all'essere focalizzati sulla persona, impilando insieme i dati del dispositivo.
translation-type: tm+mt
source-git-commit: ca79141a353dbd09176dbbe295611656262ba107

---


# Analytics tra dispositivi

> [!NOTE] La documentazione di Analytics tra dispositivi è soggetta a modifiche man mano che la funzione viene ulteriormente sviluppata. Controllate regolarmente la disponibilità di aggiornamenti.

Analytics tra dispositivi è una funzione che trasforma Analytics da una vista incentrata sui dispositivi a una vista incentrata sulle persone. Questa funzione utilizza Adobe Experience Platform Identity Service Co-op Graph o Private Graph per identificare i dispositivi appartenenti a individui e unire questi due elementi. Di conseguenza, gli analisti possono comprendere il comportamento degli utenti che utilizza browser, dispositivi o app diversi. Utilizzando CDA potrete rispondere a domande quali:

* Quante persone interagiscono con il mio marchio? Quanti e quali tipi di dispositivi usano? Come si sovrappongono?
* Con quale frequenza le persone iniziano un’attività su un dispositivo mobile e successivamente passano a un PC desktop per completare l’attività? I click-through delle campagne che arrivano su un dispositivo portano a una conversione su un altro?
* Quali informazioni aggiuntive sull’efficacia della campagna posso ottenere considerando i passaggi tra i dispositivi? Come cambia la mia analisi funnel?
* Quali sono i percorsi più comuni seguiti dagli utenti per passare da un dispositivo all’altro? Dove decidono di lasciar perdere? Dove hanno successo?
* In che modo gli utenti con più dispositivi differiscono da quelli con un solo dispositivo?

Quando i dispositivi vengono cuciti, la persistenza variabile viene mantenuta su tutti i dispositivi. Ad esempio, un utente visita prima il sito tramite un annuncio pubblicitario sul computer desktop. L’utente trova l’app mobile, la installa e alla fine effettua un acquisto sul proprio dispositivo mobile. Con Analytics multi-dispositivo, i ricavi possono essere attribuiti all'annuncio che hanno fatto clic sul computer desktop.

Consulta [IQ viaggio: Pagina](http://adobe.ly/aacda) Spark di Analytics per dispositivi diversi per ulteriori informazioni sulle funzionalità e le funzionalità di Analytics multi-dispositivo.

## Prerequisiti

A partire da settembre 2019, Analytics cross-device richiede quanto segue. Collaborate con i team all'interno dell'organizzazione e con l'Account Manager Adobe per assicurarvi di soddisfare tutti i requisiti seguenti.

> [!IMPORTANT] Se non vengono soddisfatti tutti i prerequisiti, potrebbe non essere possibile abilitare l'analisi multi-dispositivo o non essere possibile ottenere risultati soddisfacenti durante l'unione dei dati.

* I dati dell'organizzazione devono risiedere nel centro dati di Adobe Pacific Northwest. è previsto il sostegno ai centri dati in altre regioni del mondo.
* Contatta l'Account Manager della tua organizzazione per stabilire i seguenti punti chiave:
   * È necessario firmare un contratto con Adobe che includa Adobe Analytics Ultimate.
   * L’organizzazione deve utilizzare Adobe Experience Platform Identity Service Co-op Graph o Private Graph. Vedi la [home page](https://docs.adobe.com/content/help/en/device-co-op/using/home.html) nella guida utente di Device Co-op.
   * L'organizzazione deve accettare di consentire ad Adobe di elaborare e archiviare i dati di Analytics sui server Microsoft Azure. Adobe utilizza Azure per memorizzare i dati del grafico del dispositivo ed eseguire la cucitura del dispositivo. Di conseguenza, i dati di Adobe Analytics vengono trasmessi avanti e indietro tra il centro di elaborazione dati di Adobe e la presenza di Adobe in Microsoft Azure.
* Analisi tra dispositivi è abilitata per ogni suite di rapporti. Le suite di rapporti abilitate per CDA richiedono quanto segue:
   * La suite di rapporti non può avere più di 100 milioni di hit al giorno. Tale soglia aumenterà nei prossimi mesi.
   * Adobe consiglia una suite di rapporti contenente dati per più dispositivi, ossia dati provenienti da più tipi di dispositivi (Web, app, ecc.). Alcune organizzazioni fanno riferimento a questo concetto come a una suite di rapporti "globale", anche se CDA non deve essere necessariamente globale da una prospettiva geografica. L'analisi tra più dispositivi non funziona tra le suite di rapporti, né combina i dati di più suite di rapporti.
* L'implementazione deve soddisfare i seguenti requisiti:
   * È necessario distribuire la versione più recente del servizio Experience Cloud ID. Vedi la [home page](https://docs.adobe.com/content/help/en/id-service/using/home.html) nella guida utente del servizio Experience Cloud Identity. La maggior parte delle implementazioni che utilizzano Adobe Experience Platform Launch probabilmente hanno già implementato ECID.
   * Chiama la `setCustomerIDs` funzione ogni volta che è possibile identificare un individuo, ad esempio quando un utente accede o apre un messaggio e-mail. Questo requisito si applica a tutte le piattaforme, comprese le app mobili se utilizzate. Consulta [setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html) nella guida utente del servizio Experience Cloud Identity.

## Limitazioni

Analisi cross-device è una funzione innovativa e affidabile, ma presenta dei limiti nelle modalità di utilizzo.

* CDA è disponibile solo tramite Analysis Workspace.
* Non è possibile unire più suite di rapporti come descritto nei prerequisiti sopra.
* Le suite di rapporti di Adobe Analytics non possono mappare più di una organizzazione IMS. Poiché CDA blocca i dispositivi all’interno di una determinata suite di rapporti, non è possibile utilizzare CDA per unire i dati tra più organizzazioni IMS.
* CDA non è attualmente compatibile con gli attributi cliente. Gli attributi del cliente non possono essere utilizzati per creare una suite di rapporti virtuali CDA, all’interno di segmenti cross-device o per generare rapporti all’interno di un progetto di area di lavoro Analisi basato su una suite di rapporti virtuale CDA.
* CDA richiede Co-op Graph o Private Graph. I grafici dei dispositivi 3rd-party non sono supportati.
* Gli ID Analytics legacy non sono supportati. Solo i visitatori con Experience Cloud ID sono cuciti.
* L'Assistenza clienti non supporta ancora completamente questa funzione. Il forum [Analisi](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics/cross-device-analytics/overview) multi-dispositivo può essere utilizzato per il supporto su questa funzione, che include il coinvolgimento attivo e diretto dei Product Manager Adobe.
* Analytics cross-Device utilizza una suite di rapporti virtuale e l'elaborazione dei tempi di rapporto, che hanno le proprie limitazioni. Per ulteriori informazioni su queste limitazioni, consulta Suite [di rapporti](../vrs/vrs-about.md) virtuali ed elaborazione [dei tempi di](../vrs/vrs-report-time-processing.md) rapporto.
* I nuovi dispositivi che visitano il sito possono richiedere fino a due settimane per essere elaborati dal Co-op Graph o dal grafico privato. Il livello di cucitura in CDA per le ultime due settimane è generalmente inferiore a quello degli intervalli di date superiori a due settimane. Adobe pianifica di migliorare Adobe Experience Platform Identity Service per unire in tempo reale nuovi dispositivi.
* I dati storici nella suite di rapporti virtuali cambiano in base al riconoscimento e all'unione dei dispositivi da parte di Adobe. I dati nella suite di rapporti di origine non vengono modificati.

Una volta che l'organizzazione avrà soddisfatto tutti i requisiti e compreso i limiti, puoi iniziare a [configurare l'analisi](cda-setup.md)tra dispositivi.
