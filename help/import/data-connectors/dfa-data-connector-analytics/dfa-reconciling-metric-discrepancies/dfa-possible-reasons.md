---
description: Elenca una serie di motivi che possono verificarsi discrepanze nei dati tra i rapporti Adobe Analytics e DFA.
keywords: DFA
seo-description: Elenca una serie di motivi che possono verificarsi discrepanze nei dati tra i rapporti Adobe Analytics e DFA.
seo-title: Possibili motivi per discrepanze
solution: Analytics
title: Possibili motivi per discrepanze
topic: Connettori dati
uuid: fd 414 cc 6-d 568-491 e -9 b 1 c -5 d 493 dcfbe 45
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Possibili motivi per discrepanze{#possible-reasons-for-discrepancies}

Elenca una serie di motivi che possono verificarsi discrepanze nei dati tra i rapporti Adobe Analytics e DFA.

## Utenti del browser Safari e altri browser che bloccano i cookie 3 rd-party {#section-4b0dc429a54a4744a33976b0bb2d1b2a}

L'accettazione dei cookie 3 rd party è in genere la causa più importante tra Adobe Analytics e DFA. Per impostazione predefinita, Safari e altri browser bloccano i cookie di terze parti. Questo significa che, per impostazione predefinita, Safari accetta il cookie di prime parti utilizzato dalla maggior parte delle implementazioni di Analytics, ma rifiuta il cookie di terze parti utilizzato da DFA.

Un campione di dati dei clienti beta di Analytics 15 mostrava meno del 0.5% degli utenti in genere rifiuta cookie first-party, mentre 5-12 % rifiuta i cookie di terze parti (molti di questi rifiutamenti sono probabilmente causati da impostazioni predefinite del browser).

Questa discrepanza può comportare una differenza notevole nei dati raccolti da Analytics e DFA.

## Perché le impression segnalate in DFA possono essere superiori alle impression segnalate in Adobe Analytics? {#section-db0ad070a65a4985bcc589b2d0d30b90}

* DFA invia dati ai server di raccolta dati Adobe in un batch notturno, quindi i dati impression in Analytics possono essere di 2 giorni dietro i report DFA.
* Adobe utilizza classificazioni SAINT per classificare i codici di monitoraggio DFA importati in vari livelli di aggregazioni (nome campagna, nome del posizionamento, nome annuncio, ecc.) Se la discrepanza viene visualizzata durante l'esecuzione di un rapporto di classificazione, eseguite un semplice test per verificare se le classificazioni non sono ancora state rilevate con le metriche importate:

   * Nel rapporto di classificazione, individuare un elemento della linea denominato "None".
   * Effettua una suddivisione di questo elemento di riga per la stessa variabile, utilizzando il rapporto ID DFA non elaborato (ad esempio ID campagna).
   * In questo rapporto prendi nota di eventuali codici di monitoraggio DFA non classificati che si trovano nel DFA del modulo: XXXXX: XXXXX…
   * Se esistono molti di questi codici di tracciamento, controllate il processo di classificazione notturna SAINT.

## Perché i clic DFA possono essere superiori ai click-through di Adobe Analytics? {#section-2fce4608ed044bdc9cf812cb719d5d35}

* DFA registra un click prima che il visitatore arrivi sul sito Web del cliente. Analytics registra Click-Through dopo che la pagina di destinazione carica ed esegue il beacon Adobe javascript. In genere si verificano discrepanze in quanto il visitatore non arriva alla pagina di destinazione dopo che il DFA tiene premuto un click oppure se il *`s.maxDelay`* timer viene rilevato.
* Assicuratevi che tutte le posizioni di inserimento e i creativi nella configurazione Effetto sonoro includano clickthroughparam nell'URL della pagina di destinazione (ad esempio «? CID = 1»). Se non impostate questo parametro, il javascript di Adobe Analytics perderà eventuali click-through che si verificano dopo il primo hit della visita.
* Assicuratevi che tutte le posizioni di inserimento e i creativi abbiano una pagina di destinazione con tag javascript e che abbiano il modulo di integrazione DFA, e che l'ID di configurazione della spia su quella pagina di destinazione corrisponda all'ID di configurazione primitiva degli annunci serviti. Spesso, le discrepanze vengono generate perché la pagina di destinazione per gli annunci è impostata su siti di terze parti, o annunci serviti.
* Se utilizzate annunci Contenuti multimediali avanzati o annunci Flash (swf), accertatevi che ogni volta che viene raggiunto il tracciatore DFA, anche il browser del visitatore venga reindirizzato alla pagina di destinazione con quello `clickThroughParam` incluso nella stringa query. Il mancato reindirizzamento del browser non causa la registrazione di un click-through.
* Timeout rappresentano le istanze in cui i dati DFA potrebbero essere disponibili, ma javascript non ha ricevuto una risposta nel tempo. Quando un visitatore arriva sulla pagina di destinazione, Adobe javascript richiede le informazioni del visitatore dal servizio fls. doubleclick. net di DFA. Il *`s.maxDelay`* parametro determina per quanto tempo javascript attende i dati FLS (Floodlight Service). Se *`s.maxDelay`* è troppo alta, i visitatori possono lasciare il sito prima che Adobe raccolga i dati di hit; ciò significa che non vengono registrati dati di clic. Se *`s.maxDelay`* è impostato troppo basso, la connessione Internet del visitatore non riesce a recuperare i dati FLS nel tempo; ciò significa che l'hit viene inviato ad Adobe senza informazioni su DFA. Per ulteriori discussioni su questo oggetto, consultate [Ottimizzazione di s. maxdelay](../../dfa-data-connector-analytics/dfa-integration/dfa-tuning-s-maxlelay.md#concept-6deb28eee18e414db220d6009d449f0d) .

* Il traffico bot potrebbe gonfiare i numeri di clic DFA. I bot possono avere funzionalità per fare clic su un annuncio, ma non possono avere la complessità di eseguire un beacon Analytics o di attivare il tag di script sincrono per caricare i dati della richiesta. Se questi bot non vengono rimossi dalla figura Clic, potrebbe trattarsi di un'origine di discrepanza.
* I visitatori che escono dalla pagina prima *`s.maxDelay`* della scadenza e dei dati DFA andranno perduti, non verranno raccolti dati DFA o dati visitatore.
* Analytics tenta di identificare e rimuovere i click-through duplicati in modo che vengano contati una sola volta per campagna. DFA conta i visitatori che fanno clic su «Indietro» e trasferiscono l'annuncio più volte come clic ACM aggiuntivo, mentre Analytics non conta questi come più Click-through.
* I tag DFA Feadlight non fanno affidamento su javascript abilitato, mentre Analytics lo supporta. A causa di questa situazione, in alcuni casi DFA registra un hit in caso contrario. Per identificare se questo potrebbe verificarsi un problema, usa il rapporto javascript di Analytics nel menu Profilo visitatore.

## Perché le attività di post-impression DFA potrebbero essere superiori alle visualizzazioni di Adobe Analytics? {#section-5daa91039c404df48b6a3447c20406f7}

* Analytics tenta di identificare e rimuovere i click-through duplicati in modo che vengano contati una sola volta per campagna. DFA conta i visitatori che fanno clic su «Indietro» e trasferiscono l'annuncio più volte come clic ACM aggiuntivo, mentre Analytics non conta questi come più Click-through.
* I tag DFA Feadlight non si basano su javascript disattivato, mentre Analytics è in grado di farlo. A causa di questa situazione, in alcuni casi DFA registra un hit in caso contrario.
* Conteggio DFA Le attività Post-impression quando si utilizzano i tag Floodlight, che possono essere posizionati sul sito Web del client. Conteggio dei dati di Analytics Una volta eseguito il beacon javascript (richiesta immagine). La posizione del codice nella pagina Web può determinare se un caricamento di pagina interrotto viene conteggiato come attività post-impression o come visualizzazione-through.

## Cosa succede se le discrepanze non rientrano in un intervallo accettabile e quanto sopra non si applica? {#section-ca50eb75dd5d4d0396f4668b44d7547c}

Rivolgetevi al consulente per l'integrazione, o ad Adobe Client Care, per documentare le discrepanze e portarle al team engineering dei connettori dati. Per accelerare la richiesta, hai 2 - 3 giorni di dati che confrontano le metriche in questione (a livello di codice della campagna). Nella richiesta, identificare tutte le azioni che hai già effettuato per riconciliare la discrepanza.
