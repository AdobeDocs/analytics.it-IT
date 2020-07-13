---
description: Questa integrazione e-mail di Adobe® Data Connectors™ combina le informazioni comportamentali di  Analytics® con il marketing e-mail di recapito per creare uno strumento efficace per ridefinire la misurazione del successo e il pubblico di destinazione con messaggi più pertinenti.
title: Connettore dati Delivra per Adobe Analytics
uuid: 9d56d39c-98e6-4e9b-b00d-515df02ea879
translation-type: tm+mt
source-git-commit: 0fed9fd179feadae26a364a2ca79ac396251e8f6
workflow-type: tm+mt
source-wordcount: '984'
ht-degree: 2%

---


# Connettore dati Delivra per Adobe Analytics{#delivra-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>La tecnologia Adobe Data Connector terminerà a metà del 2021. [Ulteriori informazioni...](/help/import/data-connectors/data-connectors-eol.md)

Questa integrazione e-mail di Adobe® Data Connectors™ combina le informazioni comportamentali di  Analytics® con il marketing e-mail di recapito per creare uno strumento efficace per ridefinire la misurazione del successo e il pubblico di destinazione con messaggi più pertinenti.

L&#39;invio di messaggi e-mail pertinenti a questi segmenti di mercato può dare luogo a opportunità di profitto completamente nuove, aumentando la conversione e i ricavi tra campagne e-mail nuove ed esistenti. Ad esempio, la distribuzione di messaggi e-mail pertinenti basati su prodotti visualizzati durante una visita o prodotti lasciati in un carrello abbandonato ha avuto un impatto drammatico sulle entrate, con un impatto minimo sui costi, in quanto si tratta semplicemente di sfruttare i visitatori che il sito sta già ricevendo. Questo aumento dell&#39;efficienza del marketing è uno dei vantaggi principali dell&#39;integrazione  Analytics con Delivra. Inoltre, questa integrazione sincronizzerà automaticamente le metriche delle e-mail con  dati Analytics con la frequenza oraria per il reporting a circuito chiuso.

## Vantaggi chiave{#key-benefits}

Questa integrazione include i seguenti vantaggi principali:

* Consolidamento dei dati di marketing e analisi e-mail in un&#39;unica interfaccia di reporting
* Ottimizzazione delle campagne e-mail mediante conversione e contributo alle entrate e al successo del sito
* Rivendita i visitatori chiave e i segmenti di mercato basati su segmenti di marketing dinamici
* Sincronizzazione delle metriche delle e-mail in tempo reale disponibile, anziché una volta al giorno standard

## Segmenti di marketing dinamici{#dynamic-marketing-segments}

Questa integrazione e-mail dei Connettori dati supporta segmenti di marketing dinamici per aiutarti a guidare la tua attività.

Questa integrazione include i seguenti segmenti di marketing:

* **Profili di acquisto:** Aumentare gli ordini ripetuti e il valore medio degli ordini attraverso campagne mirate da pattern di acquisto dei visitatori.
* **Profilo comportamentale visualizzazione prodotto/contenuto:** Raggiungi potenziali clienti attraverso segmenti di marketing basati su viste di prodotto e profili di accesso ai contenuti.
* **Profilo abbandono carrello:** Aiuta i visitatori a convertirsi ai clienti attraverso campagne ottimizzate appositamente progettate per coloro che esitano a completare i carrelli.
* I clienti possono anche creare e pianificare segmenti di remarketing personalizzati in base alle esigenze dei propri utenti.

## Procedura di integrazione e prerequisiti{#integration-procedure-and-prerequisites}

Utilizzando una procedura guidata &quot;plug and play&quot;, i processi passo-passo intuitivi consentono di individuare i punti di sincronizzazione del sistema e di inizializzare l&#39;integrazione.

Questa integrazione con i Connettori dati richiede quanto segue:

### Prerequisiti Adobe {#section-bce14015fb7f41b3bc754da0eb7567bc}

* Adobe Data warehouse
* Account Adobe  Analytics
* Disponibili e configurate  variabili Analytics, incluse eVar ed eventi personalizzati.

### Prerequisiti: {#section-bcb904574ccf42308bcf7a15e45b4d58}

* Un account di livello Professional (o superiore) per l&#39;opzione &quot;Integrazione Adobe&quot; attivata.

## Prezzi{#pricing}

Questa integrazione con i Connettori dati include considerazioni di prezzo di cui devi essere consapevole.

Le sezioni che seguono contengono le informazioni seguenti:

### Considerazioni sui prezzi di Adobe {#section-2d1c79c895a5479bad8fdd97961ba6a3}

Questa integrazione potrebbe comportare costi ricorrenti per l&#39;implementazione. Contattate il rappresentante commerciale di riferimento Adobe per informazioni sui prezzi.

### Considerazioni sui prezzi di recapito {#section-c6afad08c34b43e3a7a3637eea3328c3}

Potrebbero essere presenti delle tariffe associate a questa integrazione.

* Contatta il tuo rappresentante commerciale per la spedizione per informazioni sui prezzi.

## Informazioni Da Sapere Prima Di Attivare L&#39;Integrazione{#what-you-should-know-before-activating-this-integration}

Prima di attivare questa integrazione, controllate i seguenti elementi rispetto alle distribuzioni di Adobe  Analytics® e del software e-mail.

In questo modo, prima dell&#39;attivazione verranno messe in atto le procedure ottimali appropriate o i prerequisiti necessari, il che porterà a un&#39;integrazione ottimale e di successo.

### Adobe Analytics{#adobe-analytics}

Leggi le seguenti informazioni sull’integrazione dei connettori dati per Adobe  Analytics:

* **Suite di rapporti specifica:** Questa integrazione è specifica per la suite di rapporti. Prima di attivare l&#39;integrazione, accertatevi di aver selezionato la suite di rapporti desiderata.
* **Rappresentante autorizzato:** L&#39;abilitazione di questa integrazione potrebbe indurre l&#39;azienda a sostenere delle spese in conformità al contratto di servizio stipulato con Adobe, Inc. o al contratto di assistenza stipulato con uno dei partner fidati di Adobe, a seconda dei casi. Attivando questa integrazione, l&#39;Utente dichiara di essere un rappresentante autorizzato della sua azienda; e, come tale, la vostra azienda accetta di pagare le eventuali tariffe indicate nel contratto di servizio sopra descritto.
* **Data warehouse™:** Questa integrazione richiede che la Data warehouse sia abilitata per generare segmenti di remarketing. Se non avete attivato l&#39;Data warehouse, contattate Adobe per ulteriori informazioni.
* **ID destinatario:** L&#39;integrazione richiede l&#39;acquisizione e la memorizzazione di un &quot;Visitor ID&quot; all&#39;interno di una variabile  Analytics (eVar). L’ID visitatore (spesso denominato &quot;ID destinatario&quot;) è una rappresentazione codificata o numerica di un indirizzo e-mail del sistema di recapito. Questo &quot;ID destinatario&quot; è associato al comportamento a valle dei visitatori sul sito (carrelli abbandonati, acquisti, ecc.) che viene trasferito nel sistema di recapito e può essere utilizzato per scopi di remarketing. Durante il processo di configurazione, è necessario identificare un&#39;eVar a tale scopo, quando richiesto dalla procedura guidata.
* **Tracciamento esterno:** Se al momento non state seguendo la procedura ottimale per abilitare il tracciamento esterno per ogni campagna e-mail inviata, dovete farlo per garantire il successo dell&#39;integrazione. Per ulteriori informazioni, consulta la sezione relativa alla consegna riportata di seguito.
* **Conformità alla privacy:** È importante comprendere che abilitando il tracciamento dell&#39;ID del destinatario o del visitatore, questa funzione può tenere traccia delle informazioni personali dei visitatori del sito. Questo ha implicazioni sulla privacy che richiedono l&#39;implementazione di procedure appropriate da parte dell&#39;organizzazione, ad esempio l&#39;informativa e il consenso dei visitatori del sito.

### Integrazione di Adobe Data Connectors{#delivra-for-adobe-data-connectors-integration}

Per informazioni sull&#39;integrazione dei connettori dati, consulta le informazioni seguenti relative a Delivery:

* **Account di recapito valido:** Per poter utilizzare l&#39;integrazione e-mail con i Connettori dati, un client deve avere un account Delivery valido.
* **Cliente attuale di Recapra:** Questa integrazione richiede l&#39;iscrizione di un cliente di Adobe e di Delivra. Se al momento non sei un cliente di Delivery, non avrai le informazioni necessarie per completare la procedura guidata di integrazione. Se al momento siete un cliente di Delivery, per completare l&#39;integrazione guidata avrete bisogno del vostro ID conto di recapito, o del nome dell&#39;elenco, assegnato alla vostra organizzazione. Per completare la configurazione, dovrete fornire l&#39;opzione Invia con il Nome società e l&#39;ID account associati all&#39;integrazione.
