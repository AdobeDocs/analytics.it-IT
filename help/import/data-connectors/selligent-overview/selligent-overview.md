---
description: 'null'
title: Connettore dati Selligent per Adobe Analytics
uuid: e16c3ca6-b131-44b1-a36c-e39697677a96
translation-type: tm+mt
source-git-commit: 3850dc3503ca57ba4f13f0de63e8420e484db501
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 4%

---


# Connettore dati Selligent per Adobe Analytics{#selligent-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>La tecnologia del Connettore dati del Adobe  terminerà il 1 agosto 2021. [Ulteriori informazioni...](/help/import/data-connectors/data-connectors-eol.md)

Questa integrazione include i seguenti vantaggi principali:

* Consolidare i dati di marketing e analisi e-mail in un&#39;unica interfaccia di reporting.
* Ottimizzate le campagne e-mail mediante la conversione e il contributo alle entrate e al successo del sito.
* Rivendita i visitatori principali e i segmenti di mercato basati su segmenti di marketing dinamici.

## Segmenti di marketing dinamici {#section-a2216f3339304636bd5417249bd635a4}

Questa integrazione delle e-mail supporta segmenti di marketing dinamici per aiutarti a promuovere la tua attività. Questa integrazione include i seguenti segmenti di marketing:

| Segmento | Descrizione |
|---|---|
| **Profilo di abbandono carrello** | Aiuta i visitatori a convertirsi ai clienti attraverso campagne ottimizzate appositamente progettate per coloro che esitano a completare i carrelli. |
| **Profilo acquisti** | Aumentare gli ordini ripetuti e il valore medio degli ordini attraverso campagne mirate da pattern di acquisto dei visitatori. |
| **Profilo comportamentale visualizzazione prodotto/contenuto** | Raggiungi potenziali clienti attraverso segmenti di marketing basati su viste di prodotto e profili di accesso ai contenuti. |
| **Segmenti di remarketing personalizzati** | I clienti possono anche creare e pianificare segmenti di ricommercializzazione personalizzati in base alle esigenze dei propri utenti. |

## Prima di attivare questa integrazione{#before-you-activate-this-integration}

Prima di attivare questa integrazione, controllate i seguenti elementi rispetto alle distribuzioni di  Adobe Analytics e del software e-mail.

In questo modo, prima dell&#39;attivazione verranno applicate le procedure ottimali e i prerequisiti adeguati. In questo modo l&#39;integrazione sarà ottimale e di successo.

## Prerequisiti per  Adobe Analytics{#prerequisites-for-adobe-analytics}

Elenca le azioni necessarie per eseguire  Adobe Analytics prima di poter distribuire l&#39;integrazione.

| Prerequisito | Note |
|---|---|
| Seleziona suite di rapporti | Questa integrazione è specifica per la suite di rapporti. Prima di attivare l&#39;integrazione, accertatevi di aver selezionato la suite di rapporti desiderata. |
| Configurare le variabili di Analytics | Questa integrazione richiede eventi personalizzati e eVar personalizzati, ed eventualmente eventi aggiuntivi e eVar aggiuntive. Consultate Configurazione delle variabili Analytics per la firma. |
| Rappresentante autorizzato | L&#39;abilitazione di questa integrazione potrebbe indurre l&#39;azienda a pagare le tariffe in conformità al contratto di servizio con  Adobe, Inc. o al contratto di assistenza con uno dei  partner  fidati, a seconda dei casi. Attivando questa integrazione, l&#39;Utente dichiara di essere un rappresentante autorizzato della sua azienda; e, come tale, la vostra azienda accetta di pagare le eventuali tariffe indicate nel contratto di servizio sopra descritto. |
| Abilita  Adobe Data Warehouse™ | Questa integrazione richiede che la Data Warehouse sia abilitata per generare segmenti di remarketing. Se non avete attivato l&#39;Data Warehouse  Adobe, contattate  Adobe per ulteriori informazioni. |
| Recipient ID | L&#39;integrazione richiede l&#39;acquisizione e la memorizzazione di un &quot;Visitor ID&quot; all&#39;interno di una variabile Analytics ( eVar). L’ID visitatore (spesso denominato &quot;ID destinatario&quot;) è una rappresentazione codificata o numerica di un indirizzo e-mail del sistema mittente. Questo &quot;ID destinatario&quot; è associato al comportamento a valle dei visitatori sul sito (carrelli abbandonati, acquisti, ecc.) che viene richiamato nel sistema Selligent e può essere sfruttato per scopi di remarketing. Durante il processo di configurazione, è necessario identificare un eVar  a tale scopo, quando richiesto dalla procedura guidata. |
| Tracciamento esterno | Se al momento non state seguendo la procedura ottimale per abilitare il tracciamento esterno per ogni campagna e-mail inviata, dovete farlo per garantire il successo dell&#39;integrazione. Per informazioni dettagliate, consulta la sezione Partecipanti di seguito. |
| Conformità alla privacy | È importante comprendere che abilitando il tracciamento dell&#39;ID del destinatario o del visitatore, questa funzione può tenere traccia delle informazioni personali dei visitatori del sito. Questo ha implicazioni sulla privacy che richiedono l&#39;implementazione di procedure appropriate da parte dell&#39;organizzazione, ad esempio l&#39;informativa e il consenso dei visitatori del sito. |

## Configurare le variabili di Analytics per Selligent{#configure-analytics-variables-for-selligent}

Questa integrazione richiede che siano riservate 2 eVar per ogni implementazione della suite di rapporti.

A parte queste eVar, alcuni eventi possono essere riservati in base ai dati di Selligent, che si desidera visualizzare in Analytics. Tali eVar ed eventi sono descritti di seguito:

<table id="table_2FFB865DBD80412F90DA8E224B12FB62"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo di variabile </th> 
   <th colname="col2" class="entry"> Variable Name </th> 
   <th colname="col3" class="entry"> Modalità di utilizzo </th> 
   <th colname="col4" class="entry"> Impostazioni </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> ID messaggio </td> 
   <td colname="col3"> Per acquisire l'identificazione della campagna con i singoli messaggi e-mail. </td> 
   <td colname="col4"> <p><b>Stato</b>: Abilitato </p> <p><b>Allocazione</b>: Più recenti </p> <p><b>Scadenza dopo</b>: "Decisione aziendale" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eV ar </td> 
   <td colname="col2"> ID destinatario </td> 
   <td colname="col3"> Per acquisire l'identificazione anonima del cliente che ha fatto clic sulla campagna e-mail. </td> 
   <td colname="col4"> <p><b>Stato</b>: Abilitato </p> <p><b>Allocazione</b>: Più recenti </p> <p><b>Scadenza dopo</b>: "Decisione aziendale" </p> </td> 
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
   <td colname="col3"> Per memorizzare il numero di e-mail che sono state recapitate. </td> 
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
   <td colname="col2"> Rimbalzato </td> 
   <td colname="col3"> Per memorizzare il numero di e-mail rimbalzate. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numerico </p> <p><b>Partecipazione</b>: Abilitato </p> </td> 
  </tr> 
 </tbody> 
</table>

## Prerequisiti per Selligent{#prerequisites-for-selligent}

Elenca le informazioni necessarie da fornire dall&#39;account Selligent prima di poter distribuire l&#39;integrazione.

**Account Selligent Valido**

Per utilizzare questa integrazione con i connettori dati, è necessario disporre di un account Selligent valido.

**Informazioni account**

Durante questa configurazione dell&#39;integrazione, dovrete disporre delle seguenti informazioni sull&#39;account Selligent:

* **URL** del servizio Adobe:

   L’URL può essere derivato dall’URL utilizzato per accedere alla soluzione Selligent Marketing. Sostituisce la parte &quot;/simweb/login.aspx&quot; dell’URL con &quot;/automation/omniture.asmx&quot;.

   Ad esempio: `http://<client-specific install url>/automation/omniture.asmx`

* **Parametri stringa query:** questi vengono aggiunti nell’URL della pagina di destinazione per ID messaggio e ID destinatario (ID visitatore). Sono sempre MID e RID rispettivamente per ID messaggio e ID destinatario.

* **Integration** TokenAvviate lo strumento Manager dall&#39;interno di Simweb e andate a  **[!UICONTROL Configuration]** >  **[!UICONTROL System Settings]** >  **[!UICONTROL General]** tab >  **[!UICONTROL System]**. In **[!UICONTROL Security]** è possibile trovare il token di integrazione.

   ![](assets/selligent-integration_token.png)
