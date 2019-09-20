---
description: La procedura guidata di integrazione dei connettori dati illustra il processo di integrazione dei connettori dati.
seo-description: La procedura guidata di integrazione dei connettori dati illustra il processo di integrazione dei connettori dati.
seo-title: Esecuzione dell'integrazione guidata Connettori dati
title: Esecuzione dell'integrazione guidata Connettori dati
uuid: 714417f7-c1df-4e61-a07f-d319f6581c9c
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Esecuzione dell'integrazione guidata Connettori dati{#running-the-data-connectors-integration-wizard}

La procedura guidata di integrazione dei connettori dati illustra il processo di integrazione dei connettori dati.

Per configurare l'integrazione:

1. Accedi a Experience Cloud.
1. Nella home page di Adobe Analytics, fai clic sull'icona Connettori dati™ sulla rotellina o sulla barra degli strumenti.
1. Nella pagina Connettori dati, seleziona la Suite di rapporti in cui vuoi configurare l'integrazione.

   >[!NOTE]
   >
   >Accertatevi di selezionare la suite di rapporti desiderata dall'elenco a discesa Suite **di** rapporti nell'angolo superiore sinistro della pagina Connettori dati.

1. Fate clic sulla scheda **Alfabetico** nella parte superiore dell'Elenco **** partner a sinistra dell'interfaccia utente Connettori dati, quindi individuate l'icona **Datran** .
1. Trascina l’icona **Datran** su uno slot plug-in vuoto nella suite di rapporti di Adobe Analytics per avviare l’integrazione guidata Connettori dati.

1. Nella pagina di introduzione dell'integrazione dei dati, rivedete il testo, quindi selezionate la casella di controllo per accettare le spese associate all'integrazione, quindi fate clic su **Avanti**.

   Questa pagina fornisce una panoramica dell’integrazione, con utili collegamenti per ulteriori informazioni. A questa integrazione sono associate sia le tariffe Adobe che Datran. Contatta i rappresentanti di vendita appropriati per entrambe le organizzazioni e assicurati di conoscere la struttura delle tariffe.
1. In ogni pagina dell'Integrazione guidata Connettori dati, fornire le informazioni necessarie, come descritto nella tabella seguente:

<table id="table_74EC1EEBE7A548AB878AA40187EBCD30"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" valign="top" align="left" class="entry"> <p><b>N. PAGINA GUIDATA</b> </p> </th> 
   <th colname="col2" class="entry"> <p><b>CAMPO</b> </p> </th> 
   <th colname="col3" class="entry"> <p><b>DESCRIPTION</b> </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2" valign="top" align="left"> <p>Nome integrazione </p> </td> 
   <td colname="col3"> <p>Specifica il nome dell'integrazione visualizzato dai Connettori dati nell'elenco Integrazione attiva della suite di rapporti. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>Indirizzo e-mail integrazione </p> </td> 
   <td colname="col3"> <p>Specificate l'indirizzo e-mail che riceve tutte le notifiche correlate a questa integrazione, quindi fate clic su <b>Avanti</b> per passare al Passaggio 2 della procedura guidata. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>ID account </p> </td> 
   <td colname="col3"> <p>Specificate l'ID account di data (l'identificatore univoco assegnato alla vostra organizzazione da Datran), quindi fate clic su <b>Avanti</b> per passare al Passaggio 3 della procedura guidata. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>ID messaggio </p> </td> 
   <td colname="col3"> <p>Identificare l'eVar di Adobe Analytics utilizzata per tenere traccia dell'ID messaggio e-mail. </p> <p>L'ID messaggio viene utilizzato per le campagne di marketing/remarketing. L'ID messaggio viene spesso definito "Codice di tracciamento". </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>ID destinatario </p> </td> 
   <td colname="col3"> <p>Identificare l'eVar di Adobe Analytics utilizzata per tenere traccia dell'ID destinatario e-mail. </p> <p>L'ID destinatario viene utilizzato per campagne di marketing/remarketing. L’ID messaggio è spesso denominato "Codice visitatore". </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Casella di controllo Accettazione </p> </td> 
   <td colname="col3"> <p>Esaminare le informazioni visualizzate accanto alla casella di controllo Accettazione: </p> <p><i>Comprendo che abilitando il tracciamento "ID destinatario", questa funzione può tenere traccia delle informazioni personali dei visitatori del nostro sito. Questo ha implicazioni sulla privacy che richiedono l'implementazione di procedure appropriate da parte della mia organizzazione, come ad esempio l'informativa e il consenso dei visitatori del nostro sito. </i> </p> <p>Se accetti l'istruzione di accettazione, seleziona la casella di controllo, quindi fai clic su <b>Avanti</b> per passare al Passaggio 4 della procedura guidata. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>Segmenti a livello di suite di rapporti definiti dal client </p> </td> 
   <td colname="col3"> <p>Questa integrazione crea i segmenti definiti dal partner visualizzati sul lato sinistro della pagina Segmenti di integrazione della procedura guidata di integrazione. </p> <p>Inoltre, puoi selezionare segmenti esistenti a livello di suite di rapporti da includere nell'integrazione. </p> <p>Seleziona i segmenti desiderati sul lato destro della pagina, quindi fai clic su <b>Avanti</b> per passare al Passaggio 5 della procedura guidata. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Clic </p> </td> 
   <td colname="col3"> <p>Specificate l'evento Adobe Analytics che memorizza i dati del messaggio e-mail Click importati dal sistema e-mail. </p> <p>L’evento Clic consente di visualizzare il numero di visitatori che hanno fatto clic sul messaggio e-mail. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Aperto </p> </td> 
   <td colname="col3"> <p>Specificate l'evento Adobe Analytics che memorizza i dati dell'e-mail di apertura importati dal sistema e-mail. </p> <p>L’evento Opened (Apertura) consente di visualizzare il numero di visitatori che hanno aperto il messaggio e-mail. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Inviato </p> </td> 
   <td colname="col3"> <p>Specificate l'evento Adobe Analytics che memorizza i dati e-mail inviati importati dal sistema e-mail. </p> <p>L’evento Clic consente di visualizzare il numero di messaggi e-mail inviati. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Totale importi </p> </td> 
   <td colname="col3"> <p>Specificate l'evento Adobe Analytics che memorizza i dati dell'e-mail Totale bacheche importati dal sistema e-mail. </p> <p>L'evento Totale rimbalzi consente di visualizzare il numero di messaggi e-mail che non sono stati inviati ai destinatari a causa di un problema di consegna. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Annulla sottoscrizione </p> </td> 
   <td colname="col3"> <p>Specificate l'evento Adobe Analytics in cui vengono memorizzati i dati dell'e-mail di annullamento della sottoscrizione importati dal sistema e-mail. </p> <p>L’evento Annulla sottoscrizione consente di visualizzare il numero di visitatori che hanno aperto il messaggio e-mail e hanno quindi fatto clic sul collegamento Annulla sottoscrizione per rifiutare i messaggi e-mail futuri della vostra organizzazione. </p> <p>Fare clic su Avanti per passare al Passaggio 6 della procedura guidata. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>Raccolta dati: Plug-in JavaScript </p> </td> 
   <td colname="col3"> <p>Selezionate Plug-in <b></b> JavaScript se desiderate utilizzare il plug-in come modello di raccolta per questa integrazione, quindi fate clic su <b>Avanti</b> per passare al Passaggio 7 della procedura guidata. </p> <p> <p>Nota:  La soluzione automatizzata è la selezione predefinita. </p> </p> <p>Per ottenere una copia del plug-in JavaScript utilizzato per questa integrazione, contattate il vostro consulente Adobe. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p>Raccolta dati: Soluzione automatizzata </p> </td> 
   <td colname="col3"> <p>Selezionate <b>Automated Solution</b> se desiderate utilizzare un modello di raccolta automatizzata per questa integrazione, quindi specificate gli identificatori univoci utilizzati per questa integrazione. </p> <p> <p>Nota:  La soluzione automatizzata è la selezione predefinita. </p> </p> <p>Se selezionate questa opzione, specificate gli identificatori univoci utilizzati per l'integrazione: </p> <p><b>Parametro stringa query ID messaggio:</b>questo valore rappresenta l’ID messaggio aggiunto all’URL della pagina di destinazione dal partner e-mail. </p> <p><b></b> Parametro stringa query ID destinatario: Questo valore rappresenta l’ID destinatario aggiunto all’URL della pagina di destinazione dal partner e-mail. </p> <p>Fare clic su <b>Avanti</b> per passare al Passaggio 7 della procedura guidata. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>Riepilogo integrazione </p> </td> 
   <td colname="col3"> <p>Verifica i parametri di integrazione facendo clic sul segno più (+) accanto a ciascuna categoria, quindi fai clic su <b>Salva</b> per passare al Passaggio 8 della procedura guidata. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p>Integrazione completa </p> </td> 
   <td colname="col3"> <p>Fate clic su <b>Fine</b> per completare l'integrazione. </p> <p><b></b> IMPORTANTE: Adobe Analytics non salva le impostazioni di integrazione finché non fai clic su <b>Fine</b>. </p> </td> 
  </tr> 
 </tbody> 
</table>

