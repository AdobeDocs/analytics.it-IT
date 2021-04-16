---
description: Talvolta, alcune metriche potrebbero non rientrare in una differenza accettabile quando si confrontano metriche di Adobe Analytics con metriche DFA. Di seguito è riportato un elenco delle definizioni delle metriche e dei possibili motivi delle varianze.
keywords: DFA
title: Riconciliazione delle discrepanze metriche
feature: Data Connectors
uuid: aa3ca006-d3cf-410e-a000-781ab17fb9e3
exl-id: bfe0f9cb-1bbc-40f9-b996-0002d5143889
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '1270'
ht-degree: 0%

---

# Riconciliazione delle discrepanze metriche{#reconciling-metric-discrepancies}

Talvolta, alcune metriche potrebbero non rientrare in una differenza accettabile quando si confrontano metriche di Adobe Analytics con metriche DFA. Di seguito è riportato un elenco delle definizioni delle metriche e dei possibili motivi delle varianze.

Questa sezione include i seguenti argomenti:

## Definizione delle metriche{#metric-definitions}

Adobe utilizza i termini seguenti quando si parla di metriche relative all’integrazione DFA:

**Impression**: Le impression si riferiscono al numero di volte in cui un annuncio è stato visualizzato. Le impressioni sono riportate in base a un annuncio per annuncio, ma possono anche essere aggregate in gruppi di annunci o altri raggruppamenti con più annunci. La metrica impression in Analytics viene importata da DFA tramite un’importazione notturna di origini dati.

**Clic**: I clic si riferiscono al numero di volte in cui un annuncio è stato fatto clic, come rapporto di DFA. I clic vengono registrati nella pagina di reindirizzamento DFA prima che il visitatore arrivi sul sito web del cliente. Come per le impression, la metrica dei clic in Analytics viene importata da DFA tramite un’importazione notturna di origini dati.

**Click-through**: Click-through fa riferimento al numero di volte in cui l’utente è arrivato alla pagina di destinazione dopo aver fatto clic su un annuncio. Questa metrica può essere leggermente diversa dai clic.

**View-Throughs**: View-Throughs si riferisce al numero di volte in cui un visitatore è andato al sito Web del cliente dopo aver visualizzato un annuncio, ma NON aver fatto clic sull&#39;annuncio. Il visitatore deve accedere al sito all’interno della finestra di visualizzazione, che per impostazione predefinita è impostata su 30 giorni. L&#39;impressione deve essere avvenuta più di recente dell&#39;ultimo clic. Le visualizzazioni vengono registrate una volta per campagna, per visita e vengono conteggiate quando l’integrazione compila l’eVar di visualizzazione view-through con l’ID della campagna DFA e l’evento view-through viene impostato.

## Possibili motivi per discrepanze{#possible-reasons-for-discrepancies}

Elenca una serie di motivi per cui possono verificarsi discrepanze di dati tra i rapporti Adobe Analytics e DFA.

### Utenti sul browser Safari e altri browser che bloccano i cookie di terze parti {#section-4b0dc429a54a4744a33976b0bb2d1b2a}

L’accettazione di cookie di terze parti è in genere la causa più grande di discrepanza tra Adobe Analytics e DFA. Per impostazione predefinita, Safari e altri browser bloccano i cookie di terze parti. Questo significa che, per impostazione predefinita, Safari accetta il cookie di prima parte utilizzato dalla maggior parte delle implementazioni di Analytics, ma rifiuta il cookie di terze parti utilizzato da DFA.

Un esempio di dati dai nostri clienti beta di Analytics 15 mostrava meno dello 0,5% degli utenti che generalmente rifiutano i cookie di prime parti, mentre il 5-12% rifiuta i cookie di terze parti (molti di questi rifiuti sono probabilmente dovuti alle impostazioni predefinite del browser).

Questa discrepanza può comportare una grande differenza nei dati raccolti da Analytics e DFA.

### Perché le impression riportate in DFA potrebbero essere più alte delle impression riportate in Adobe Analytics? {#section-db0ad070a65a4985bcc589b2d0d30b90}

* DFA invia i dati ai server di raccolta dati di Adobe in un batch notturno, in modo che i dati sulle impression in Analytics possano trascorrere fino a 2 giorni dai rapporti DFA.
* Adobe utilizza le classificazioni di SAINT per classificare i codici di tracciamento DFA importati in vari livelli di aggregazioni (nome della campagna, nome del posizionamento, nome dell’annuncio, ecc.) Se viene visualizzata una discrepanza durante l’esecuzione di un rapporto di classificazione, esegui un semplice test per verificare se le classificazioni non hanno ancora raggiunto le metriche importate:

   * Nel rapporto di classificazione, individua una riga denominata &quot;None&quot;.
   * Effettua un raggruppamento dell’elemento riga in base alla stessa variabile, utilizzando il rapporto ID DFA non elaborato (come ID campagna).
   * In questo rapporto, prendi nota di eventuali codici di tracciamento DFA non classificati sotto forma di `DFA:XXXXX:XXXXX`.
   * Se esistono molti di questi codici di tracciamento, esamina il processo di classificazione SAINT notturno.

### Perché i clic DFA potrebbero essere più alti dei click-through Adobe Analytics? {#section-2fce4608ed044bdc9cf812cb719d5d35}

* DFA registra un clic prima che il visitatore arrivi sul sito web del cliente. Analytics registra il click-through dopo che la pagina di destinazione carica ed esegue il beacon JavaScript di Adobe. In genere, si verificano delle discrepanze perché il visitatore non arriva alla pagina di destinazione dopo che DFA tiene traccia di un clic o quando viene premuto il timer `s.maxDelay`.
* Assicurati che tutti i posizionamenti e le creatività nella configurazione del faro includano clickThroughParam nell&#39;URL della pagina di destinazione (ad esempio &quot;`?CID=1`&quot;). Se non si imposta questo parametro, il JavaScript di Adobe Analytics non noterà alcun click-through che si verifica dopo il primo hit della visita.
* Assicurati che tutti i posizionamenti e i creativi abbiano una pagina di destinazione con tag JavaScript e il modulo Integrato DFA, e che l’ID di configurazione di Floodlight in quella pagina di destinazione corrisponda all’ID di configurazione di Floodlight degli annunci serviti. Spesso le discrepanze si verificano perché la pagina di destinazione degli annunci è impostata su un sito di terze parti o sugli annunci serviti.
* Se utilizzi annunci Rich Media o annunci di Flash (swf), assicurati che ogni volta che viene premuto il clicktracker DFA, anche il browser del visitatore venga reindirizzato alla pagina di destinazione con il `clickThroughParam` incluso nella stringa di query. Se il browser non viene reindirizzato, non viene registrato alcun click-through.
* I timeout rappresentano istanze in cui i dati DFA potrebbero essere stati disponibili ma il codice JavaScript non ha ricevuto una risposta in tempo. Quando un visitatore arriva sulla pagina di destinazione, Adobe JavaScript richiede le informazioni del visitatore dal servizio fls.doubleclick.net di DFA. Il parametro `s.maxDelay` determina per quanto tempo JavaScript attende i dati del servizio Floodlight (FLS). Se `s.maxDelay` è troppo alto, i visitatori possono lasciare il sito prima che Adobe raccolga i dati degli hit; significa che non vengono registrati dati di clic. Se `s.maxDelay` è impostato su un valore troppo basso, la connessione Internet del visitatore non può recuperare i dati FLS in tempo; significa che l’hit viene inviato ad Adobe senza informazioni di clic DFA.
* Il traffico dei bot potrebbe gonfiare i numeri di clic del DFA. I bot possono disporre di funzionalità per fare clic su un annuncio, ma potrebbero non avere la complessità per eseguire un beacon di Analytics o attivare il tag script sincrono per caricare i dati della richiesta dei server di Floodlight. Se questi robot non vengono rimossi dalla figura Clic, potrebbe essere una causa di discrepanza.
* I visitatori che lasciano la pagina prima della scadenza di `s.maxDelay` e la restituzione dei dati DFA andranno perduti; per loro non verranno raccolti dati DFA o visitatore.
* Analytics tenta di identificare e rimuovere i click-through duplicati in modo che vengano conteggiati una sola volta per campagna per visita. DFA conta i visitatori che fanno clic su &quot;Indietro&quot; e passano attraverso l’annuncio reindirizzato più volte come clic ACM aggiuntivi, mentre Analytics non li considera come più click-through.
* I tag DFA Floodlight non si basano sull’abilitazione di JavaScript, mentre Analytics lo fa. Per questo motivo, in alcuni casi in cui il DFA registra un hit quando Analytics non lo fa. Per identificare se questo potrebbe essere un problema, utilizza il rapporto JavaScript di Analytics nel menu Profilo visitatore .

### Perché le attività di post-impression DFA potrebbero essere più alte delle visualizzazioni-through di Adobe Analytics? {#section-5daa91039c404df48b6a3447c20406f7}

* Analytics tenta di identificare e rimuovere i click-through duplicati in modo che vengano conteggiati una sola volta per campagna per visita. DFA conta i visitatori che fanno clic su &quot;Indietro&quot; e passano attraverso l’annuncio reindirizzato più volte come clic ACM aggiuntivi, mentre Analytics non li considera come più click-through.
* I tag DFA Floodlight non si basano su JavaScript disabilitato, mentre Analytics lo fa. Per questo motivo, in alcuni casi in cui il DFA registra un hit quando Analytics non lo fa.
* DFA conta le attività post-impression quando si utilizzano i tag Floodlight, che possono essere posizionati sul sito Web client. Analytics conta le visualizzazioni dopo l’esecuzione del beacon JavaScript (richiesta immagine). Il posizionamento del codice sulla pagina Web può determinare se un caricamento della pagina interrotto viene conteggiato come attività di post-impression o come visualizzazione-through.

### Cosa succede se le discrepanze sono ben al di fuori di un intervallo accettabile e le possibili ragioni di cui sopra non si applicano? {#section-ca50eb75dd5d4d0396f4668b44d7547c}

Consulta il tuo consulente di integrazione o l’Assistenza clienti Adobe per documentare le discrepanze e segnalarle al team di progettazione dei Data Connectors. Per accelerare la richiesta, disponi di 2-3 giorni di dati che confrontano le metriche in questione (a livello di codice della campagna). Nella tua richiesta, identifica tutte le azioni che hai già intrapreso per riconciliare la discrepanza.
