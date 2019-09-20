---
description: La procedura guidata di integrazione dei connettori dati illustra il processo di integrazione dei connettori dati.
seo-description: La procedura guidata di integrazione dei connettori dati illustra il processo di integrazione dei connettori dati.
seo-title: Integrazione Silverpop
title: Integrazione Silverpop
uuid: dc5e6a09-3238-412d-9980-4a105ce14819
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Integrazione Silverpop{#silverpop-integration}

La procedura guidata di integrazione dei connettori dati illustra il processo di integrazione dei connettori dati.

Per configurare l'integrazione:

1. In Adobe Experience Cloud, seleziona Connettori dati™ dall'elenco a discesa dei prodotti.
1. Fare clic **[!UICONTROL Add New]** e selezionare **[!UICONTROL By Name]** nell'elenco a **[!UICONTROL Show]** discesa.
1. Trova l'icona **Silverpop Engage 2.0** e trascinala in uno slot plug-in vuoto nella suite di rapporti di Analytics per avviare l'Integrazione guidata Connettori dati.
1. Nella pagina di introduzione di Silverpop Integration, rivedete il testo, quindi selezionate la casella di controllo per accettare le tariffe associate all'integrazione.
1. Selezionate la suite di rapporti da utilizzare per questa integrazione.
1. Immettete un nome descrittivo per identificare l'integrazione, quindi fate clic su **[!UICONTROL Create and Configure this Integration]**.

   Questa pagina fornisce una panoramica dell’integrazione, con utili collegamenti per ulteriori informazioni. A questa integrazione sono associate sia le tariffe Adobe che Silverpop. Contatta i rappresentanti di vendita appropriati per entrambe le organizzazioni e assicurati di conoscere la struttura delle tariffe.
1. In ogni pagina dell'Integrazione guidata Connettori dati, fornire le informazioni necessarie, come descritto nella tabella seguente:

<table id="table_74EC1EEBE7A548AB878AA40187EBCD30"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col2" class="entry"> <p> <b>Campo</b> </p> </th> 
   <th colname="col03" valign="top" align="left" class="entry"> <p> <b>Sezione di configurazione</b> </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Descrizione</b> </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col2" valign="top" align="left"> <p>Nome integrazione </p> </td> 
   <td colname="col03"> <p>(1) Impostazioni di integrazione </p> </td> 
   <td colname="col3"> <p>Specifica il nome dell'integrazione visualizzato dai Connettori dati nell'elenco Integrazione attiva della suite di rapporti. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2" valign="top" align="left"> <p>Scarica file </p> </td> 
   <td colname="col03"> <p>(2) Mappature variabili </p> </td> 
   <td colname="col3"> <p> Da utilizzare con il remarketing del download dei file. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> Email Address </p> </td> 
   <td colname="col03"> <p>(2) Mappature variabili </p> </td> 
   <td colname="col3"> <p>Utilizzato per il remarketing per i visitatori senza un ID Silverpop noto. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>ID account </p> </td> 
   <td colname="col03"> <p>(2) Mappature variabili </p> </td> 
   <td colname="col3"> <p>Specificate il vostro ID account Silverpop (l'identificatore univoco assegnato alla vostra organizzazione da Silverpop), quindi fate clic su <b>Avanti</b> per passare al Passaggio 3 della procedura guidata. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Nome modulo </p> </td> 
   <td colname="col03"> <p>(2) Mappature variabili </p> </td> 
   <td colname="col3"> <p>Da utilizzare con remarketing di abbandono del modulo. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>ID postale </p> </td> 
   <td colname="col03"> <p>(2) Mappature variabili </p> </td> 
   <td colname="col3"> <p>(Obbligatorio) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Silverpop ID </p> </td> 
   <td colname="col03"> <p>(2) Mappature variabili </p> </td> 
   <td colname="col3"> <p>(Obbligatorio) </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> Bounce </p> </td> 
   <td colname="col03"> <p>(2) Mappature variabili </p> </td> 
   <td colname="col3"> <p>(Obbligatorio) Specificate l'evento Analytics che memorizza i dati dell'e-mail Totale bacheche importati dal sistema e-mail. </p> <p>L'evento Totale rimbalzi consente di visualizzare il numero di messaggi e-mail che non sono stati inviati ai destinatari a causa di un problema di consegna. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Clic </p> </td> 
   <td colname="col03"> <p>(2) Mappature variabili </p> </td> 
   <td colname="col3"> <p>(Obbligatorio) Specificate l'evento di Analytics in cui sono memorizzati i dati del clic del messaggio e-mail importati dal sistema e-mail. </p> <p>L’evento Clic consente di visualizzare il numero di visitatori che hanno fatto clic sul messaggio e-mail. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> File scaricato </td> 
   <td colname="col03"> <p>(2) Mappature variabili </p> </td> 
   <td colname="col3"> <p> Da utilizzare con il remarketing del download dei file. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> Modulo completato </td> 
   <td colname="col03"> <p>(2) Mappature variabili </p> </td> 
   <td colname="col3"> <p>Da utilizzare con remarketing di abbandono del modulo. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> Modulo avviato </td> 
   <td colname="col03"> <p>(2) Mappature variabili </p> </td> 
   <td colname="col3"> <p>Da utilizzare con remarketing di abbandono del modulo. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Aperto </p> </td> 
   <td colname="col03"> <p>(2) Mappature variabili </p> </td> 
   <td colname="col3"> <p>(Obbligatorio) Specificate l'evento Analytics in cui sono memorizzati i dati dell'e-mail aperta importati dal sistema e-mail. </p> <p>L’evento Opened (Apertura) consente di visualizzare il numero di visitatori che hanno aperto il messaggio e-mail. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Inviato </p> </td> 
   <td colname="col03"> <p>(2) Mappature variabili </p> </td> 
   <td colname="col3"> <p>(Obbligatorio) Specificate l'evento Analytics in cui sono memorizzati i dati e-mail inviati importati dal sistema e-mail. </p> <p>L'evento Inviato consente di visualizzare il numero di messaggi e-mail inviati. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Annulla sottoscrizione </p> </td> 
   <td colname="col03"> <p>(2) Mappature variabili </p> </td> 
   <td colname="col3"> <p>(Obbligatorio) Specificate l'evento di Analytics in cui sono memorizzati i dati di annullamento della sottoscrizione dell'e-mail importati dal sistema e-mail. </p> <p>L’evento Annulla sottoscrizione consente di visualizzare il numero di visitatori che hanno aperto il messaggio e-mail e hanno quindi fatto clic sul collegamento Annulla sottoscrizione per rifiutare i messaggi e-mail futuri della vostra organizzazione. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Segmenti </p> </td> 
   <td colname="col03"> <p>(3) Impostazioni dati </p> </td> 
   <td colname="col3"> <p>Questa integrazione crea i segmenti definiti dal partner visualizzati nella sezione Segmenti partner. </p> <p>Inoltre, puoi selezionare segmenti esistenti a livello di suite di rapporti da includere nell'integrazione. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p> Richieste di accesso </p> </td> 
   <td colname="col03"> <p>(3) Impostazioni dati </p> </td> 
   <td colname="col3"> <p> (Obbligatorio) Abilita <span class="uicontrol"> Consenti integrazione di scaricare i dati</span>del prodotto. </p> <p>Facoltativo: Consenti a questa integrazione di scaricare ricavi, ordini e unità. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Raccolta dati </p> </td> 
   <td colname="col03"> <p>(3) Impostazioni dati </p> </td> 
   <td colname="col3"> <p>Selezionate Plug-in <b></b> JavaScript se desiderate utilizzare il plug-in s_code.js come modello di raccolta per questa integrazione (consultate <a href="../silverpop-overview/silverpop-analytics-code.md#concept-28e7c834a6804a949aa9306f8896b36e" format="dita" scope="local"> Codice</a>plug-in di Analytics). </p> <p>Selezionate <b>Automated Solution</b> se desiderate utilizzare un modello di raccolta automatizzata per questa integrazione, quindi specificate gli identificatori univoci utilizzati per questa integrazione. </p> <p>Se selezionate questa opzione, specificate gli identificatori univoci utilizzati per l'integrazione: </p> <p> <b>Parametro stringa query ID messaggio:</b>questo valore rappresenta l’ID messaggio aggiunto all’URL della pagina di destinazione dal partner e-mail. </p> <p> <b></b> Parametro stringa query ID destinatario: Questo valore rappresenta l’ID destinatario aggiunto all’URL della pagina di destinazione dal partner e-mail. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col2"> <p>Generazione di dashboard e segnalibri </p> </td> 
   <td colname="col03"> <p>(4) Impostazioni rapporto </p> </td> 
   <td colname="col3"> <p>Genera automaticamente dashboard e segnalibri per l'integrazione. </p> </td> 
  </tr> 
 </tbody> 
</table>

