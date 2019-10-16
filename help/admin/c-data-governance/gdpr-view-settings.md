---
description: La finestra di dialogo Data Governance (Governance dei dati) negli strumenti dell’amministratore offre una panoramica delle suite di rapporti configurate per la governance dei dati, indica se sono state mappate in un’organizzazione Experience Cloud e se per essa sono stati impostati i criteri di conservazione dei dati.
seo-description: La finestra di dialogo Data Governance (Governance dei dati) negli strumenti dell’amministratore offre una panoramica delle suite di rapporti configurate per la governance dei dati, indica se sono state mappate in un’organizzazione Experience Cloud e se per essa sono stati impostati i criteri di conservazione dei dati.
seo-title: Visualizzare/gestire le impostazioni di governance dei dati della suite di rapporti
title: Visualizzare/gestire le impostazioni di governance dei dati della suite di rapporti
uuid: f3b83e8e-00af-4a60-a5de-29b5c43f6788
translation-type: tm+mt
source-git-commit: 3be4e96df12d5e53bf77b1960afc229a1ac6c046

---


# Visualizzare/gestire le impostazioni di governance dei dati della suite di rapporti

La finestra di dialogo Data Governance (Governance dei dati) negli strumenti dell’amministratore offre una panoramica delle suite di rapporti configurate per la governance dei dati, indica se sono state mappate in un’organizzazione Experience Cloud e se per essa sono stati impostati i criteri di conservazione dei dati.

1. Accedi ad Adobe Experience Cloud.
1. Navigate to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Data Governance.]**

   Visualizzerai tutte le suite di rapporti che fanno parte della società di accesso:

   ![](assets/privacy_setup_an.png)

<table id="table_448292730FF0475E9DCB731882F9A29B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Impostazione </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Suite di rapporti </p> </td> 
   <td colname="col2"> <p>La prima riga elenca il nome descrittivo della suite di rapporti. La seconda riga contiene il nome interno della suite di rapporti. Se ti è consentito impostare le etichette per una suite di rapporti, la prima riga sarà un collegamento cliccabile che ti porta alla pagina di etichettatura. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Organization Mapping (Mappatura dell’organizzazione) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EF8F613B0C5E42D19DB60BD0C89C114B"> 
     <li id="li_B35EE88555F547EFBF55ADE9D0C9EC3B"><b>Mappata</b>: questa suite di rapporti è già stata mappata nella stessa organizzazione Experience Cloud della società di accesso di Analytics in cui hai effettuato l’accesso. È possibile etichettare solo le suite di rapporti che hanno questa impostazione. </li> 
     <li id="li_4E800BF80CFF477BAA091EF272D9071C"><b>Map Report Suite (Mappa suite di rapporti)</b>: facendo clic su questo collegamento potrai <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html" format="html" scope="external">mappare una suite di rapporti</a> in un’organizzazione Experience Cloud. <p>In questo modo, verrai reindirizzato alla pagina di amministrazione Mappatura di suite di rapporti per un’organizzazione Experience Cloud dove dovrai individuare la suite di rapporti e assegnarla all’organizzazione appropriata. Dopo aver eseguito questa operazione, torna a questa schermata Data Governance (Governance dei dati). </p> </li> 
     <li id="li_FF825A65D089487BBF5FCB0D74D41CD7"><b>Mapped to Another Organization (Mappata in un’altra organizzazione)</b>: un’altra organizzazione ha già mappato questa suite di rapporti al proprio interno. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Data Retention Policy (Criteri di conservazione dei dati) </p> </td> 
   <td colname="col2"> <p>L'implementazione della privacy dei dati di Analytics richiede l'implementazione di un criterio di conservazione dei dati. </p> <p>Questa impostazione consente di vedere se </p> 
    <ul id="ul_AC1F0827293B47E39BFEC4B1766A0CAC"> 
     <li id="li_3AAD93EA92B94C6180E5AEBC5E4D10FB">sono stati impostati i criteri di conservazione dei dati per questa suite di rapporti e </li> 
     <li id="li_2E8D71905C734F8BB3245FEEDA953B3E">per quanto tempo i dati vengono conservati da Adobe prima di essere cancellati. Il periodo di conservazione dei dati predefinito è di 25 mesi. </li> 
    </ul> <p>Nota:  Adobe Analytics non è in grado di fornire assistenza nell'elaborazione delle richieste all'API per la privacy dei dati, ovvero l'elaborazione delle richieste di accesso o eliminazione ricevute dagli utenti finali, se il periodo di conservazione dei dati non è stato impostato. Contatta il tuo Customer Success Manager per impostare il periodo di conservazione dei dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Groups (Gruppi) </p> </td> 
   <td colname="col2"> <p>La funzionalità di raggruppamento al momento non è implementata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Barra laterale a sinistra </p> </td> 
   <td colname="col2"> <p>Fai clic sull’icona dell’imbuto per aprire o chiudere la barra laterale. </p> <p>La sezione Organization Mapping (Mappatura dell’organizzazione) mostra il numero di suite di rapporti che rientrano in ognuna delle categorie descritte. </p> <p>La sezione Data Retention Policy (Criteri di conservazione dei dati) mostra tutti i criteri univoci di conservazione dei dati e il numero di suite di rapporti assegnate ai criteri di conservazione dei dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Export to CSV (Esporta in CSV) </p> </td> 
   <td colname="col2"> <p>Se indichi il segno di spunta accanto a una o più suite di rapporti, viene visualizzata l’opzione <span class="uicontrol">Esporta in CSV</span>. Questa opzione ti consente di scaricare un file CSV contenente tutte le definizioni delle etichette attuali per tutte le variabili per tutte le suite di rapporti selezionate. </p> <p>Consigliamo al team legale di esaminare le scelte di etichettatura; questa opzione facilita la revisione. Invece di dover eseguire la revisione quando sei autenticato nell’interfaccia utente della governance dei dati, puoi condividere il file .CSV. </p> <p><img placement="break"  src="assets/export_csv.png" width="300px" id="image_5FE821B2D07B402D8E0F6FE53D6FC52E" /> </p> </td> 
  </tr> 
 </tbody> 
</table>

