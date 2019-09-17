---
title: Domande frequenti su Analytics tra dispositivi
description: Domande frequenti per Analytics multi-dispositivo
translation-type: tm+mt
source-git-commit: e7a78c2ac21042f57487c1c230e1c96318810429

---


# Domande frequenti

> [!NOTE] La documentazione di Analytics tra dispositivi è soggetta a modifiche man mano che la funzione viene ulteriormente sviluppata. Controllate regolarmente la disponibilità di aggiornamenti.

**Come posso usare CDA per vedere come le persone si spostano da un tipo di dispositivo all'altro?**

Puoi utilizzare una visualizzazione Flusso con la dimensione Tipo dispositivo mobile.

1. Accedi ad Adobe Analytics e crea un nuovo progetto Workspace vuoto.
2. Fai clic sulla scheda Visualizzazioni a sinistra, quindi trascina una visualizzazione Flusso sul quadro a destra.
3. Fare clic sulla scheda Componenti a sinistra, quindi trascinare la dimensione 'Tipo di dispositivo mobile' nella posizione centrale denominata 'Dimensione o elemento'.
4. Questo rapporto di flusso è interattivo. Fate clic su uno dei valori per espandere i flussi alle pagine successive o precedenti. Per espandere o comprimere le colonne, usate il menu di scelta rapida. All’interno dello stesso rapporto di flusso possono essere utilizzate dimensioni diverse.

**Posso vedere in che modo le persone si spostano tra diverse esperienze utente (ad esempio browser desktop e browser mobile e app mobile)?**

L'utilizzo del tipo di dispositivo mobile come illustrato sopra consente di vedere come le persone si spostano tra i tipi di dispositivi mobili e di dispositivi desktop. Tuttavia è possibile distinguere i browser desktop dai browser mobili. Un modo per farlo è creare una eVar che registri se l'esperienza si è verificata in un browser desktop, in un browser mobile o in un'app mobile. Quindi create un diagramma di flusso come descritto sopra, utilizzando la dimensione "experience" eVar anziché la dimensione Mobile Device Type (Tipo dispositivo mobile). Questo fornisce una vista leggermente diversa sul comportamento tra dispositivi.

**Quanto tempo fa i visitatori di CDA possono contare?**

* Adobe conserva i dati relativi alle cuciture dei dispositivi per circa 30 giorni. Se un dispositivo non è inizialmente identificato dal grafico Co-op o dal grafico Privato, ma viene successivamente identificato entro 30 giorni, CDA torna indietro e riafferma che il dispositivo appartiene a una persona identificata fino a 30 giorni nel passato. Se alcuni dei comportamenti non identificati di un utente non rientrano nella finestra di lookback di 30 giorni, la parte del percorso dell'utente non viene bloccata.
* Adobe conserva le mappature dei dispositivi in Co-op Graph e Private Graph per circa 6 mesi. Un ECID che non ha attività per più di sei mesi viene rimosso dal grafico. I dati già uniti in CDA non vengono modificati, ma gli hit successivi per tale ECID vengono trattati come un nuovo individuo.

**In che modo CDA gestisce gli hit con marca temporale?**

Adobe considera gli hit con marca temporale come se fossero stati ricevuti al momento della marca temporale, non come ricevuti da Adobe. Gli hit con marca temporale maggiore di 1 mese non possono essere cuciti, in quanto non rientrano nell’intervallo di tempo, i dati utilizzati da Adobe per le cuciture sono conservati.

**Come si confronta CDA con l’ID visitatore personalizzato?**

[L’ID](../../implement/js-implementation/c-unique-visitors/visid-custom.md) visitatore personalizzato è un metodo legacy per [connettere gli utenti tra dispositivi](../../implement/js-implementation/xdevice-visid/xdevice-connecting.md). Con un ID visitatore personalizzato, utilizzate la `s.visitorID` variabile per impostare esplicitamente l’ID utilizzato per la logica del visitatore. La `s.visitorID` variabile ha la precedenza sugli ID basati su cookie presenti. Per ulteriori informazioni, consulta [Identificare visitatori](../../implement/js-implementation/c-unique-visitors/visid-overview.md) univoci nella guida Implementa.

Gli ID visitatore personalizzati hanno una serie di effetti collaterali indesiderati che CDA è progettato per superare o ridurre al minimo. Ad esempio, la metodologia ID visitatore personalizzata non dispone di funzionalità di lookback. Se un utente si autentica nel bel mezzo di una visita, la prima parte della visita associa a un ID visitatore diverso da quello dell’ultima parte della visita. Gli ID visitatore separati generano l’inflazione delle visite e dei visitatori. La finestra di lookback di 30 giorni di CDA consente di tornare indietro nel tempo per riaffermare il comportamento precedente come appartenente alla stessa persona, portando un comportamento cross-device non autenticato insieme a un comportamento cross-device autenticato con un'inflazione zero o minima.

**Posso effettuare l’aggiornamento dall’ID visitatore personalizzato a CDA?**

I clienti che già utilizzano l’ID visitatore personalizzato possono effettuare l’aggiornamento a CDA. Gli ID basati su cookie sottostanti `s.visitorID` vengono comunque sostituiti nella suite di rapporti di base. Tuttavia, all’interno della suite di rapporti virtuali, CDA ignora `s.visitorID` i dispositivi identificati dal grafico del dispositivo.

**In che modo il grafico del dispositivo gestisce i dispositivi condivisi?**

In alcune situazioni è possibile che più persone accedano dallo stesso dispositivo. Alcuni esempi includono un dispositivo condiviso a casa, PC condivisi in una libreria o un chiosco in un punto vendita. In questi casi, l’ID si sincronizza con il grafico del dispositivo da questi dispositivi condivisi per indicare che più utenti si associano a tale dispositivo nel tempo. Il grafico del dispositivo (che sia Co-op o Grafico privato) non collega l'ECID su quel dispositivo a nessuno di questi utenti. Al contrario, il grafico collega l’ECID a un "cluster" che include tutti gli utenti associati. Il grafico tenta di mantenere il cluster il più stabile possibile, anziché cambiare continuamente l'ECID tra cluster nel tempo. Di conseguenza, CDA non è in grado di distinguere i singoli utenti su un dispositivo condiviso. Tutti gli utenti del dispositivo condiviso sono considerati una singola "persona" all'interno di CDA.

**In che modo il grafico del dispositivo gestisce le situazioni in cui una singola persona dispone di MOLTI dispositivi/ECID?**

In alcune situazioni, un singolo utente può associarsi a un numero elevato di ECID. Questo può verificarsi se l'individuo utilizza molti browser o app, e può essere esacerbato se spesso cancellano i cookie o utilizzano la modalità di navigazione privata o incognito del browser. Il grafico del dispositivo limita a 200 il numero di ECID associati a un determinato ID utente. Se un ID utente si associa a troppi ECID, il grafico del dispositivo presuppone che l'ID utente non sia valido e rimuove il cluster associato a tale ID utente. L'ID utente verrà quindi inserito in una blacklist per non essere più incluso in futuro. Il risultato in CDA è che il comportamento dell'ID utente non è bloccato su più dispositivi.
