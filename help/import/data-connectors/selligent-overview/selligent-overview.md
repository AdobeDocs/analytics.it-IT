---
description: nulle
solution: Analytics
title: Connettore dati intelligente per Adobe Analytics
uuid: e16c3ca6-b131-44b1-a36c-e39697677a96
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Connettore dati intelligente per Adobe Analytics{#selligent-data-connector-for-adobe-analytics}

Questa integrazione include i seguenti vantaggi principali:

* Consolidare i dati di marketing e analisi e-mail in un'unica interfaccia di reporting.
* Ottimizzate le campagne e-mail mediante la conversione e il contributo alle entrate e al successo del sito.
* Rivendita i visitatori principali e i segmenti di mercato basati su segmenti di marketing dinamici.

## Segmenti di marketing dinamici {#section-a2216f3339304636bd5417249bd635a4}

Questa integrazione delle e-mail supporta segmenti di marketing dinamici per aiutarti a promuovere la tua attività. Questa integrazione include i seguenti segmenti di marketing:

| Segmento | Descrizione |
|---|---|
| **Profilo di abbandono carrello** |  Aiuta i visitatori a convertirsi ai clienti attraverso campagne ottimizzate appositamente progettate per coloro che esitano a completare i carrelli. |
| **Profilo acquisti** |  Aumentare gli ordini ripetuti e il valore medio degli ordini attraverso campagne mirate da pattern di acquisto dei visitatori. |
| **Profilo comportamentale visualizzazione prodotto/contenuto** |  Raggiungi potenziali clienti attraverso segmenti di marketing basati su viste di prodotto e profili di accesso ai contenuti. |
| **Segmenti di remarketing personalizzati** | I clienti possono anche creare e pianificare segmenti di ricommercializzazione personalizzati in base alle esigenze dei propri utenti. |

## Prima di attivare questa integrazione{#before-you-activate-this-integration}

Prima di attivare questa integrazione, controlla i seguenti elementi rispetto alle distribuzioni di Adobe Analytics e del software e-mail.

In questo modo, prima dell'attivazione verranno applicate le procedure ottimali e i prerequisiti adeguati. In questo modo l'integrazione sarà ottimale e di successo.

## Prerequisiti per Adobe Analytics{#prerequisites-for-adobe-analytics}

Elenca le azioni necessarie da eseguire in Adobe Analytics prima di poter distribuire l'integrazione.

| Prerequisito | Note |
|---|---|
| Seleziona suite di rapporti | Questa integrazione è specifica per la suite di rapporti. Prima di attivare l'integrazione, accertatevi di aver selezionato la suite di rapporti desiderata. |
| Configurare le variabili di Analytics |  Questa integrazione richiede eventi personalizzati e eVar personalizzati, ed eventualmente eventi aggiuntivi e eVar aggiuntive. Consultate Configurazione delle variabili Analytics per la firma. |
| Rappresentante autorizzato |  L'abilitazione di questa integrazione potrebbe indurre l'azienda a sostenere delle spese in conformità al contratto di servizio stipulato con Adobe, Inc. o al contratto di assistenza stipulato con uno dei partner fidati di Adobe, a seconda dei casi. Attivando questa integrazione, l'Utente dichiara di essere un rappresentante autorizzato della sua azienda; e, come tale, la vostra azienda accetta di pagare le eventuali tariffe indicate nel contratto di servizio sopra descritto. |
| Abilita Adobe Data Warehouse™ |  Questa integrazione richiede che Data Warehouse sia abilitato per generare segmenti di remarketing. Se non hai attivato Adobe Data Warehouse, contatta Adobe per ulteriori informazioni. |
| Recipient ID |  L'integrazione richiede l'acquisizione e la memorizzazione di un "Visitor ID" in una variabile di Analytics (eVar). L’ID visitatore (spesso denominato "ID destinatario") è una rappresentazione codificata o numerica di un indirizzo e-mail del sistema mittente. Questo "ID destinatario" è associato al comportamento a valle dei visitatori sul sito (carrelli abbandonati, acquisti, ecc.) che viene richiamato nel sistema Selligent e può essere sfruttato per scopi di remarketing. Durante il processo di configurazione, è necessario identificare un'eVar a tale scopo quando richiesto dalla procedura guidata. |
| Tracciamento esterno |  Se al momento non state seguendo la procedura ottimale per abilitare il tracciamento esterno per ogni campagna e-mail inviata, dovete farlo per garantire il successo dell'integrazione. Per informazioni dettagliate, consulta la sezione Partecipanti di seguito. |
| Conformità alla privacy |  È importante comprendere che abilitando il tracciamento dell'ID destinatario o visitatore, questa funzione può tenere traccia delle informazioni personali dei visitatori del sito. Questo ha implicazioni sulla privacy che richiedono l'implementazione di procedure appropriate da parte dell'organizzazione, ad esempio l'informativa e il consenso dei visitatori del sito. |

## Configurare le variabili Analytics per la firma{#configure-analytics-variables-for-selligent}

Questa integrazione richiede che siano riservate 2 eVar per ogni implementazione della suite di rapporti.

A parte queste eVar, alcuni eventi possono essere riservati in base ai dati di Selligent, che si desidera visualizzare in Analytics. Tali eVar ed eventi sono descritti di seguito:

<table id="table_2FFB865DBD80412F90DA8E224B12FB62"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo di variabile </th> 
   <th colname="col2" class="entry"> Nome della variabile </th> 
   <th colname="col3" class="entry"> Modalità di utilizzo </th> 
   <th colname="col4" class="entry"> Impostazioni </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> ID messaggio </td> 
   <td colname="col3"> Per acquisire l'identificazione della campagna con i singoli messaggi e-mail. </td> 
   <td colname="col4"> <p><b>Stato</b>: Abilitato </p> <p><b>Allocazione</b>:Più recenti </p> <p><b>Scadenza dopo</b>: "Decisione aziendale" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eV ar </td> 
   <td colname="col2"> Recipient ID </td> 
   <td colname="col3"> Per acquisire l'identificazione anonima del cliente che ha fatto clic sulla campagna e-mail. </td> 
   <td colname="col4"> <p><b>Stato</b>: Abilitato </p> <p><b>Allocazione</b>:Più recenti </p> <p><b>Scadenza dopo</b>: "Decisione aziendale" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Inviato </td> 
   <td colname="col3"> Per memorizzare il numero di e-mail inviate da Selligent. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numerico </p> <p><b>Partecipazione</b>: Abilitato </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Consegnato </td> 
   <td colname="col3"> Per memorizzare il numero di e-mail distribuite. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numerico </p> <p><b>Partecipazione</b>: Abilitato </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Viste </td> 
   <td colname="col3"> Per memorizzare il numero di e-mail univoche visualizzate. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numerico </p> <p><b>Partecipazione</b>: Abilitato </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Clic </td> 
   <td colname="col3"> Per memorizzare il numero di volte in cui è stato fatto clic su un messaggio e-mail. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numerico </p> <p><b>Partecipazione</b>: Abilitato </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Bloccato </td> 
   <td colname="col3"> Per memorizzare il numero di e-mail rimbalzate. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numerico </p> <p><b>Partecipazione</b>: Abilitato </p> </td> 
  </tr> 
 </tbody> 
</table>

## Prerequisiti per la firma{#prerequisites-for-selligent}

Elenca le informazioni necessarie da fornire dall'account Selligent prima di poter distribuire l'integrazione.

**Account Selligent Valido**

Per utilizzare questa integrazione con i connettori dati, è necessario disporre di un account Selligent valido.

**Informazioni account**

Durante questa configurazione dell'integrazione, dovrete disporre delle seguenti informazioni sull'account Selligent:

* **URL** servizio Adobe:

   L’URL può essere derivato dall’URL utilizzato per accedere alla soluzione Selligent Marketing. Sostituisce la parte "/simweb/login.aspx" dell’url con "/automation/omniture.asmx"

   E.g: `http://<client-specific install url>/automation/omniture.asmx`

* **** Parametri stringa query: Questi vengono aggiunti nell’URL della pagina di destinazione per ID messaggio e ID destinatario (ID visitatore). Sono sempre MID e RID rispettivamente per ID messaggio e ID destinatario.

* **Token** di integrazione Avviate lo strumento Manager dall'interno di Simweb e andate a **[!UICONTROL Configuration]** &gt; **[!UICONTROL System Settings]** &gt; **[!UICONTROL General]** scheda &gt; **[!UICONTROL System]**. In **[!UICONTROL Security]** questa sezione è disponibile il token di integrazione.

   ![](assets/selligent-integration_token.png)
