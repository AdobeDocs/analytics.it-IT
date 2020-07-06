---
title: Analytics tra dispositivi
description: Cross-Device  Analytics modifica i dati dall'essere incentrati sul dispositivo all'essere focalizzati sulla persona, impilando insieme i dati del dispositivo.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '965'
ht-degree: 14%

---


# Analytics tra dispositivi

Cross-Device  Analytics è una funzione che trasforma  Analytics da una vista incentrata sui dispositivi a una vista incentrata sulle persone. Questa funzione utilizza il grafico Co-op di  Adobe Experience Platform Identity Service o il grafico privato per identificare i dispositivi appartenenti a individui, e li unisce. Di conseguenza, gli analisti possono comprendere il comportamento degli utenti che utilizza browser, dispositivi o app diversi. Utilizzando CDA potrete rispondere a domande quali:

* Quante persone interagiscono con il mio marchio? Quanti e quali tipi di dispositivi usano? Come si sovrappongono?
* Con quale frequenza le persone iniziano un’attività su un dispositivo mobile e successivamente passano a un PC desktop per completare l’attività? I click-through delle campagne che arrivano su un dispositivo portano a una conversione su un altro?
* Quali informazioni aggiuntive sull’efficacia della campagna posso ottenere considerando i passaggi tra i dispositivi? Come cambia la mia analisi funnel?
* Quali sono i percorsi più comuni seguiti dagli utenti per passare da un dispositivo all’altro? Dove decidono di lasciar perdere? Dove hanno successo?
* In che modo gli utenti con più dispositivi differiscono da quelli con un solo dispositivo?

Quando i dispositivi vengono cuciti, la persistenza variabile viene mantenuta su tutti i dispositivi. Ad esempio, un utente visita prima il sito tramite un annuncio pubblicitario sul computer desktop. L’utente trova l’app mobile, la installa e alla fine effettua un acquisto sul proprio dispositivo mobile. Con i dispositivi  Analytics, i ricavi possono essere attribuiti all&#39;annuncio che hanno fatto clic sul computer desktop.

Consulta IQ [del viaggio: Pagina](http://adobe.ly/aacda) di Analytics Spark  dispositivi per saperne di più sulle funzionalità e le funzionalità di Analytics  dispositivi diversi.

## Prerequisiti

Tra dispositivi  Analytics richiede quanto segue. Collaborate con i team all&#39;interno dell&#39;organizzazione e con l&#39;Account Manager Adobe per assicurarvi di soddisfare tutti i requisiti indicati di seguito.

>[!IMPORTANT]
>
>Se non vengono soddisfatti tutti i prerequisiti, potrebbe non essere possibile abilitare l&#39; di Analytics tra dispositivi diversi o risultati negativi durante l&#39;unione dei dati.

* I dati dell&#39;organizzazione devono risiedere nel centro dati di Adobe Pacific Northwest. è previsto il sostegno ai centri dati in altre regioni del mondo.
* Contatta l&#39;Account Manager della tua organizzazione per stabilire i seguenti punti chiave:
   * È necessario firmare un contratto con Adobe che includa Adobe  Analytics Ultimate.
   * L&#39;organizzazione deve utilizzare il grafico Co-op o il grafico privato  Adobe Experience Platform Identity Service. Vedi la [home page](https://docs.adobe.com/content/help/it-IT/device-co-op/using/home.html) nella guida utente di Device Co-op.
   * In uno spirito di collaborazione e trasparenza, vogliamo che i nostri clienti siano consapevoli del nostro uso di Microsoft Azure in associazione con i dispositivi  Analytics. Adobe utilizza Azure per memorizzare i dati del grafico del dispositivo e per eseguire l&#39;unione tra dispositivi. Di conseguenza, i dati di Adobe  Analytics vengono trasmessi avanti e indietro tra il centro di elaborazione dati di Adobe e le istanze di Microsoft Azure con provisioning di Adobe.
* Cross-Device  Analytics è abilitato a livello di suite per report. Le suite di rapporti abilitate per CDA richiedono quanto segue:
   * La suite di rapporti non può avere più di 500 milioni di hit al giorno.
   * Adobe consiglia una suite di rapporti contenente dati per più dispositivi, ossia dati provenienti da più tipi di dispositivi (Web, app, ecc.). Alcune organizzazioni fanno riferimento a questo concetto come a una suite di rapporti &quot;globale&quot;, anche se CDA non deve necessariamente essere rigorosamente globale da una prospettiva geografica. I dispositivi  Analytics non funzionano tra suite di rapporti, né combinano i dati di più suite di rapporti.
* L&#39;implementazione deve soddisfare i seguenti requisiti:
   * È necessario distribuire la versione più recente del servizio ID Experience Cloud . Consulta la [Home Page](https://docs.adobe.com/content/help/it-IT/id-service/using/home.html) nella guida utente  Experience Cloud Identity Service. La maggior parte delle implementazioni che utilizzano  lancio Adobe Experience Platform probabilmente hanno già implementato ECID.
   * Chiama la `setCustomerIDs` funzione ogni volta che è possibile identificare un individuo, ad esempio quando un utente accede o apre un messaggio e-mail. Questo requisito si applica a tutte le piattaforme, comprese le app mobili se utilizzate. Consulta [setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html) nella guida utente  Experience Cloud Identity Service.

## Limitazioni

Cross-Device  Analytics è una funzionalità innovativa e robusta, ma presenta dei limiti nelle modalità di utilizzo.

* CDA è disponibile solo tramite  Analysis Workspace.
* Non è possibile unire più suite di rapporti come descritto nei prerequisiti sopra.
* Le suite di rapporti Adobe  Analytics non possono mappare più di una organizzazione IMS. Poiché CDA blocca i dispositivi all’interno di una determinata suite di rapporti, non è possibile utilizzare CDA per unire i dati tra più organizzazioni IMS.
* CDA non è attualmente compatibile con gli attributi cliente. Gli attributi del cliente non possono essere utilizzati per creare una suite di rapporti virtuali CDA, all’interno di segmenti cross-device o per generare rapporti all’interno di un progetto di area di lavoro Analisi basato su una suite di rapporti virtuale CDA.
   > [!TIP] Sebbene gli attributi del cliente non possano essere utilizzati in CDA, entrambe le funzioni dipendono dalla `setCustomerIDs` funzione. Queste due funzioni possono coincidere in suite di rapporti virtuali separate.
* CDA richiede Co-op Graph o Private Graph. I grafici dei dispositivi 3rd-party non sono supportati.
*  ID Analytics legacy non sono supportati. Solo i visitatori con  ID Experience Cloud sono cuciti.
*  Analytics utilizza una suite di rapporti virtuale e un&#39;elaborazione del tempo di rapporto, con le proprie limitazioni. Per ulteriori informazioni su queste limitazioni, consulta Suite [di rapporti](../vrs/vrs-about.md) virtuali ed elaborazione [dei tempi di](../vrs/vrs-report-time-processing.md) rapporto.
* L&#39;API 1.4 non è supportata. I connettori Power BI e Generatore di report si basano entrambi sull&#39;API 1.4 e non sono quindi compatibili con CDA.
* Se l’organizzazione utilizza Private Graph, i nuovi dispositivi impiegano fino a 24 ore per essere uniti.
* I nuovi dispositivi che visitano il sito possono richiedere fino a due settimane per essere elaborati da Co-op Graph. Il livello di cucitura in CDA per le ultime due settimane è generalmente inferiore a quello degli intervalli di date superiori a due settimane.
* I dati storici nella suite di rapporti virtuali vengono modificati in base al riconoscimento e all&#39;unione dei dispositivi da parte di Adobe. I dati nella suite di rapporti di origine non vengono modificati.

Una volta che l&#39;organizzazione avrà soddisfatto tutti i requisiti e compreso i limiti, puoi iniziare a [configurare l&#39; cross-device Analytics](cda-setup.md).
