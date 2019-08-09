---
description: nulle
keywords: DFA
seo-description: nulle
seo-title: Domande frequenti
solution: Analytics
title: Domande frequenti
topic: Connettori dati
uuid: 59 d 187 e 9-1 ec 1-4 cf 3-8831-b 981 f 87 c 9372
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Domande frequenti{#frequently-asked-questions}

## Perché la procedura guidata Connettori dati non accetta le mie credenziali di accesso? {#section-f019b3de18774df3954af7881aa564fa}

Se avete verificato che le credenziali di accesso siano valide, verificate che il nome utente fornito all'integrazione sia abilitato per l'accesso API. La procedura guidata Connettori dati utilizza l'API DFA per convalidare le credenziali di accesso, oltre a disattivare e alle impostazioni specifiche di Adobe nell'API DFA. Accesso API è un'impostazione che deve essere attivata dall'interfaccia DFA da un amministratore. Quindi, accertatevi di disporre dell'autorizzazione per accedere all'ID advertiser o all'ID di configurazione floodlight selezionato nella procedura guidata.

## Perché non vedo dati dalle metriche caricate notturne (impression DFA, clic DFA, ecc.)? {#section-465fd22ae6b447ffb6baf20b57daa433}

Se utilizzate la versione 1.5 dell'integrazione, ciò potrebbe dipendere dal fatto che all'integrazione non è ancora stato assegnato un ID sito client. È necessario un ID sito client (CSID) per lo scambio notturno e per richiedere dati dal server di annunci DFA. I CSIDS possono richiedere fino a 3 giorni dalla data di integrazione da scambiare con Google. Una volta ricevuto CSID da Google, riceverete una notifica tramite l'indirizzo e-mail dell'integrazione del nuovo CSID, insieme al codice javascript più recente.

Se sono trascorsi più di 3 giorni e non avete ricevuto l'e-mail e le metriche di configurazione, il problema più probabile è che il CSID è già stato assegnato a un'altra integrazione. Google mantiene una mappatura tra 1 e 1 tra CSID e Suite di rapporti, il che significa che se un'integrazione in una suite di rapporti utilizza lo stesso ID pubblicitario come un'altra integrazione in un'altra suite di rapporti, solo alla prima verrà assegnato un ID CS. Per modificare la suite di rapporti o l'ID pubblicitario a cui viene mappato un CSID, un ticket deve essere aperto con il supporto Google.

Ad esempio, supponiamo che nella suite di rapporti A sia presente un'integrazione con l'ID dell'inserzionista Z a cui viene assegnato un CSID. Se un'altra integrazione viene successiva in Report Suite B con Advertiser Z, questa nuova integrazione NON sarà assegnata nuovamente a CSID. Questo richiede un ticket Google. D'altra parte, prendi l'esempio di un'integrazione nella suite di rapporti A, con l'ID inserzionista Z e un'altra integrazione in Report Suite A, Advertiser Z è configurazione. Solo la prima integrazione riceverà i dati per l'integrazione; In questo caso, tuttavia, la prima integrazione può essere disattivata e i dati scorrono alla seconda integrazione.

>[!NOTE]
>
>I CSIDS non vengono utilizzati nella versione 2.0 dell'integrazione e non si applica il processo di negoziazione CSID.

## Uso la versione 2.0 dell'integrazione e le metriche costi non vengono visualizzate per i miei annunci DFA. Perché potrebbe essere? {#section-805748111bbe4bbf918d6dbbb2641fff}

Le metriche costi devono essere attivate sia dal lato Google DFA che fornite nell'interfaccia DFA, così come attivate nella procedura guidata Connettori dati. Il primo punto da verificare consiste nel fatto che hai mappato un evento Analytics per DFA Media Cost e che fornisce un codice valuta. Se hai mappato l'evento di prezzo multimediale e hai terminato e salvato la procedura guidata, il flag omniturecostdata DFA verrà attivato nell'API DFA. Questo segnale a Google che le metriche devono essere inviate nel file notturno. Puoi eseguire due volte il check-through tramite l'interfaccia DFA che omniturecostdata è abilitata analizzando le proprietà in Rilievo integrato. Infine, dopo aver controllato questi due luoghi, assicurati che gli annunci che fanno parte di Experience Dlight specifichino i dati costi e le strutture dei costi. Se i dati costi non sono inclusi nell'interfaccia DFA, non saranno visualizzati in Analytics.

## Perché alcuni annunci non mostrano impression DFA o visualizzazioni di visualizzazione, ma mostrano clic e click-through? {#section-39b2eeeefd7f43d1a373df0b987bacef}

Ci sono annunci pubblicitari che registrano solo dati clic, chiamati clicktracker. Questi tipi di annunci non restituiscono i dati dell'ultima impression da quando viene interrogato il server Floodlight. Per verificare se un determinato annuncio è un annuncio o un annuncio di solo clic, contatta l'agenzia DFA o il rappresentante di supporto Google.

## Perché non sono disponibili click-through per annunci che mostrano clic DFA? {#section-758c1f1fc5b54bfc9294dcdc71bbd96a}

Ci può essere una di molte risposte.

Innanzitutto, verificate che l'annuncio in questione disponga di un URL della pagina di destinazione (a) con tag Adobe per la stessa suite di rapporti per la quale state visualizzando la discrepanza in e (b) contiene il *`clickThroughParam`* parametro della stringa query.

Secondo, verifica di disporre di un'integrazione di lavoro seguendo i passaggi descritti in [Conferma di un'integrazione DFA completata](../dfa-data-connector-analytics/dfa-integration/dfa-confirm-integration.md#concept-c1c869d2a6fa46b09fe41fc286e407c6). Se un codice di tracciamento DFA viene visualizzato con l'hit Adobe sulla pagina di destinazione, dovresti vedere che Click-through viene incluso nel rapporto Campagne DFA. Se non la visualizzate, verificate che le suite di rapporti corrispondano tra la *`s.account`* variabile della pagina di destinazione e la suite di rapporti visualizzata in Reporting e analisi. Se corrispondono, controlla i codici di monitoraggio nel rapporto Visualizza attraverso evar che si presenta come DFA: XXX: XXX: XXX: Llxxx: XXX: XXX: XXX: XXX.

Questi indicano errori della regola DFA VISTA per digest i dati non elaborati da DFA. Questo problema può essere risolto aprendo un ticket di supporto tramite il vostro account Adobe Account.
Se nessuna delle soluzioni qui sopra spiega il problema, consultate [Riconciliare le discrepanze delle metriche](../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies/dfa-reconciling-metric-discrepancies.md#concept-8c31ebe761ca4b3fab1e3a18ef5d098f) per esplorare altre possibilità.