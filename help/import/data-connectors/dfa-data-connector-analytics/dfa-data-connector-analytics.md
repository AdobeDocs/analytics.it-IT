---
description: Utilizza l’integrazione DoubleClick per gli inserzionisti con Adobe Analytics.
keywords: DFA
title: Connettore dati DFA per Adobe Analytics
topic: Connettori dati
uuid: 8d04909f-6f17-4b7d-a199-99c923253474
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '1736'
ht-degree: 3%

---


# Connettore dati DFA per Adobe Analytics{#dfa-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>La tecnologia Adobe Data Connector terminerà il 1° agosto 2021. [Ulteriori informazioni...](/help/import/data-connectors/data-connectors-eol.md)

Nel mercato online sempre più complesso e competitivo di oggi, gli inserzionisti e le agenzie online devono continuamente migliorare la loro comprensione dell&#39;ambiente di marketing online e del loro ritorno sulla spesa pubblicitaria. Sebbene gli inserzionisti, le agenzie e gli editori siano tutti in possesso di strumenti individuali per contribuire a raggiungere questi obiettivi, l’aggregazione manuale dei dati da sistemi e processi di dati diversi può seriamente ostacolare l’efficacia delle campagne di marketing on-line, con conseguente prestazioni delle campagne meno ottimali, discrepanze di dati e confusione.

L&#39;integrazione DoubleClick for Advertiser (DFA) risolve questo problema utilizzando Adobe® Data Connectors™ per consentire a DoubleClick DFA di passare automaticamente i dati a Reports &amp; Analytics.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Data Connectors]**

![](assets/data-connectors-home.png)

## Vantaggi chiave{#key-benefits}

I vantaggi principali dell’integrazione Data Connector - DFA includono:

* **Maggiore conversione**: Ottieni informazioni direzionali per ottimizzare il posizionamento delle campagne pubblicitarie e la conversione in sito in base al comportamento e alle preferenze dei visitatori dopo aver fatto clic su di esse.
* **Posizione condivisa per i dati**: Combina il click-through e la visualizzazione dei dati con doppio clic DFA con Reports &amp; Analytics per migliorare la collaborazione e le capacità organizzative per prendere decisioni obiettive.
* **Analisi** a valore aggiunto: L’integrazione automatizzata tra DFA e Adobe Reports &amp; Analytics consente agli inserzionisti e alle agenzie di trascorrere meno tempo stringendo i dati e più tempo analizzando i rapporti e intervenendo.
* **Informazioni** più approfondite sui clienti: Scopri di più su dove vengono i visitatori e cosa stanno facendo sul tuo sito.
* **Metriche** di successo del ciclo di vita: Misura l’efficacia delle campagne di acquisizione nell’intero ciclo di vita del visitatore.
* **Reporting** integrato: Sincronizza automaticamente i dati tra DFA e Reports &amp; Analytics per processi aziendali e reporting semplificati.
* **Analisi** del visitatore a vita: Misura l’efficacia della campagna in base a più eventi di successo definiti dall’utente e al valore del ciclo di vita.
* **Metriche** di costo: Ottimizzare il ritorno sugli investimenti confrontando in un unico sistema i dati relativi ai costi e ai ricavi generati da tali costi.

## Panoramica dell&#39;integrazione di Ad Server{#ad-serving-integration-overview}

Esistono diversi modi in cui questa integrazione acquisisce i dati sui visitatori basati su annunci. Il primo modo è facendo clic su un annuncio e arrivando a una pagina di destinazione con tag, denominata click-through:

![](assets/Diagram1.png)

Il visitatore arriva sul sito di un editore che ospita l’annuncio. Questo annuncio ha un identificatore univoco, denominato Ad ID. Gli annunci comprendono un posizionamento e un creativo, che descrivono dove si trova l’annuncio sul sito dell’editore e quale contenuto è stato mostrato al visitatore. Quando il visitatore recupera l’annuncio, il posizionamento o la creatività dai server di contenuto DFA, tiene traccia di un’impression sui server DFA Floodlight per questo visitatore (1).

Se il visitatore fa clic sull’annuncio (2), viene eseguita una query sul server di alluvione, che conta un clic, quindi 302 reindirizzerà il visitatore alla pagina di destinazione (3). Quando il visitatore è arrivato sulla pagina di destinazione, viene chiamato click-through. Questa pagina contiene un Adobe di codice di tracciamento che invia una query ai dati dal DFA Floodlight Server.

Se il visitatore non arriva effettivamente alla pagina di destinazione dopo che il server di Mobile ha tracciato un clic, questo non viene definito click-through. Alcuni annunci e implementazioni potrebbero non causare il reindirizzamento del browser del visitatore a 302. Per ulteriori discussioni su questo argomento, consulta [Riconciliazione delle discrepanze metriche](../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies.md).

La metrica successiva acquisita da questa integrazione si verifica quando il visitatore riceve l’impression dell’annuncio, non fa clic, ma in un futuro prossimo arriva sulla pagina di destinazione con altri mezzi.

![](assets/Viewthrough.png)

Questo scenario è denominato view-through. La differenza in questo scenario con lo scenario di click-through è che il visitatore non fa clic sull’annuncio, ma continua ad altre attività prima di passare alla pagina di destinazione (2). Nel caso più semplice, il visitatore digita l’URL della pagina di destinazione nel browser. In altri casi, il visitatore continua a navigare ma in seguito utilizza un motore di ricerca, che indirizza il visitatore alla pagina di destinazione. In ogni caso, l’utente arriva alla pagina di destinazione.

## Integrazione Adobe: Raccolta dati in tempo reale{#adobe-integration-real-time-data-collection}

La figura seguente illustra il funzionamento della raccolta dati.

![](assets/DFA_data_collection.png)

La porzione di raccolta dati dell’integrazione di Adobe inizia quando il visitatore arriva alla pagina di destinazione (1). Il codice di raccolta dati di Adobe in esecuzione sulla pagina di destinazione non è a conoscenza della cronologia che il visitatore ha avuto con gli annunci serviti. Il team DFA di Google ha coordinato un servizio in esecuzione su DFA Floodlight Server per consentire al codice di Adobe di inviare query ad informazioni sul visitatore attualmente sul sito (2). Per ottenere questi dati, ritarda temporaneamente il beacon immagine di Adobe e richiede i dati dal server Floodlight.

Una volta che i dati arrivano o richiedono troppo tempo, viene attivato l’hit sui server di tracciamento di Adobe (3).

Il modulo Integrate è uno speciale modulo JavaScript di base di Adobe che causa il ritardo del beacon dell’immagine di Adobe, in attesa di una richiesta di terze parti per un periodo di tempo specifico (`s.maxDelay`). `s.maxDelay` definisce per quanto tempo il modulo Integrate attenderà i dati dal DFA Floodlight Server prima di attivare il tag immagine nel browser del visitatore. Questo comportamento è importante in modo che i dati dei visitatori di base vengano ancora raccolti, anche quando i server DFA Floodlight sono inattivi o a carico elevato. Se i dati di Mobile arrivano prima della scadenza di `s.maxDelay` , i dati di tracciamento Adobe verranno attivati immediatamente e conterranno i dati DFA aggiuntivi.

Quando si verifica un timeout, il codice della pagina può specificare un evento Adobe Reports &amp; Analytics da utilizzare come evento di timeout. Questo evento è utile per diagnosticare problemi con l&#39;integrazione o per la regolazione di `s.maxDelay`. Nei casi in cui si verificano timeout eccessivi, aumenta `s.maxDelay`. `s.maxDelay` può essere impostato su un livello troppo alto, tuttavia, in quali casi i visitatori potrebbero avere il potenziale di lasciare il sito prima della scadenza del  `s.maxDelay` timer. .

A volte Floodlight Server risponde con errori relativi al visitatore. Questo di solito si verifica quando Floodlight Server non sa nulla del visitatore, perché il visitatore non ha ancora visto annunci o non ha un cookie visitatore DFA. Il codice della pagina può specificare una variabile di conversione personalizzata (eVar) che raccoglierà questi errori e può aiutare a risolvere i problemi di implementazione o segnalare i problemi con la transazione Google. Gli errori più comuni sono: Nessuna cronologia, Nessun cookie, Errore query e Rinuncia, come descritto nella tabella seguente:

| Errore | Nome | Descrizione |
|---|---|---|
| nh | Nessuna cronologia | Il visitatore non ha visualizzato o fatto clic su alcun annuncio. |
| nc | Nessun cookie | Il visitatore non dispone di un cookie visitatore DFA. |
| qe | Errore di query | Errore durante l&#39;esecuzione di query dei dati per il server Floodlight. |
| oo | Rinuncia | Il visitatore ha rinunciato al tracciamento delle impression/clic di Google. |

## Integrazione Adobe: Importazione dati notturna{#adobe-integration-nightly-data-import}

La parte dell’integrazione relativa alla raccolta dei dati raccoglie i dati click-through e view-through relativi ai visitatori del sito. Per ottenere le metriche di clic, impression e costi DFA, esiste un processo notturno coordinato da Google e da Adobe per importare questi dati aggiuntivi nella suite di rapporti integrata. Queste metriche vengono importate tramite Origini dati, il che significa che sono disponibili solo sotto forma di aggregato e non a livello di visita.

## Differenze tra versioni{#version-differences}

Al momento sono disponibili tre versioni dell’integrazione DFA: 1.0, 1.5 e 2.0.

Nella tabella seguente sono riepilogate le funzioni di ogni versione dell’integrazione.

| Funzione | Versione 1.0 | Versione 1.5 | Versione 2.0 |
|---|---|---|---|
| Metriche di clic e impression DFA notturne | Sì | Sì | Sì |
| Tracciamento click-through e view-through | Sì | Sì | Sì |
| L&#39;integrazione riceve dati a livello di inserzionista | No | Sì | Sì |
| L&#39;integrazione riceve i dati a un livello di configurazione Floodlight | No | No | Sì |
| Metriche di costo | No | No | Sì |
| Metriche creative | No | No | Sì |
| Stringhe di query oltre 2 KB | No | Sì | Sì |
| Utilizza il modulo Integrate per una raccolta dati ottimale di terze parti | No | Sì | Sì |
| Tracciamento timeout ed errori | No | Sì | Sì |
| Non è necessario negoziare l’ID lato client | No | No | Sì |

### Informazioni sulla versione 1.5 {#section-b5a3e967cfa141ea8f740612336181be}

La versione 1.5 dell’integrazione introduce il modulo Integrate nella pagina di destinazione Java Script. Il modulo Integrate consente richieste di dimensioni fisse al DFA ad server (ad.doubleclick.net) che superano i limiti di richiesta 2K dell’integrazione precedente. Inoltre, introduce un timeout configurabile, *`s.maxDelay`*, per continuare a raccogliere i dati dei visitatori Adobi quando si verificano interruzioni di rete. Gli errori e i timeout possono essere acquisiti anche nelle variabili di Analytics.

La figura seguente illustra le interazioni di rete sulla pagina di destinazione nella versione 1.5.

![](assets/DFA_About_1_5.png)

Nella versione 1.5, il modulo Integrate (2) richiede i dati da Floodlight Server (3). Il Floodlight Server eseguirà il reindirizzamento al DFA ad server, che restituirà i dati sul visitatore allo stesso modo della versione 1.0. Il reindirizzamento a 302 (4) a uno speciale servizio di traduzione al momento di integrare.112.2o7.net, che trasformerà la struttura di risposta in un oggetto JSON. Il modulo Integrate utilizza questo oggetto JSON e trasmette le informazioni al tracciamento degli Adobi (5).

Il passaggio dalla versione 1.0 dell&#39;integrazione alla versione 1.5 comporta una modifica JavaScript. Per ottenere questo JavaScript, accedi al tuo account Adobe Online Marketing Suite, scegli il prodotto di Genesis, fai clic su Modifica sull’integrazione DFA e passa alla procedura guidata. Se in precedenza è stato assegnato un ID sito client, una volta salvata l’integrazione riceverai immediatamente il nuovo codice JavaScript tramite e-mail. Una volta ottenuto questo codice, sarà necessaria anche una nuova versione del codice s_code di base che dispone del modulo Integrate. Questo codice può essere richiesto al tuo Account Manager o consulente di implementazione.

Una caratteristica importante del nuovo codice JavaScript è che non è necessaria alcuna modifica di implementazione tra la versione 1.5 e la versione 2.0.

### Informazioni sulla versione 2.0 {#section-afd56de0c56c4489bb5ddc5798d6709a}

L’ultima versione dell’integrazione DFA contiene i dati per un’intera configurazione di Floodlight nell’integrazione. Precedentemente alla versione 2.0, le integrazioni individuali erano legate a un singolo inserzionista DFA. Con questa modifica, le metriche Clic, Impressione e Costo per l’intera configurazione del faro verranno incluse nella suite di rapporti integrata. È inoltre possibile tenere traccia della visualizzazione tra siti attraverso, quando questi due siti si trovano all’interno della stessa configurazione di Floodlight.

A partire dalla versione 2.0 dell’integrazione sono disponibili anche le metriche del costo multimediale. Per abilitare le metriche dei costi dei file multimediali per un’integrazione, devi scegliere un evento Reporting e analisi per Costo contenuto multimediale nella procedura guidata di Genesis, nonché specificare la valuta in cui si trovano le cifre delle metriche nell’interfaccia DFA.

I timeout dovrebbero diminuire con l&#39;integrazione 2.0, poiché i reindirizzamenti 302 sono stati eliminati. L’eliminazione di questi luppolo dovrebbe ridurre i timeout e aumentare la quantità di dati DFA che è possibile integrare.

Se una configurazione Floodlight è una configurazione condivisa in DFA, l’aggiornamento dalla versione 1. Da 5 a 2.0 i dati di conversione per tutti gli inserzionisti condivisi nella configurazione di Mobile vengono inclusi nella suite di rapporti.

### Aggiornamento alla versione 2.0 {#section-f0bf90b9a7a1434ab1540b6c0999f4c7}

La tabella seguente illustra i proprietari della migrazione alle versioni più recenti dell’integrazione:

| Migrazione | Proprietario | Attività |
|---|---|---|
| Da 1.0 a 1.5 | Client | Implementare JavaScript versione 1.5 con il modulo Integrate |
| Da 1.5 a 2.0 | Client | Il client inizia la discussione con Google sui tempi di aggiornamento. Dopo l’approvazione, Google abilita Advanced Ad Serving. |
