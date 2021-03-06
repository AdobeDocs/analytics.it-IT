---
description: Utilizza il connettore dati Selligent con Adobe Analytics.
title: Connettore dati Selligent per Adobe Analytics
uuid: e16c3ca6-b131-44b1-a36c-e39697677a96
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '896'
ht-degree: 4%

---


# Connettore dati Selligent per Adobe Analytics{#selligent-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>La tecnologia Adobe Data Connector terminerà il 1° agosto 2021. [Ulteriori informazioni...](/help/import/data-connectors/data-connectors-eol.md)

Questa integrazione include i seguenti vantaggi principali:

* Consolidare i dati di marketing e analisi e-mail in un’unica interfaccia di reporting.
* Ottimizza le campagne e-mail in base alla conversione e al contributo ai ricavi e al successo del sito.
* Effettua il remarketing per visitatori chiave e segmenti di mercato basati su segmenti di marketing dinamici.

## Segmenti di marketing dinamici {#section-a2216f3339304636bd5417249bd635a4}

Questa integrazione e-mail supporta segmenti di marketing dinamici per aiutarti a guidare la tua attività. Questa integrazione offre i seguenti segmenti di marketing:

| Segmento | Descrizione |
|---|---|
| **Profilo di abbandono del carrello** | Aiuta i visitatori a convertirsi ai clienti attraverso campagne ottimizzate appositamente progettate per coloro che esitano a completare i carrelli. |
| **Profilo acquisti** | Aumenta gli ordini ripetuti e il valore medio dell’ordine attraverso le campagne mirate dai pattern di acquisto dei visitatori. |
| **Profilo comportamentale visualizzazione prodotto/contenuto** | Puoi raggiungere potenziali clienti attraverso segmenti di marketing basati sulle visualizzazioni dei prodotti e sulla profilazione dell’accesso ai contenuti. |
| **Segmenti di remarketing personalizzati** | I clienti possono anche creare e pianificare segmenti di ricommercializzazione personalizzati specifici per le esigenze dei loro utenti. |

## Prima di attivare questa integrazione{#before-you-activate-this-integration}

Prima di attivare questa integrazione, controlla i seguenti elementi rispetto alle distribuzioni di Adobe Analytics e del software e-mail.

In questo modo, prima dell’attivazione verranno applicate le best practice e i prerequisiti appropriati. Ciò si tradurrà in un&#39;integrazione ottimale e di successo.

## Prerequisiti per Adobe Analytics{#prerequisites-for-adobe-analytics}

Elenca le azioni necessarie da eseguire in Adobe Analytics prima di poter distribuire l’integrazione.

| Prerequisito | Note |
|---|---|
| Seleziona suite di rapporti | Questa integrazione è specifica per la suite di rapporti. Assicurati di aver selezionato la suite di rapporti desiderata prima di attivare l’integrazione. |
| Configurare le variabili di Analytics | Questa integrazione richiede eventi personalizzati ed eVar personalizzati ed eventualmente eventi aggiuntivi ed eVar aggiuntivi. Consulta Configurazione delle variabili di Analytics per Selligent. |
| Rappresentante autorizzato | L’abilitazione di questa integrazione potrebbe comportare costi per l’azienda in conformità al contratto di servizio con Adobe, Inc. o al contratto di servizio con uno dei partner fidati di Adobe, a seconda dei casi. Attivando questa integrazione, l&#39;utente dichiara di essere un rappresentante autorizzato della sua azienda; e in quanto tale, la tua azienda accetta di pagare le eventuali tariffe stabilite nel contratto di servizio sopra descritto. |
| Abilita Adobe Data Warehouse™ | Questa integrazione richiede l’abilitazione della Data Warehouse per generare segmenti di remarketing. Se non hai abilitato la Data Warehouse Adobe, contatta l’Adobe per ulteriori informazioni. |
| Recipient ID | L’integrazione richiede l’acquisizione e la memorizzazione di un &quot;ID visitatore&quot; all’interno di una variabile di Analytics (eVar). L’ID visitatore (spesso denominato &quot;ID destinatario&quot;) è una rappresentazione codificata o numerica di un indirizzo e-mail dal sistema Selligent. Questo &quot;ID destinatario&quot; è associato al comportamento dei visitatori a valle sul sito (abbandoni il carrello, acquisti, ecc.) che viene richiamato nel sistema Selligent e può essere utilizzato a scopo di remarketing. Come parte del processo di configurazione, è necessario identificare un eVar a questo scopo quando richiesto dalla procedura guidata. |
| Tracciamento esterno | Se al momento non segui la best practice per abilitare il tracciamento esterno per ogni campagna e-mail inviata, devi farlo per garantire il successo dell’integrazione. Per ulteriori informazioni, consulta la sezione Selligent . |
| Conformità alla privacy | È importante comprendere che abilitando il tracciamento del Destinatario o del Visitatore ID, questa funzione può tracciare le informazioni personali dei visitatori del sito. Questo ha implicazioni in materia di privacy che richiedono l’implementazione di procedure appropriate da parte dell’organizzazione, ad esempio l’invio di avvisi ai visitatori del sito e il loro consenso. |

## Configura le variabili di Analytics per Selligent{#configure-analytics-variables-for-selligent}

Questa integrazione richiede 2 eVar da riservare per ogni implementazione della suite di rapporti.

Oltre a queste eVar, alcuni eventi possono essere riservati a seconda dei dati di Selligent, che desideri visualizzare in Analytics. Queste eVar ed eventi sono descritti come segue:

<table id="table_2FFB865DBD80412F90DA8E224B12FB62"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo di variabile </th> 
   <th colname="col2" class="entry"> Nome variable </th> 
   <th colname="col3" class="entry"> Come viene utilizzato </th> 
   <th colname="col4" class="entry"> Impostazioni </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> ID messaggio </td> 
   <td colname="col3"> Per acquisire l’identificazione della campagna dei singoli messaggi e-mail. </td> 
   <td colname="col4"> <p><b>Stato</b>: Abilitato </p> <p><b>Allocazione</b>: Più recente </p> <p><b>Scadenza dopo</b>: "Decisione aziendale" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eV ar </td> 
   <td colname="col2"> ID destinatario </td> 
   <td colname="col3"> Per acquisire l’identificazione anonima del cliente che ha fatto clic sulla campagna e-mail. </td> 
   <td colname="col4"> <p><b>Stato</b>: Abilitato </p> <p><b>Allocazione</b>: Più recente </p> <p><b>Scadenza dopo</b>: "Decisione aziendale" </p> </td> 
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
   <td colname="col3"> Memorizzare il numero di e-mail consegnate. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numerico </p> <p><b>Partecipazione</b>: Abilitato </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Viste </td> 
   <td colname="col3"> Memorizzare il numero di e-mail univoche visualizzate. </td> 
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
   <td colname="col2"> Rimbalzato </td> 
   <td colname="col3"> Memorizzare il numero di e-mail rimbalzate. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numerico </p> <p><b>Partecipazione</b>: Abilitato </p> </td> 
  </tr> 
 </tbody> 
</table>

## Prerequisiti per Selligent{#prerequisites-for-selligent}

Elenca le informazioni necessarie da fornire dall’account Selligent prima di poter distribuire l’integrazione.

**Account Selligent valido**

Per utilizzare questa integrazione dei Data Connectors, è necessario disporre di un account Selligent valido.

**Informazioni sull&#39;account**

Durante questa configurazione dell’integrazione, dovrai ottenere le seguenti informazioni sul tuo account Selligent:

* **URL** del servizio Adobe:

   L’URL può essere derivato dall’URL utilizzato per accedere alla soluzione Selligent Marketing. Sostituisci la parte &quot;/simweb/login.aspx&quot; dell’url con &quot;/automation/omniture.asmx&quot;

   Ad esempio: `http://<client-specific install url>/automation/omniture.asmx`

* **Parametri stringa di query:** questi vengono aggiunti all’URL della pagina di destinazione per ID messaggio e ID destinatario (ID visitatore). Sono sempre MID e RID rispettivamente per ID messaggio e ID destinatario.

* **Integrazione** TokenAvvia lo strumento Manager dall&#39;interno di Simweb e vai a  **[!UICONTROL Configuration]** >  **[!UICONTROL System Settings]** >  **[!UICONTROL General]** scheda >  **[!UICONTROL System]**. Alla voce **[!UICONTROL Security]**, puoi trovare il token di integrazione.

   ![](assets/selligent-integration_token.png)
