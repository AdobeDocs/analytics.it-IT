---
description: Domande frequenti sul connettore dati DFA.
keywords: DFA
title: Domande frequenti
topic: Connettori dati
uuid: 59d187e9-1ec1-4cf3-8831-b981f87c9372
translation-type: tm+mt
source-git-commit: 6669f678c1327b6af4a5b67c8033a9b7d8c9dbcf
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 0%

---


# Domande frequenti{#frequently-asked-questions}

## Perché la procedura guidata Data Connectors non accetta le mie credenziali di accesso? {#section-f019b3de18774df3954af7881aa564fa}

Se hai verificato che le credenziali di accesso sono valide, verifica quindi che il nome utente fornito all’integrazione sia abilitato per l’accesso API. La procedura guidata Connettori dati utilizza l’API DFA per convalidare le credenziali di accesso, nonché per disattivare e attivare le impostazioni specifiche per Adobe nell’API DFA. Accesso API è un’impostazione che deve essere attivata da un amministratore dall’interno dell’interfaccia DFA. Quindi, assicurati di disporre dell’autorizzazione per accedere all’ID inserzionista o all’ID di configurazione del faro selezionato nella procedura guidata.

## Perché non vedo dati dalle metriche caricate ogni notte (impressioni DFA, clic DFA, ecc.)? {#section-465fd22ae6b447ffb6baf20b57daa433}

Se utilizzi la versione 1.5 dell’integrazione, potrebbe essere perché all’integrazione non è ancora stato assegnato un ID del sito client. Per lo scambio notturno è necessario un ID del sito client (CSID) e per richiedere i dati dal DFA e dal server. I CSID possono richiedere fino a 3 giorni dalla data di integrazione da scambiare con Google. Una volta ricevuto il CSID da Google, riceverai una notifica tramite l&#39;indirizzo e-mail dell&#39;integrazione del nuovo CSID, insieme al codice JavaScript più recente.

Se sono passati più di 3 giorni e non hai ricevuto l&#39;e-mail di configurazione e le metriche non scorrono, allora il problema più probabile è che il CSID è già stato assegnato a un&#39;altra integrazione. Google gestisce una mappatura da 1 a 1 tra CSID e suite di rapporti, il che significa che se un’integrazione in una suite di rapporti utilizza lo stesso ID inserzionista di un’altra integrazione in un’altra suite di rapporti, solo alla prima verrà assegnato un ID CS. Per modificare la suite di rapporti o l’ID inserzionista a cui è mappato un CSID, è necessario aprire un ticket con il supporto Google.

Ad esempio, supponiamo che nella suite di rapporti A sia presente un’integrazione con l’ID inserzionista Z a cui viene assegnato un CSID. Se un’altra integrazione viene successivamente impostata in Report Suite B con Advertiser Z, questa integrazione più recente NON verrà riassegnata al CSID. Questo richiederebbe un biglietto Google. Dall’altro lato, considera l’esempio di un’integrazione in Report Suite A, con Advertiser ID Z e in seguito un’altra integrazione in Report Suite A, Advertiser Z è configurato. Solo la prima integrazione riceverà i dati per l&#39;integrazione; tuttavia, in questo caso, la prima integrazione può essere disattivata e i dati passeranno alla seconda integrazione.

>[!NOTE]
>
>I CSID non vengono utilizzati nella versione 2.0 dell&#39;integrazione e pertanto il processo di negoziazione CSID non è applicabile.

## La versione 2.0 dell’integrazione e le metriche dei costi non vengono visualizzate per gli annunci DFA. Perché questo potrebbe essere? {#section-805748111bbe4bbf918d6dbbb2641fff}

Le metriche dei costi devono essere sia attivate dal lato DFA di Google, sia fornite nell’interfaccia DFA, sia attivate nella procedura guidata Connettori dati. La prima posizione da verificare è che hai mappato un evento Analytics per DFA Media Cost e hai fornito un codice valuta. Se hai mappato l’evento Media Cost e hai completato e salvato la procedura guidata, il flag DFA omnitureCostData verrà attivato nell’API DFA. Questo segnalerà a Google che le metriche devono essere inviate nel file notturno. È possibile controllare due volte tramite l’interfaccia DFA che omnitureCostData sia abilitato controllando le proprietà del Floodlight integrato. Infine, dopo aver controllato questi due luoghi, assicurati che gli annunci che fanno parte del Floodlight integrato specifichino i dati di costo e le strutture di costo. Se i dati dei costi non vengono forniti nell’interfaccia DFA, non verranno visualizzati in Analytics.

## Perché alcuni annunci non mostrano impression DFA o visualizzazioni, ma mostrano clic e click-through? {#section-39b2eeeefd7f43d1a373df0b987bacef}

Ci sono alcuni annunci che registrano solo dati di clic, chiamati clicktracker. Questi tipi di annunci non restituiscono i dati dell’ultima impression da quando viene eseguita una query sul server di Floodlight. Per verificare se un determinato annuncio è un click-tracker o un annuncio solo clic, contatta l’agenzia DFA o il tuo rappresentante di supporto Google.

## Perché non ci sono click-through per gli annunci che mostrano i clic DFA? {#section-758c1f1fc5b54bfc9294dcdc71bbd96a}

Ci può essere una delle tante risposte a questo.

In primo luogo, controlla che l’annuncio in questione abbia un URL della pagina di destinazione che sia (a) con tag di codice Adobe per la stessa suite di rapporti in cui stai visualizzando la discrepanza in e (b) contiene il parametro della stringa di query *`clickThroughParam`* .

In secondo luogo, verifica di disporre di un’integrazione di lavoro seguendo i passaggi descritti in [Conferma di un’integrazione DFA riuscita](../dfa-data-connector-analytics/dfa-integration.md). Se vedi un codice di tracciamento DFA arrivare con l’hit di Adobe sulla pagina di destinazione, dovresti vedere che il click-through è presente nel rapporto Campagne DFA. Se non visualizzi il passaggio , verifica che le suite di rapporti corrispondano tra la variabile *`s.account`* della pagina di destinazione e la suite di rapporti visualizzata in Reports &amp; Analytics. Se questi corrispondono, controlla i codici di tracciamento nel rapporto View Through eVar che assomigliano a DFA:XXX:XXX:llXXX:XXX:XXX:XXX:XXX:XXX:XXX:XXX.

Questi indicano gli errori della regola VISTA DFA per digerire i dati non elaborati dal DFA. Per risolvere questo problema, apri un ticket di supporto tramite il tuo rappresentante commerciale Adobe.

Se nessuna delle soluzioni di cui sopra spiega il problema, consulta [Riconciliazione delle discrepanze metriche](../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies.md) per esplorare altre possibilità.
