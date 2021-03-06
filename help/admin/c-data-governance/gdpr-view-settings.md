---
description: La finestra di dialogo Data Governance (Governance dei dati) negli strumenti dell’amministratore offre una panoramica delle suite di rapporti configurate per la governance dei dati, indica se sono state mappate in un’organizzazione Experience Cloud e se per essa sono stati impostati i criteri di conservazione dei dati.
title: Visualizzare/gestire le impostazioni di governance dei dati della suite di rapporti
feature: Data Governance
exl-id: 87b0be42-1098-4e72-8eb8-0c1bb56791f8
source-git-commit: f6199620033af9c8e304bd0f537d4e0b052ed64d
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 100%

---

# Visualizzare/gestire le impostazioni di governance dei dati della suite di rapporti

La finestra di dialogo Data Governance (Governance dei dati) negli strumenti dell’amministratore offre una panoramica delle suite di rapporti configurate per la governance dei dati, indica se sono state mappate in un’organizzazione Experience Cloud e se per essa sono stati impostati i criteri di conservazione dei dati.

1. Accedi ad Adobe Experience Cloud.
1. Passa a  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Data Governance]**.

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
     <li id="li_FF825A65D089487BBF5FCB0D74D41CD7"><b>Mapped to Another Organization (Mappata in un’altra organizzazione)</b>: un’altra organizzazione ha già mappato questa suite di rapporti al proprio interno. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Data Retention Policy (Criteri di conservazione dei dati) </p> </td> 
   <td colname="col2"> <p>Per implementare la Privacy dei dati in Analytics è necessario aver impostato i criteri di conservazione dei dati. </p> <p>Questa impostazione consente di vedere se: </p> 
    <ul> 
     <li>sono stati impostati i criteri di conservazione dei dati per questa suite di rapporti; e </li> 
     <li>per quanto tempo i dati vengono conservati da Adobe prima di essere eliminati. Il periodo di conservazione dei dati predefinito è di 25 mesi. </li> 
    </ul> <p>Nota: in Adobe Analytics non è possibile ricevere assistenza per elaborare le richieste per l’API Privacy dei dati, ovvero per elaborare le richieste di accesso o di cancellazione ricevute dagli utenti finali, se non è stato impostato il periodo di conservazione dei dati. Contatta il tuo Customer Success Manager per impostare il periodo di conservazione dei dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Groups (Gruppi) </p> </td> 
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
