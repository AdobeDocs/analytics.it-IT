---
title: Domande frequenti su Analytics tra dispositivi
description: Domande frequenti per Analytics multi-dispositivo
translation-type: tm+mt
source-git-commit: d847fb9dc1427727a0162be993ddc4a73c52f192
workflow-type: tm+mt
source-wordcount: '1185'
ht-degree: 0%

---


# Domande frequenti

**Come posso usare CDA per vedere come le persone si spostano da un tipo di dispositivo all&#39;altro?**

Puoi utilizzare una visualizzazione Flusso con la dimensione Tipo dispositivo mobile.

1. Accedi ad Adobe Analytics e crea un nuovo progetto Workspace vuoto.
2. Fai clic sulla scheda Visualizzazioni a sinistra, quindi trascina una visualizzazione Flusso sul quadro a destra.
3. Fare clic sulla scheda Componenti a sinistra, quindi trascinare la dimensione &#39;Tipo di dispositivo mobile&#39; nella posizione centrale denominata &#39;Dimensione o elemento&#39;.
4. Questo rapporto di flusso è interattivo. Fate clic su uno dei valori per espandere i flussi alle pagine successive o precedenti. Per espandere o comprimere le colonne, usate il menu di scelta rapida. All’interno dello stesso rapporto di flusso possono essere utilizzate dimensioni diverse.

**Posso vedere in che modo le persone si spostano tra diverse esperienze utente (ad es. browser desktop e browser mobile e app mobile)?**

L&#39;utilizzo del tipo di dispositivo mobile come illustrato sopra consente di vedere come le persone si spostano tra i tipi di dispositivi mobili e di dispositivi desktop. Tuttavia è possibile distinguere i browser desktop dai browser mobili. Un modo per farlo è creare una eVar che registri se l&#39;esperienza si è verificata in un browser desktop, in un browser mobile o in un&#39;app mobile. Quindi create un diagramma di flusso come descritto sopra, utilizzando la dimensione &quot;experience&quot; eVar anziché la dimensione Mobile Device Type (Tipo dispositivo mobile). Questo fornisce una vista leggermente diversa sul comportamento tra dispositivi.

**Quanto tempo fa i visitatori di CDA possono contare?**

* Adobe conserva i dati relativi alle cuciture dei dispositivi per circa 30 giorni. Se un dispositivo non è inizialmente identificato dal grafico Co-op o dal grafico Privato, ma viene successivamente identificato entro 30 giorni, CDA torna indietro e riafferma che il dispositivo appartiene a una persona identificata fino a 30 giorni nel passato. Se alcuni dei comportamenti non identificati di un utente non rientrano nella finestra di lookback di 30 giorni, la parte del percorso dell&#39;utente non viene bloccata.
* Adobe conserva le mappature dei dispositivi in Co-op Graph e Private Graph per circa 6 mesi. Un ECID che non ha attività per più di sei mesi viene rimosso dal grafico. I dati già cuciti in CDA non vengono modificati, ma gli hit successivi per tale ECID vengono trattati come un nuovo individuo.

**In che modo CDA gestisce gli hit con marca temporale?**

Adobe considera gli hit con marca temporale come se fossero stati ricevuti al momento della marca temporale, non come ricevuti da Adobe. Gli hit con marca temporale maggiore di 1 mese non possono essere cuciti, in quanto non rientrano nell’intervallo di tempo, i dati utilizzati da Adobe per le cuciture sono conservati.

**In che modo CDA si confronta con gli ID visitatore personalizzati?**

[L’ID](/help/implement/vars/config-vars/visitorid.md) visitatore personalizzato è un metodo legacy per [connettere gli utenti tra dispositivi](/help/implement/js/xdevice-visid/xdevice-connecting.md). Con un ID visitatore personalizzato, utilizzate la `s.visitorID` variabile per impostare esplicitamente l’ID utilizzato per la logica del visitatore. La `s.visitorID` variabile ha la precedenza sugli ID basati su cookie presenti.

Gli ID visitatore personalizzati hanno diversi effetti collaterali indesiderati che CDA supera o riduce al minimo. Ad esempio, la metodologia ID visitatore personalizzata non dispone di funzionalità di lookback. Se un utente si autentica nel bel mezzo di una visita, la prima parte della visita associa a un ID visitatore diverso da quello dell’ultima parte della visita. Gli ID visitatore separati generano l’inflazione delle visite e dei visitatori. La finestra di lookback di 30 giorni di CDA consente di tornare indietro nel tempo per riaffermare il comportamento precedente come appartenente alla stessa persona, portando un comportamento cross-device non autenticato insieme a un comportamento cross-device autenticato con un&#39;inflazione zero o minima.

**Posso effettuare l’aggiornamento dall’ID visitatore personalizzato a CDA?**

I clienti che già utilizzano l’ID visitatore personalizzato possono effettuare l’aggiornamento a CDA. Gli ID basati su cookie sottostanti `s.visitorID` vengono comunque sostituiti nella suite di rapporti di base. Tuttavia, all’interno della suite di rapporti virtuali, CDA ignora `s.visitorID` i dispositivi identificati dal grafico del dispositivo.

**In che modo il grafico del dispositivo gestisce i dispositivi condivisi?**

In alcune situazioni è possibile che più persone accedano dallo stesso dispositivo. Alcuni esempi includono un dispositivo condiviso a casa, PC condivisi in una libreria o un chiosco in un punto vendita. In questi casi, l’ID si sincronizza con il grafico del dispositivo da questi dispositivi condivisi per indicare che più utenti si associano a tale dispositivo nel tempo. Il grafico del dispositivo (che sia Co-op o Grafico privato) non collega l&#39;ECID su quel dispositivo a nessuno di questi utenti. Al contrario, il grafico collega l’ECID a un &quot;cluster&quot; che include tutti gli utenti associati. Il grafico tenta di mantenere il cluster il più stabile possibile, anziché cambiare continuamente l&#39;ECID tra cluster nel tempo. Di conseguenza, CDA non è in grado di distinguere i singoli utenti su un dispositivo condiviso. Tutti gli utenti del dispositivo condiviso sono considerati una singola &quot;persona&quot; all&#39;interno di CDA.

**In che modo il grafico del dispositivo gestisce le situazioni in cui una singola persona dispone di MOLTI dispositivi/ECID?**

In alcune situazioni, un singolo utente può associarsi a un numero elevato di ECID. Questo può verificarsi se l&#39;individuo utilizza molti browser o app, e può essere esacerbato se spesso cancellano i cookie o utilizzano la modalità di navigazione privata o incognito del browser. Il grafico del dispositivo limita a 200 il numero di ECID associati a un determinato ID utente. Se un ID utente si associa a troppi ECID, il grafico del dispositivo presuppone che l&#39;ID utente non sia valido e rimuove il cluster associato a tale ID utente. L&#39;ID utente verrà quindi inserito in una blacklist per non essere più incluso in futuro. Il risultato in CDA è che il comportamento dell&#39;ID utente non è bloccato su più dispositivi.

**Qual è la differenza tra la metrica &#39;Persone&#39; in CDA e la metrica &#39;Visitatori unici&#39; all&#39;esterno di CDA?**

La metrica &quot;Persone&quot; è simile alla metrica &quot;Visitatori unici&quot;, in quanto segnala il numero di individui univoci. Tuttavia, quando si utilizza Analytics tra dispositivi, i visitatori univoci vengono combinati quando altrimenti vengono registrati come due visitatori univoci separati al di fuori di CDA. La metrica &#39;Persone&#39; sostituisce la metrica &#39;Visitatori unici&#39; quando è abilitata l&#39;analisi tra dispositivi.

**Qual è la differenza tra la metrica &quot;Dispositivi univoci&quot; in CDA e la metrica &quot;Visitatori unici&quot; al di fuori di CDA?**

Queste due metriche sono approssimativamente equivalenti tra loro.

**Posso includere le metriche CDA utilizzando l&#39;API 2.0?**

Sì. Analysis Workspace utilizza l’API 2.0 per richiedere dati dai server Adobe e puoi visualizzare le chiamate API che Adobe usa per creare i tuoi rapporti:

1. Effettuando l’accesso ad Analysis Workspace, apri gli strumenti di sviluppo del browser (F12 per la maggior parte dei browser).
1. Nella console del browser, digitate `adobeTools.showDebugger()`. La pagina viene ricaricata con le icone di debug nell’angolo superiore destro di ciascun pannello.
1. Fate clic sull&#39;icona di debug nel pannello desiderato, quindi selezionate la visualizzazione desiderata e l&#39;ora della richiesta.
1. Individuate la richiesta JSON, che potete utilizzare nella chiamata API ad Adobe.

**Analytics cross-device può unire visitatori univoci. Può fare visite insieme?**

Sì. Se un singolo utente invia hit da due dispositivi separati entro il timeout di visita della suite di rapporti virtuale (per impostazione predefinita, 30 minuti), viene bloccato nella stessa visita.

**Qual è l’ID visitatore finale utilizzato da CDA? Posso esportarlo da Adobe Analytics?**

Analytics tra dispositivi calcola i dati uniti utilizzando un &quot;ID cluster&quot;. Questo identificatore viene calcolato da Adobe al momento dell&#39;esecuzione del rapporto, noto anche come elaborazione del rapporto. La natura dell&#39;elaborazione del tempo per i report implica che non è compatibile con Data Warehouse, feed di dati o altre funzioni di esportazione offerte da Adobe.
