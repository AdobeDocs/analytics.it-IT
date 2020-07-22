---
title: Domande frequenti su Analytics tra dispositivi
description: Domande frequenti per Analytics  cross-device
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '1298'
ht-degree: 0%

---


# Domande frequenti

## Come posso usare CDA per vedere come le persone si spostano da un tipo di dispositivo all&#39;altro?

Puoi utilizzare una visualizzazione Flusso con la dimensione Tipo dispositivo mobile.

1. Accedi ad Adobe  Analytics e crea un nuovo progetto Workspace vuoto.
2. Fai clic sulla scheda Visualizzazioni a sinistra, quindi trascina una visualizzazione Flusso sul quadro a destra.
3. Fare clic sulla scheda Componenti a sinistra, quindi trascinare la dimensione &#39;Tipo di dispositivo mobile&#39; nella posizione centrale denominata &#39;Dimensione o elemento&#39;.
4. Questo rapporto di flusso è interattivo. Fate clic su uno dei valori per espandere i flussi alle pagine successive o precedenti. Per espandere o comprimere le colonne, usate il menu di scelta rapida. All’interno dello stesso rapporto di flusso possono essere utilizzate dimensioni diverse.

## Posso vedere in che modo le persone si spostano tra diverse esperienze utente (ad es. browser desktop e browser mobile e app mobile)?

L&#39;utilizzo del tipo di dispositivo mobile come illustrato sopra consente di vedere come le persone si spostano tra i tipi di dispositivi mobili e di dispositivi desktop. Tuttavia è possibile distinguere i browser desktop dai browser mobili. Un modo per farlo è creare una eVar che registri se l&#39;esperienza si è verificata in un browser desktop, in un browser mobile o in un&#39;app mobile. Quindi create un diagramma di flusso come descritto sopra, utilizzando la dimensione &quot;experience&quot; eVar anziché la dimensione Mobile Device Type (Tipo dispositivo mobile). Questo fornisce una vista leggermente diversa sul comportamento tra dispositivi.

## Quanto tempo fa i visitatori di CDA possono contare?

Adobe conserva i dati relativi alle cuciture dei dispositivi per circa 30 giorni. Se un dispositivo non viene inizialmente identificato ma viene successivamente identificato entro 30 giorni, CDA torna indietro e riafferma che il dispositivo appartiene a una persona identificata fino a 30 giorni nel passato. Se alcuni dei comportamenti non identificati di un utente non rientrano nella finestra di lookback di 30 giorni, la parte del percorso dell&#39;utente non viene bloccata.

* **Se si utilizza un grafico** del dispositivo, Adobe mantiene le mappature dei dispositivi in Co-op Graph e Private Graph per circa 6 mesi. Un ECID che non ha attività per più di sei mesi viene rimosso dal grafico. I dati già cuciti in CDA non vengono modificati, ma gli hit successivi per tale ECID vengono trattati come una nuova persona.

## In che modo CDA gestisce gli hit con marca temporale?

Adobe considera gli hit con marca temporale come se fossero stati ricevuti al momento della marca temporale, non come ricevuti da Adobe. Gli hit con marca temporale maggiore di 1 mese non vengono mai cuciti in quanto non rientrano nell’intervallo di tempo utilizzato da Adobe per le cuciture.

## In che modo CDA si confronta con gli ID visitatore personalizzati?

L’utilizzo di un ID visitatore personalizzato è un metodo legacy per [connettere gli utenti tra dispositivi](/help/implement/js/xdevice-visid/xdevice-connecting.md). Con un ID visitatore personalizzato, utilizzate la [`visitorID`](/help/implement/vars/config-vars/visitorid.md) variabile per impostare esplicitamente l’ID utilizzato per la logica del visitatore. La `visitorID` variabile ha la precedenza sugli ID basati su cookie presenti.

Gli ID visitatore personalizzati hanno diversi effetti collaterali indesiderati che CDA supera o riduce al minimo. Ad esempio, la metodologia ID visitatore personalizzata non dispone di funzionalità di [ripetizione](replay.md) . Se un utente si autentica nel bel mezzo di una visita, la prima parte della visita associa a un ID visitatore diverso da quello dell’ultima parte della visita. Gli ID visitatore separati generano l’inflazione delle visite e dei visitatori. CDA ridefinisce i dati storici in modo che gli hit non autenticati appartengano alla persona corretta.

## Posso effettuare l’aggiornamento dall’ID visitatore personalizzato a CDA?

I clienti che già utilizzano l’ID visitatore personalizzato possono effettuare l’aggiornamento a CDA senza alcuna modifica di implementazione. La `visitorID` variabile viene ancora utilizzata nella suite di rapporti di origine. Tuttavia, CDA ignora la `visitorID` variabile nella suite di rapporti virtuali se un utente si autentica.

## In che modo il grafico del dispositivo gestisce i dispositivi condivisi?

In alcune situazioni è possibile che più persone accedano dallo stesso dispositivo. Alcuni esempi includono un dispositivo condiviso a casa, PC condivisi in una libreria o un chiosco in un punto vendita.

* **Se si utilizza un grafico** del dispositivo, la capacità di gestire i dispositivi condivisi è limitata. Il grafico del dispositivo utilizza un algoritmo per determinare la proprietà di un &quot;cluster&quot; e può cambiare ogni volta che il cluster viene pubblicato. Gli utenti del dispositivo condiviso sono soggetti al cluster a cui appartengono.
* **Se si utilizza la cucitura** basata su campo, la prop o eVar scelta aiuterà a identificare gli utenti connessi sostituendo altri identificatori. I dispositivi condivisi vengono considerati persone separate, anche se provengono dallo stesso dispositivo.

## In che modo CDA gestisce le situazioni in cui una singola persona dispone di MOLTI dispositivi/ECID?

In alcune situazioni, un singolo utente può associarsi a un numero elevato di ECID. Questo può verificarsi se l&#39;individuo utilizza molti browser o app, e può essere esacerbato se spesso cancellano i cookie o utilizzano la modalità di navigazione privata o incognito del browser.

* **Se si utilizza un grafico** del dispositivo, CDA limita a 50 il numero di ECID che si collega a un dato ID utente. Se un ID utente si associa a troppi ECID, il grafico del dispositivo presuppone che l&#39;ID utente non sia valido e rimuove il cluster associato a tale ID utente. L&#39;ID utente viene quindi aggiunto a un inserire nell&#39;elenco Bloccati di  per impedirne l&#39;aggiunta a eventuali cluster in futuro. Il risultato nel reporting è che l&#39;ID utente non viene unito tra i dispositivi.
* **Se si utilizza la cucitura** basata su campo, il numero di dispositivi è irrilevante a favore della prop/eVar scelta per aiutare a identificare gli utenti connessi. Un singolo utente può appartenere a un numero qualsiasi di dispositivi, senza che ciò comprometta la capacità di CDA di cucire tra i dispositivi.

## Qual è la differenza tra la metrica Persone in CDA e la metrica Visitatori unici al di fuori di CDA?

La metrica [Persone](/help/components/metrics/people.md) è simile alla metrica Visitatori [](/help/components/metrics/unique-visitors.md) unici, in quanto segnala il numero di individui univoci. Tuttavia, quando si utilizza Cross-Device  Analytics, i visitatori univoci vengono combinati quando altrimenti vengono registrati come due visitatori univoci separati al di fuori di CDA. La metrica &quot;Persone&quot; sostituisce la metrica &quot;Visitatori unici&quot; quando è abilitato  Analytics tra dispositivi.

## Qual è la differenza tra la metrica &quot;Dispositivi univoci&quot; in CDA e la metrica &quot;Visitatori unici&quot; al di fuori di CDA?

Queste due metriche sono approssimativamente equivalenti tra loro.

## Posso includere le metriche CDA utilizzando l&#39;API 2.0?

Sì.  Analysis Workspace utilizza l&#39;API 2.0 per richiedere dati dai server Adobe, e puoi visualizzare le chiamate API che Adobe usa per creare i tuoi rapporti:

1. Effettuando l&#39;accesso a  Analysis Workspace, andate a [!UICONTROL Help] > [!UICONTROL Enable debugger].
2. Fate clic sull&#39;icona di debug nel pannello desiderato, quindi selezionate la visualizzazione desiderata e l&#39;ora della richiesta.
3. Individuate la richiesta JSON, che potete utilizzare nella chiamata API ad Adobe.

## Cross-Device  Analytics può unire visitatori univoci. Può fare visite insieme?

Sì. Se un singolo utente invia hit da due dispositivi separati entro il timeout di visita della suite di rapporti virtuale (per impostazione predefinita, 30 minuti), viene bloccato nella stessa visita.

## Qual è l’ID visitatore finale utilizzato da CDA? Posso esportarlo da Adobe  Analytics?

* **Se si utilizza un grafico** del dispositivo, un ID personalizzato basato sul cluster è l&#39;identificatore principale.
* **Se si utilizza la cucitura** basata su un campo, l’identificatore principale è un ID personalizzato basato sulla prop/eVar scelta.

Entrambi gli identificatori vengono calcolati da Adobe al momento dell&#39;esecuzione del rapporto, noto anche come elaborazione [del tempo di](../vrs/vrs-report-time-processing.md)rapporto. La natura dell&#39;elaborazione del tempo per i report implica che non è compatibile con Date warehouse, feed di dati o altre funzioni di esportazione offerte da Adobe.

## Come posso passare dal grafico del dispositivo alla cucitura basata sul campo o viceversa?

Per cambiare i metodi di identificazione CDA, rivolgiti all&#39;Account Manager della tua organizzazione. L&#39;Account Manager può fornire alla suite di rapporti il metodo desiderato per identificare le persone. *I dati storici cuciti dal metodo precedente vengono persi.*

## In che modo Adobe gestisce i limiti univoci per un&#39;eVar utilizzata nelle cuciture basate sul campo?

CDA richiama elementi dimensione eVar prima di essere ottimizzati per la generazione di rapporti. Non devi preoccuparti di limiti unici ai fini di CDA. Tuttavia, se avete provato a utilizzare tale prop/eVar in un progetto Workspace, potete comunque visualizzare l’elemento dimensione [(traffico limitato)](/help/technotes/low-traffic.md) .
