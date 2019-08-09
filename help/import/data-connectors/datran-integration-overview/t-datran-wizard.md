---
description: La procedura guidata Integrazione dei connettori dati ti passaggi attraverso il processo di integrazione dei connettori dati.
seo-description: La procedura guidata Integrazione dei connettori dati ti passaggi attraverso il processo di integrazione dei connettori dati.
seo-title: Esecuzione della procedura guidata Integrazione dei connettori dati
title: Esecuzione della procedura guidata Integrazione dei connettori dati
uuid: 714417 f 7-c 1 df -4 e 61-a 07 f-d 319 f 6581 c 9 c
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Esecuzione della procedura guidata Integrazione dei connettori dati{#running-the-data-connectors-integration-wizard}

La procedura guidata Integrazione dei connettori dati ti passaggi attraverso il processo di integrazione dei connettori dati.

Per configurare l'integrazione:

1. Accedi a Marketing Cloud.
1. Nella home page di Adobe Analytics, fate clic sull'icona Connettori dati™ sulla rotellina o sulla barra degli strumenti.
1. Nella pagina Connettori dati, seleziona la suite di rapporti in cui vuoi configurare l'integrazione.

   >[!NOTE]
   >
   >Make sure that you select the desired report suite from the **Report Suite** drop-down list in the upper-left corner of the Data Connectors page.

1. Click the **Alphabetical** tab at the top of the **Partner List** on the left side of the Data Connectors UI, then locate the **Datran** icon.
1. Trascina l'icona **Data su** un plug-in vuoto nella suite di rapporti di Adobe Analytics per avviare la procedura guidata Integrazione dei connettori dati.

1. Nella pagina introduttiva Integrazione dati, controlla il testo, quindi seleziona la casella di controllo per accettare le tariffe associate all'integrazione, quindi fai clic su **Avanti**.

   Questa pagina fornisce una panoramica dell'integrazione e dei collegamenti utili per ulteriori informazioni. There are both Adobe and Datran fees associated with this integration. Contatta i tuoi rappresentanti vendite appropriati per entrambe le organizzazioni e assicurati di conoscere la struttura delle tariffe.
1. In ogni pagina della procedura guidata Integrazione dei connettori dati, fornisci le informazioni necessarie, come descritto nella tabella seguente:

<table id="table_74EC1EEBE7A548AB878AA40187EBCD30"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" valign="top" align="left" class="entry"> <p><b>Procedura guidata Pagina</b> </p> </th> 
   <th colname="col2" class="entry"> <p><b>FIELD</b> </p> </th> 
   <th colname="col3" class="entry"> <p><b>DESCRIPTION</b> </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2" valign="top" align="left"> <p>Nome integrazione </p> </td> 
   <td colname="col3"> <p>Specifica il nome dell'integrazione che Connettori dati visualizza nell'Elenco integrazione attivo della suite di rapporti. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>Indirizzo e-mail integrazione </p> </td> 
   <td colname="col3"> <p>Specificate l'indirizzo e-mail che riceve tutte le notifiche correlate a questa integrazione, quindi fate clic <b>su Avanti</b> per passare al Passaggio 2 della procedura guidata. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>ID account </p> </td> 
   <td colname="col3"> <p>Specificate l'ID account Datran (l'identificatore univoco assegnato alla vostra organizzazione da Datran), quindi fate clic <b>su Avanti</b> per passare al passaggio 3 della procedura guidata. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>ID messaggio </p> </td> 
   <td colname="col3"> <p>Identifica l'evar di Adobe Analytics utilizzato per tenere traccia dell'ID messaggio e-mail. </p> <p>L'ID messaggio viene usato per campagne di marketing/remarketing. L'ID messaggio viene spesso denominato "Codice di tracciamento". </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>ID destinatario </p> </td> 
   <td colname="col3"> <p>Identifica l'evar di Adobe Analytics utilizzato per tenere traccia dell'ID destinatario e-mail. </p> <p>L'ID destinatario viene usato per campagne di marketing/remarketing. L'ID messaggio viene spesso denominato "Codice visitatore". </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Casella di controllo Accettazione </p> </td> 
   <td colname="col3"> <p>Controlla le informazioni visualizzate accanto alla casella di controllo Accettazione: </p> <p><i>Capisco che abilitando il tracciamento di "ID destinatario", questa funzione potrebbe tenere traccia delle informazioni personali dei nostri visitatori del sito. Ciò ha implicazioni sulla privacy che richiedono l'implementazione delle procedure appropriate dalla mia organizzazione, ad esempio fornire avviso e autorizzare i visitatori del sito. </i> </p> <p>Se accetti l'istruzione di accettazione, seleziona la casella di controllo, quindi fai clic su <b>Avanti</b> per passare al passaggio 4 della procedura guidata. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>Segmenti a livello di suite di rapporti definiti dal cliente </p> </td> 
   <td colname="col3"> <p>Questa integrazione crea i segmenti definiti dal partner visualizzati sul lato sinistro della pagina Segmenti integrazione della procedura guidata Integrazione. </p> <p>Inoltre, puoi selezionare i segmenti esistenti a livello di suite di rapporti da includere nell'integrazione. </p> <p>Seleziona i segmenti desiderati sul lato destro della pagina, quindi fai clic su <b>Avanti</b> per passare al passaggio 5 della procedura guidata. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Clic </p> </td> 
   <td colname="col3"> <p>Specificate l'evento Adobe Analytics che archivia i dati e-mail importati importati dall'e-mail. </p> <p>L'evento Clic permette di visualizzare il numero di visitatori che hanno fatto clic sul messaggio e-mail. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Aperto </p> </td> 
   <td colname="col3"> <p>Specificate l'evento Adobe Analytics che memorizza l'e-mail I dati aperti importati dall'e-mail. </p> <p>L'evento Aperto permette di visualizzare il numero di visitatori che hanno aperto il messaggio e-mail. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Inviato </p> </td> 
   <td colname="col3"> <p>Specificate l'evento Adobe Analytics che archivia l'e-mail di invio dei dati inviati dall'e-mail. </p> <p>L'evento Clic permette di visualizzare il numero di messaggi e-mail inviati. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Totale bounce </p> </td> 
   <td colname="col3"> <p>Specificate l'evento Adobe Analytics che archivia il numero totale di dati importati dall'e-mail system. </p> <p>L'evento Rimbalzi totali permette di visualizzare il numero di messaggi e-mail che non sono stati consegnati ai destinatari a causa di un problema di consegna. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Annullato </p> </td> 
   <td colname="col3"> <p>Specificate l'evento Adobe Analytics che archivia l'e-mail di cancellazione dei dati importati dall'e-mail. </p> <p>L'evento Non iscritto consente di visualizzare il numero di visitatori che hanno aperto il messaggio e-mail, quindi hanno fatto clic sul collegamento Annulla sottoscrizione per rifiutare i messaggi e-mail futuri dall'organizzazione. </p> <p>Fate clic su Avanti per passare al passaggio 6 della procedura guidata. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>Raccolta dati: Plug-in javascript </p> </td> 
   <td colname="col3"> <p>Selezionate <b>Plug-in javascript</b> se desiderate utilizzare il plug-in come modello di raccolta per questa integrazione, quindi fate clic <b>su Avanti</b> per passare al Passaggio 7 della procedura guidata. </p> <p> <p>Nota: La soluzione automatizzata è la selezione predefinita. </p> </p> <p>Contattate il vostro Adobe Consulente per ottenere una copia del plug-in javascript utilizzato per questa integrazione. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>Raccolta dati: Soluzione automatizzata </p> </td> 
   <td colname="col3"> <p>Selezionate <b>Soluzione automatizzata</b> se desiderate utilizzare un modello di raccolta automatizzato per questa integrazione, quindi specificate gli identificatori unici utilizzati per tale integrazione. </p> <p> <p>Nota: La soluzione automatizzata è la selezione predefinita. </p> </p> <p>Se selezionate questa opzione, specificate gli identificatori unici utilizzati per questa integrazione: </p> <p><b>Parametro stringa query ID messaggio:</b>Questo valore rappresenta l'ID messaggio aggiunto all'URL della pagina di destinazione dal vostro partner e-mail. </p> <p><b>Parametro stringa query ID destinatario:</b> Questo valore rappresenta l'ID destinatario aggiunto all'URL della pagina di destinazione dal tuo partner e-mail. </p> <p>Fate clic <b>su Avanti</b> per passare al passaggio 7 della procedura guidata. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>Riepilogo integrazione </p> </td> 
   <td colname="col3"> <p>Verifica i parametri di integrazione facendo clic sul segno più (+) accanto a ciascuna categoria, quindi fai clic <b>su Salva</b> per passare al passaggio 8 della procedura guidata. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p>Integrazione completa </p> </td> 
   <td colname="col3"> <p>Fate clic <b>su Fine</b> per completare l'integrazione. </p> <p><b>IMPORTANTE:</b> Adobe Analytics non salva le impostazioni di integrazione fino a quando non fate clic <b>su Fine</b>. </p> </td> 
  </tr> 
 </tbody> 
</table>

