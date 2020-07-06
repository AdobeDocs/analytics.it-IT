---
description: 'null'
keywords: DFA
title: Domande frequenti
topic: Data connectors
uuid: 59d187e9-1ec1-4cf3-8831-b981f87c9372
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '879'
ht-degree: 0%

---


# Domande frequenti{#frequently-asked-questions}

## Perché la procedura guidata Connettori dati non accetta le mie credenziali di accesso? {#section-f019b3de18774df3954af7881aa564fa}

Se avete verificato la validità delle credenziali di accesso, verificate quindi che il nome utente fornito all&#39;integrazione sia abilitato per l&#39;accesso all&#39;API. La procedura guidata Connettori dati utilizza l’API DFA per convalidare le credenziali di accesso, nonché per disattivare e attivare le impostazioni specifiche di Adobe nell’API DFA. Accesso API è un&#39;impostazione che deve essere attivata da un amministratore dall&#39;interfaccia DFA. Quindi, accertatevi di disporre dell&#39;autorizzazione per accedere all&#39;ID inserzionista o all&#39;ID di configurazione del faro selezionato nella procedura guidata.

## Perché non visualizzo alcun dato dalle metriche caricate notturne (Impressioni DFA, Clic DFA, ecc.)? {#section-465fd22ae6b447ffb6baf20b57daa433}

Se utilizzate la versione 1.5 dell&#39;integrazione, ciò potrebbe essere dovuto al fatto che all&#39;integrazione non è ancora stato assegnato un ID del sito client. È necessario un ID del sito client (CSID) per lo scambio notturno e per richiedere i dati al DFA e al server. I CSID possono richiedere fino a 3 giorni dalla data di integrazione da scambiare con Google. Una volta ricevuto il CSID da Google, riceverai una notifica tramite l&#39;indirizzo e-mail dell&#39;integrazione del nuovo CSID, insieme al codice JavaScript più recente.

Se sono trascorsi più di 3 giorni e non avete ricevuto l’e-mail di configurazione e le metriche non sono in flusso, il problema più probabile è che il CSID è già stato assegnato a un’altra integrazione. Google gestisce una mappatura da 1 a 1 tra CSID e Suite di rapporti, il che significa che se un&#39;integrazione in una suite di rapporti utilizza lo stesso ID inserzionista di un&#39;altra integrazione in un&#39;altra suite di rapporti, solo alla prima verrà assegnato un ID CS. Per modificare la suite di rapporti o l&#39;ID pubblicitario a cui è mappato un CSID, è necessario aprire un ticket con il supporto Google.

Ad esempio, supponiamo che esista un&#39;integrazione nella Suite di rapporti A con l&#39;ID inserzionista Z a cui sia assegnato un CSID. Se un&#39;altra integrazione viene successivamente configurata nella Suite di rapporti B con l&#39;inserzionista Z, questa nuova integrazione NON verrà riassegnata al CSID. Questo richiederebbe un biglietto Google. Dall&#39;altro lato, prendete l&#39;esempio di un&#39;integrazione in Report Suite A, con Advertiser ID Z, e successivamente un&#39;altra integrazione in Report Suite A, Advertiser Z è configurato. Solo la prima integrazione riceverà i dati per l&#39;integrazione; tuttavia, in questo caso, la prima integrazione può essere disattivata e i dati passeranno alla seconda integrazione.

>[!NOTE]
>
>I CSID non vengono utilizzati nella versione 2.0 dell&#39;integrazione, pertanto il processo di negoziazione CSID non è applicabile.

## Sto utilizzando la versione 2.0 dell&#39;integrazione e le metriche dei costi non vengono visualizzate per i miei annunci DFA. Perché questo potrebbe essere? {#section-805748111bbe4bbf918d6dbbb2641fff}

Le metriche dei costi devono essere sia attivate dal lato Google DFA sia fornite nell&#39;interfaccia DFA, sia attivate nella procedura guidata Connettori dati. Il primo punto da verificare è che è stato mappato un evento Analytics  per DFA Media Cost e fornito un codice valuta. Se hai mappato l’evento Media Cost, e hai completato e salvato la procedura guidata, il flag DFA omnitureCostData sarà attivato nell’API DFA. Questo indicherà a Google che le metriche devono essere inviate nel file notturno. È possibile controllare due volte tramite l&#39;interfaccia DFA che omnitureCostData sia attivato esaminando le proprietà sul Floodlight integrato. Infine, dopo aver controllato questi due luoghi, accertati che gli annunci che fanno parte del Floodlight integrato specifichino i dati dei costi e le strutture dei costi. Se i dati dei costi non vengono forniti nell&#39;interfaccia DFA, non verranno visualizzati  Analytics.

## Perché alcuni annunci non mostrano alcuna impressione o visualizzazione DFA, ma mostrano clic e click-through? {#section-39b2eeeefd7f43d1a373df0b987bacef}

Ci sono alcuni annunci che registrano solo dati di clic, chiamati clicktrackers. Questi tipi di annunci non restituiscono i dati dell&#39;ultima impressione dal momento in cui viene interrogato il server Floodlight. Per verificare se un determinato annuncio è un click-tracker o un annuncio di solo clic, contatta la tua agenzia DFAE o il tuo rappresentante del supporto Google.

## Perché non ci sono click-through per gli annunci che mostrano clic su DFA? {#section-758c1f1fc5b54bfc9294dcdc71bbd96a}

Ci può essere una delle tante risposte a questo.

Innanzitutto, verificate che l’annuncio in questione disponga di un URL della pagina di destinazione che sia (a) dotato di tag Adobe per la stessa suite di rapporti in cui state visualizzando la discrepanza e (b) contiene il parametro della stringa di *`clickThroughParam`* query.

In secondo luogo, verifica di disporre di un’integrazione di lavoro seguendo i passaggi descritti in [Conferma di un’integrazione](../dfa-data-connector-analytics/dfa-integration.md)DFA di successo. Se viene visualizzato un codice di tracciamento DFA con l’hit Adobe sulla pagina di destinazione, il messaggio Click-through compare nel rapporto Campagne DFAE. Se non visualizzi il risultato finale, verifica che le suite di rapporti corrispondano tra la *`s.account`* variabile della pagina di destinazione e la suite di rapporti visualizzata in Reporting e  Analytics. Se queste corrispondenze, verificate la presenza di codici di monitoraggio nel rapporto View Through eVar che siano come DFA:XXX:XXX:XXX:llXXX:XXX:XXX:XXX:XXX:XXX.

Ciò indica errori della regola VISTA del DFAE per la classificazione dei dati grezzi dal DFAE. È possibile risolvere il problema aprendo un ticket di assistenza tramite il rappresentante commerciale Adobe.

Se nessuna delle soluzioni di cui sopra spiega il problema, vedere [Riconciliazione delle differenze](../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies.md) di metrica per esplorare altre possibilità.
