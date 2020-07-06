---
description: Descrizioni dei campi per Gestisci richieste nel Generatore di report.
title: 'Gestire le richieste: definizioni'
topic: Report builder
uuid: 01b21d0e-c870-4df8-95b9-f4aef1f4d16b
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 3%

---


# Gestire le richieste: definizioni

Descrizioni dei campi per Gestisci richieste nel Generatore di report.

## Panoramica {#section_75C288C945FA4781A4EDF806711A5660}

Viene [!UICONTROL Request Manager] fornita una visualizzazione dettagliata dello stato di tutte le richieste create per tutti i fogli o solo un foglio della cartella di lavoro attiva. È inoltre possibile aggiungere, modificare, aggiornare ed eliminare una richiesta (funzioni generalmente associate a [!UICONTROL Request Wizard] e [!UICONTROL Request Manager]) facendo clic con il pulsante destro del mouse su una cella disponibile nel foglio di calcolo Excel contenente richieste precedenti.

Il [!UICONTROL Request Manager] display viene visualizzato quando fate clic **[!UICONTROL Manage]** ( ![](assets/edit_request.gif) nella barra degli strumenti Generatore di report).

>[!NOTE]
>
>Adobe Report Builder applica le dipendenze delle richieste solo all&#39;interno dello stesso foglio di lavoro, non tra fogli di lavoro. Limitarsi alle dipendenze all&#39;interno di un singolo foglio di lavoro garantisce la tempestività dell&#39;esecuzione.

## Definizioni {#section_FD29D8614DE74F32A0027FA130F40304}

<table id="table_0880204181074BDBBA37E3DF2972A672"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Tutti i fogli </p> </td> 
   <td colname="col2"> <p>Visualizza le richieste da tutti i fogli della cartella di lavoro attiva. Per visualizzare le richieste da fogli specifici, disattivate questa opzione. Se disattivate questa opzione, dovete fare clic su una scheda Foglio nella parte inferiore del rapporto Excel per visualizzare le richieste associate a tale foglio nel Gestore <span class="wintitle"> delle</span>richieste. L'etichetta accanto alla casella di controllo indica quale foglio della cartella di lavoro è attualmente attivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Foglio </p> </td> 
   <td colname="col2"> <p>Visualizza il nome dei fogli nella cartella di lavoro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Suite di rapporti </p> </td> 
   <td colname="col2"> <p>Visualizza il nome della suite di rapporti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Intervallo di date </p> </td> 
   <td colname="col2"> <p>Visualizza l'intervallo di date specificato nel rapporto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Granularity (Granularità) </p> </td> 
   <td colname="col2"> <p>Specifica la granularità della richiesta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Ultima esecuzione </p> </td> 
   <td colname="col2"> <p>Specifica la data dell'ultima elaborazione della richiesta da parte del Generatore di report. In questa tabella, se applicabile, viene visualizzato anche un messaggio diagnostico nella colonna <span class="wintitle"> Ultima esecuzione</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Add </p> </td> 
   <td colname="col2"> <p>Visualizza la finestra di dialogo Richiesta guidata. See <a href="/help/analyze/report-builder/data-requests/t-create-a-data-request.md"   > Create a Data Request</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modificare </p> </td> 
   <td colname="col2"> <p> (O Modifica multipla) Modifica una richiesta selezionata. Viene visualizzata la finestra di dialogo <span class="wintitle"> Richiesta guidata</span> . See <a href="/help/analyze/report-builder/manage-requests/t-edit-multiple-requests.md"   > Edit Multiple Requests</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Elimina </p> </td> 
   <td colname="col2"> <p>Elimina le richieste. Potete eliminare più richieste selezionate. È inoltre possibile eliminare una richiesta dall'elenco selezionando la richiesta e premendo Elimina sulla tastiera. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Seleziona tutto </p> </td> 
   <td colname="col2"> <p>Selezionate tutte le richieste. Il <span class="wintitle"> Gestore</span> richieste visualizza il numero di richieste selezionate nella parte inferiore dell'elenco di richieste. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Da cella </p> </td> 
   <td colname="col2"> <p>Ottiene i dati per una richiesta dal foglio di lavoro. Se una richiesta è associata alla cella attualmente selezionata nel foglio di lavoro attivo, viene selezionata la richiesta associata nell'elenco. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Aggiorna </p> </td> 
   <td colname="col2"> <p>Aggiorna una singola richiesta o una selezione di richieste. (See <a href="/help/analyze/report-builder/manage-requests/t-refresh-a-request.md"   > Refresh a Request</a>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Aggiorna elenco </p> </td> 
   <td colname="col2"> <p>Aggiorna tutte le richieste visualizzate. Quando aggiornate tutte le richieste, il tempo necessario per aggiornare le informazioni dal server al rapporto è direttamente proporzionale alla complessità delle richieste nel rapporto. Per i report di grandi dimensioni, l'aggiornamento di tutte le richieste potrebbe richiedere diversi minuti. Per questo motivo, potete aggiornare singolarmente le richieste più urgenti e selezionare <span class="wintitle"> Aggiorna tutto</span> in un altro momento, meno importante dal punto di vista del tempo. </p> <p> <p>Nota: È consigliabile controllare spesso i risultati in <span class="wintitle"> Request Manager</span> se si aggiorna un foglio di lavoro contenente più richieste. Se si verifica un errore di richiesta, il messaggio di errore nella colonna diagnostica consente di individuare l'origine dell'errore. Anche se nella maggior parte dei casi viene visualizzato un messaggio di errore quando una richiesta non riesce, talvolta non viene generato alcun messaggio di errore. È possibile notare che un aggiornamento non aggiorna i dati in una cella contenente un riferimento, o che un aggiornamento rimuove i dati dalla cella. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

