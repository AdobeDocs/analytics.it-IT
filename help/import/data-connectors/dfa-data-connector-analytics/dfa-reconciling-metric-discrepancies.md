---
description: Talvolta, alcune metriche potrebbero non rientrare in una differenza accettabile quando si confrontano metriche Adobe Analytics con metriche DFA. Di seguito è riportato un elenco delle definizioni delle metriche e dei possibili motivi delle varianti.
keywords: DFAE
seo-description: Talvolta, alcune metriche potrebbero non rientrare in una differenza accettabile quando si confrontano metriche Adobe Analytics con metriche DFA. Di seguito è riportato un elenco delle definizioni delle metriche e dei possibili motivi delle varianti.
seo-title: Riconciliazione delle discrepanze metriche
solution: Analytics
title: Riconciliazione delle discrepanze metriche
topic: Connettori dati
uuid: aa3ca006-d3cf-410e-a000-781ab17fb9e3
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# Riconciliazione delle discrepanze metriche{#reconciling-metric-discrepancies}

Talvolta, alcune metriche potrebbero non rientrare in una differenza accettabile quando si confrontano metriche Adobe Analytics con metriche DFA. Di seguito è riportato un elenco delle definizioni delle metriche e dei possibili motivi delle varianti.

Questa sezione include i seguenti argomenti:

## Definizione delle metriche{#metric-definitions}

Adobe utilizza i seguenti termini quando si parla di metriche correlate all’integrazione DFA:

**Impressioni**: Le impression fanno riferimento al numero di volte in cui un annuncio è stato visualizzato. Le impression vengono riportate in base agli annunci, ma possono anche essere aggregate in gruppi di annunci o altri raggruppamenti con più annunci. La metrica impression in Analytics viene importata dal DFA tramite l’importazione notturna di origini dati.

**Clic**: I clic fanno riferimento al numero di volte in cui è stato fatto clic su un annuncio, come rapporto del DFAE. I clic vengono registrati nella pagina di reindirizzamento del DFAE prima della destinazione del visitatore sul sito Web del cliente. Come per le impression, la metrica dei clic in Analytics viene importata dal DFA tramite un'importazione notturna di origini dati.

**Click-through**: Click-through indica il numero di volte in cui l’utente è arrivato alla pagina di destinazione dopo aver fatto clic su un annuncio. Questa metrica può essere leggermente diversa dai clic.

**Visualizza-Attraverso**: View-Throughs indica il numero di volte in cui un visitatore è arrivato sul sito Web del cliente dopo aver visualizzato un annuncio, ma NON avendo fatto clic su di esso. Il visitatore deve trovarsi nel sito all’interno della finestra di visualizzazione, che per impostazione predefinita è impostata su 30 giorni. L'impressione deve essere avvenuta più di recente dell'ultimo clic. Le visualizzazioni vengono registrate una volta per campagna, per visita e vengono conteggiate quando l'integrazione compila l'eVar di visualizzazione-through con l'ID campagna DFA e l'evento di visualizzazione-through è impostato.

## Possibili ragioni di discrepanze{#possible-reasons-for-discrepancies}

Elenca una serie di motivi per cui possono verificarsi discrepanze di dati tra i rapporti Adobe Analytics e DFA.

### Utenti sul browser Safari e altri browser che bloccano i cookie 3rd-party {#section-4b0dc429a54a4744a33976b0bb2d1b2a}

L'accettazione di cookie di terze parti è in genere la causa maggiore di discrepanza tra Adobe Analytics e DFA. Per impostazione predefinita, Safari e altri browser bloccano i cookie di terze parti. Questo significa che per impostazione predefinita, Safari accetta il cookie di prima parte utilizzato dalla maggior parte delle implementazioni di Analytics, ma rifiuta il cookie di terza parte utilizzato dal DFA.

Un esempio di dati dai nostri clienti beta di Analytics 15 mostrava meno dello 0,5% degli utenti che generalmente rifiutano i cookie di prime parti, mentre il 5-12% rifiutano i cookie di terze parti (molti di questi rifiuti sono probabilmente dovuti alle impostazioni predefinite del browser).

Questa discrepanza può comportare una grande differenza nei dati raccolti da Analytics e DFA.

### Perché le impression riportate nel DFA potrebbero essere superiori a quelle riportate in Adobe Analytics? {#section-db0ad070a65a4985bcc589b2d0d30b90}

* Il DFA invia i dati ai server di raccolta dati Adobe in batch notturno, in modo che i dati di impression in Analytics possano trovarsi fino a 2 giorni prima dei rapporti DFA.
* Adobe utilizza le classificazioni SAINT per classificare i codici di monitoraggio DFA importati in vari livelli di aggregazioni (nome campagna, nome posizionamento, nome annuncio, ecc.) Se la discrepanza viene visualizzata durante l'esecuzione di un rapporto di classificazione, eseguite un semplice test per verificare se le classificazioni non hanno ancora raggiunto le metriche importate:

   * Nel rapporto classificazione, individuare un elemento di riga denominato "None".
   * Suddivide l’elemento riga per la stessa variabile, utilizzando il rapporto ID DFA non elaborato (ad esempio, ID campagna).
   * In questo rapporto, prendere nota di eventuali codici di monitoraggio DFA non classificati presenti nel modulo `DFA:XXXXX:XXXXX`.
   * Se esistono molti di questi codici di monitoraggio, controllate il processo di classificazione SAINT notturno.

### Perché i clic DFA potrebbero essere superiori ai click-through di Adobe Analytics? {#section-2fce4608ed044bdc9cf812cb719d5d35}

* Il DFA registra un clic prima che il visitatore arrivi sul sito Web del cliente. I record di Analytics Click-through dopo che la pagina di destinazione carica ed esegue il beacon Adobe JavaScript. In genere, si verificano delle discrepanze perché il visitatore non arriva alla pagina di destinazione dopo che il DFA tiene traccia di un clic, oppure il `s.maxDelay` timer viene colpito.
* Assicurati che tutti i posizionamenti e le creatività nella configurazione di Floodlight includano clickThroughParam nell’URL della pagina di destinazione (ad esempio "`?CID=1`"). Se non viene impostato questo parametro, il codice JavaScript di Adobe Analytics non riuscirà a ricevere i click-through che si verificano dopo il primo hit della visita.
* Assicurati che tutti i posizionamenti e le creazioni abbiano una pagina di destinazione con tag JavaScript e il modulo Integrate DFA, e che l’ID di configurazione del faro in quella pagina di destinazione corrisponda all’ID di configurazione del faro degli annunci serviti. Spesso, le discrepanze sono dovute al fatto che la pagina di destinazione degli annunci è impostata su un sito di terze parti o sugli annunci serviti.
* Se utilizzate annunci multimediali avanzati o annunci Flash (swf), accertatevi che ogni volta che viene premuto il Clicktracker del DFA, il browser del visitatore venga reindirizzato alla pagina di destinazione con il `clickThroughParam` contenuto nella stringa di query. Se il browser non viene reindirizzato, non verrà registrato alcun click-through.
* I timeout rappresentano le istanze in cui i dati DFA potrebbero essere stati disponibili ma il codice JavaScript non ha ricevuto una risposta in tempo. Quando un visitatore arriva sulla pagina di destinazione, Adobe JavaScript richiede le informazioni del visitatore dal servizio fls.doubleclick.net del DFA. Il `s.maxDelay` parametro determina per quanto tempo JavaScript attende i dati FLS (Floodlight Service). Se `s.maxDelay` è troppo alto, i visitatori possono lasciare il sito prima che Adobe raccolga i dati dell’hit; che significa che non vengono registrati dati di clic. Se `s.maxDelay` è impostato su un valore troppo basso, la connessione Internet del visitatore non può recuperare i dati FLS in tempo; che significa che l’hit viene inviato ad Adobe senza informazioni sul clic del DFA.
* Il traffico dei bot potrebbe gonfiare i numeri di clic del DFAE. I bot possono avere funzionalità per fare clic su un annuncio, ma potrebbero non essere complessi per eseguire un beacon Analytics o attivare il tag script sincrono per caricare i dati della richiesta dei server di Floodlight. Se questi bot non vengono rimossi dalla figura Clic, potrebbe essere una discrepanza.
* I visitatori che lasciano la pagina prima della `s.maxDelay` scadenza e che restituiscono dati DFA andranno perduti; per loro non verranno raccolti dati DFA o visitatore.
* Analytics tenta di identificare e rimuovere i Click-through duplicati in modo che vengano conteggiati una sola volta per ogni campagna per visita. Il DFA conta i visitatori che fanno clic su "Indietro" e passano attraverso il reindirizzamento dell'annuncio più volte come clic ACM aggiuntivi, mentre Analytics non li conta come più click-through.
* I tag DFA Floodlight non si basano sull'abilitazione di JavaScript, mentre Analytics no. A causa di questo, in alcuni casi il DFA registra un hit quando Analytics non lo fa. Per identificare se questo potrebbe essere un problema, usa il rapporto JavaScript di Analytics nel menu Profilo visitatore.

### Perché le attività di post-impressione DFA potrebbero essere superiori alle visualizzazioni di Adobe Analytics? {#section-5daa91039c404df48b6a3447c20406f7}

* Analytics tenta di identificare e rimuovere i Click-through duplicati in modo che vengano conteggiati una sola volta per ogni campagna per visita. Il DFA conta i visitatori che fanno clic su "Indietro" e passano attraverso il reindirizzamento dell'annuncio più volte come clic ACM aggiuntivi, mentre Analytics non li conta come più click-through.
* I tag DFA Floodlight non si basano su JavaScript disabilitato, mentre Analytics no. A causa di questo, in alcuni casi il DFA registra un hit quando Analytics non lo fa.
* Il DFA conta le attività Post-impression quando si utilizzano i tag Floodlight, che possono essere posizionati sul sito Web client. Analytics conta i casi di visualizzazione dopo l’esecuzione del beacon JavaScript (richiesta immagine). La posizione del codice nella pagina Web può determinare se un caricamento di pagina interrotto viene conteggiato come attività Post-impression o come visualizzazione.

### Cosa succede se le discrepanze sono ben al di fuori di un intervallo accettabile e le possibili ragioni sopra indicate non si applicano? {#section-ca50eb75dd5d4d0396f4668b44d7547c}

Consulta il tuo Consulente per l'integrazione o Adobe Client Care per documentare le discrepanze e segnalarle al team di progettazione dei connettori dati. Per accelerare la richiesta, fai confrontare i dati in questione tra 2 e 3 giorni (a livello di codice della campagna). Nella richiesta, identificate tutte le azioni che avete già intrapreso per riconciliare la discrepanza.
