---
description: Descrive le efficienze di marketing ottenute grazie all'integrazione.
title: Connettore dati Lyris per Adobe Analytics
uuid: db213865-1296-4a93-a0a2-781c026b2be5
translation-type: tm+mt
source-git-commit: 3850dc3503ca57ba4f13f0de63e8420e484db501
workflow-type: tm+mt
source-wordcount: '1049'
ht-degree: 2%

---


# Connettore dati Lyris per Adobe Analytics{#lyris-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>La tecnologia del Connettore dati del Adobe  terminerà il 1 agosto 2021. [Ulteriori informazioni...](/help/import/data-connectors/data-connectors-eol.md)

L&#39;integrazione di e-mail con  Adobe® Data Connectors™ combina le informazioni comportamentali  Adobe Analytics con il marketing e-mail di Lyris per ridefinire la misurazione del successo e il pubblico di destinazione con messaggi più pertinenti.

L&#39;invio di messaggi e-mail pertinenti a questi segmenti di mercato può dare luogo a opportunità di profitto completamente nuove, aumentando la conversione e i ricavi tra campagne e-mail nuove ed esistenti. Ad esempio, la distribuzione di messaggi e-mail pertinenti basati su prodotti visualizzati durante una visita o prodotti lasciati in un carrello abbandonato ha avuto un impatto drammatico sulle entrate, con un impatto minimo sui costi, in quanto si tratta semplicemente di sfruttare i visitatori che il sito sta già ricevendo.

Questo aumento dell&#39;efficienza del marketing è uno dei vantaggi chiave dell&#39;integrazione  Adobe Analytics con Lyris. Inoltre, questa integrazione sincronizzerà automaticamente le metriche delle e-mail con  dati Adobe Analytics con la frequenza oraria per il reporting a circuito chiuso.

## Vantaggi e funzionalità principali{#key-benefits-and-features}

Descrive i vantaggi principali dell&#39;integrazione di Lyris e Marketing reports and analytics di Adobe .

L&#39;integrazione di Lyris e  Adobe Analytics offre i seguenti vantaggi principali:

* Consolidamento dei dati di marketing e analisi e-mail in un&#39;unica interfaccia di reporting
* Ottimizzazione delle campagne e-mail mediante conversione e contributo alle entrate e al successo del sito
* Rivendita i visitatori chiave e i segmenti di mercato basati su segmenti di marketing dinamici

### Segmenti di marketing dinamici

L&#39;integrazione delle e-mail supporta segmenti di marketing dinamici per aiutarti a promuovere la tua attività. Questa integrazione include i seguenti segmenti di marketing:

* **Profilo** di abbandono carrello: Aiuta i visitatori a convertirsi ai clienti attraverso campagne di ottimizzazione appositamente progettate per coloro che esitano a completare i carrelli
* **Profili** di acquisto: Aumentare gli ordini ripetuti e il valore medio degli ordini attraverso campagne mirate per i pattern di acquisto dei visitatori
* **Profilo** comportamentale di visualizzazione prodotto/contenuto: Raggiungi potenziali clienti attraverso segmenti di marketing basati sulle visualizzazioni dei prodotti e sui profili di accesso ai contenuti
* I clienti possono anche creare e pianificare **segmenti di ricommercializzazione personalizzati** specifici in base alle esigenze degli utenti.

## Prerequisiti di integrazione{#integration-prerequisites}

Descrive i prerequisiti per un&#39;integrazione di successo.

Prima di attivare questa integrazione, controllate i seguenti elementi rispetto alle distribuzioni di  Adobe Analytics e del software e-mail.

In questo modo, prima dell&#39;attivazione verranno messe in atto le procedure ottimali e i prerequisiti adeguati, che consentiranno un&#39;integrazione ottimale e di successo.

### Prerequisiti per  Adobe Analytics {#section-ddb9d4f3b283438ea33788f47f35e69a}

* **Suite di rapporti specifica**: Questa integrazione è specifica per la suite di rapporti. Accertatevi di aver selezionato la suite di rapporti desiderata prima di attivare l&#39;integrazione
* **Variabili** Analytics disponibili e configurate: Questa integrazione richiede eventi personalizzati e eVar personalizzati, ed eventualmente eventi aggiuntivi e eVar aggiuntive.

* **Rappresentante** autorizzato: L&#39;abilitazione di questa integrazione potrebbe indurre l&#39;azienda a pagare le tariffe in conformità al contratto di servizio con  Adobe, Inc. o al contratto di assistenza con uno dei  partner  fidati, a seconda dei casi. Attivando questa integrazione, l&#39;Utente dichiara di essere un rappresentante autorizzato della sua azienda; e, come tale, la vostra azienda accetta di pagare le eventuali tariffe indicate nel contratto di servizio sopra descritto.
* **data warehouse** Adobe Analytics: Questa integrazione richiede l&#39;abilitazione  data warehouse Adobe Analytics per generare segmenti di ricommercializzazione. Se non hai attivato il data warehouse, contatta  Adobe per ulteriori informazioni.
* **ID** destinatario: L&#39;integrazione richiede l&#39;acquisizione e la memorizzazione di un &quot;Visitor ID&quot; all&#39;interno di una variabile Analytics ( eVar). L’ID visitatore (spesso denominato &quot;ID destinatario&quot;) è una rappresentazione codificata o numerica di un indirizzo e-mail del sistema Lyris. Questo &quot;ID destinatario&quot; è associato al comportamento a valle dei visitatori sul sito (carrelli abbandonati, acquisti, ecc.) che è riportato nel sistema Lyris e può essere sfruttato per scopi di ricommercializzazione. Durante il processo di configurazione, è necessario identificare un eVar  a tale scopo, quando richiesto dalla procedura guidata.
* **Tracciamento** esterno: Se al momento non state seguendo la procedura ottimale per abilitare il tracciamento esterno per ogni campagna e-mail inviata, dovete farlo per garantire il successo dell&#39;integrazione. Consulta la sezione Lyris di seguito per i dettagli
* **Conformità** alla privacy: È importante comprendere che abilitando il tracciamento dell&#39;ID del destinatario o del visitatore, questa funzione può tenere traccia delle informazioni personali dei visitatori del sito. Ciò ha implicazioni sulla privacy, che richiedono l&#39;implementazione di procedure appropriate da parte dell&#39;organizzazione, ad esempio l&#39;informativa e il consenso dei visitatori del sito.

### Prerequisiti per Lyris EmailLabs {#section-84abae9401224a3699fed861f715ebde}

* **Account** Lyris valido: Per utilizzare questa integrazione del connettore dati, è necessario avere un account Lyris valido.
* **Informazioni** account: Durante la configurazione dell&#39;integrazione avrete bisogno delle seguenti informazioni sul vostro account Lyris:

   * *Lyris API Key*: Utilizzato per la popolazione di dati
   * *Parametri* stringa query: Questi vengono aggiunti nell’URL della pagina di destinazione per ID messaggio e ID destinatario (ID visitatore).
   * *Lyris Server/URL*: Il valore del server utilizzato nel sistema Lyris
   * *ID* sito Lyris: Noto anche come &quot;ID cliente&quot;, questo è il valore unico per la vostra istanza di Lyris HQ. Questo si trova in &quot;Informazioni cliente&quot; nella sezione &quot;Home account&quot; di EmailLabs.

## Configurare  variabili Adobe Analytics per Lyris{#configure-adobe-analytics-variables-for-lyris}

Descrive le eVar ed Eventi da riservare per ogni implementazione della suite di rapporti.

Questa integrazione richiede che siano riservate almeno 2 eVar per ogni implementazione della suite di rapporti. A parte queste eVar, alcuni eventi possono essere riservati a seconda dei dati Lyris che vorresti vedere in Analytics. Tali eVar ed eventi sono descritti nella tabella seguente:

<table id="table_43E32344E9E54FED8491F28047249329"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo di variabile </th> 
   <th colname="col2" class="entry"> Variable Name </th> 
   <th colname="col3" class="entry"> Modalità di utilizzo della variabile </th> 
   <th colname="col4" class="entry"> Impostazioni </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> ID messaggio </td> 
   <td colname="col3"> Per acquisire l'identificazione della campagna con i singoli messaggi e-mail </td> 
   <td colname="col4"> <p>Stato: Abilitato </p> <p>Allocazione: Più recenti </p> <p>Scadenza dopo: "Decisione aziendale" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">  eVar </td> 
   <td colname="col2"> Email Recipient ID </td> 
   <td colname="col3"> Per acquisire l'identificazione anonima del cliente che ha fatto clic sulla campagna e-mail </td> 
   <td colname="col4"> <p>Stato: Abilitato </p> <p>Allocazione: Più recenti </p> <p>Scadenza dopo: "Decisione aziendale" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - E-Mail Inviate </td> 
   <td colname="col3"> Per memorizzare il numero. delle email inviate da Lyris </td> 
   <td colname="col4">Tipo: Numerico <p>Partecipazione: Abilitato </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - E-Mail Aperte </td> 
   <td colname="col3"> Per memorizzare il numero. di e-mail che sono state aperte </td> 
   <td colname="col4">Tipo: Numerico <p>Partecipazione: Abilitato </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - E-Mail Uniche Aperte </td> 
   <td colname="col3"> Per memorizzare il numero. di e-mail univoche aperte </td> 
   <td colname="col4">Tipo: Numerico <p>Partecipazione: Abilitato </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - Click-through e-mail </td> 
   <td colname="col3"> Per memorizzare il numero. di volte in cui è stato fatto clic su qualsiasi e-mail </td> 
   <td colname="col4">Tipo: Numerico <p>Partecipazione: Abilitato </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - E-Mail Bounce </td> 
   <td colname="col3"> Per memorizzare il no. di e-mail rimbalzate </td> 
   <td colname="col4">Tipo: Numerico <p>Partecipazione: Abilitato </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - E-Mail Annulla sottoscrizione </td> 
   <td colname="col3"> Per memorizzare il no. di iscrizioni e-mail disattivate </td> 
   <td colname="col4">Tipo: Numerico <p>Partecipazione: Abilitato </p> </td> 
  </tr> 
 </tbody> 
</table>
