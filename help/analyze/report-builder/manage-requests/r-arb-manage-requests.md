---
description: Descrizioni dei campi per Gestione richieste in Generatore di report.
seo-description: Descrizioni dei campi per Gestione richieste in Generatore di report.
seo-title: Gestione delle richieste - definizioni
solution: Analytics
title: Gestione delle richieste - definizioni
topic: Generatore di report
uuid: 01 b 21 d 0 e-c 870-4 df 8-95 b 9-f 4 aef 1 f 4 d 16 b
translation-type: tm+mt
source-git-commit: 6a70b32b576cc7b5b6a6f0037d98e35b3f8c1426

---


# Gestione delle richieste - definizioni

Descrizioni dei campi per Gestione richieste in Generatore di report.

## Panoramica {#section_75C288C945FA4781A4EDF806711A5660}

The [!UICONTROL Request Manager] provides a detailed view of the status of all requests you have built for all sheets or just one sheet of the active workbook. You can also add, edit, refresh, and delete a request (functions typically associated with the [!UICONTROL Request Wizard] and [!UICONTROL Request Manager]) by right-clicking on an available cell in the Excel spreadsheet that contains previous requests.

The [!UICONTROL Request Manager] displays when you click **[!UICONTROL Manage]** ( ![](assets/edit_request.gif) in the Report Builder toolbar.

>[!NOTE]
>
>Adobe Report Builder applica le dipendenze richieste solo all'interno dello stesso foglio di lavoro, non tra fogli di lavoro. La limitazione alle dipendenze all'interno di un singolo foglio di lavoro garantisce la tempestività dell'esecuzione.

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
   <td colname="col2"> <p>Visualizza le richieste da tutti i fogli della cartella di lavoro attiva. Disattivare questa opzione per visualizzare le richieste da un foglio specifico. If you turn off this option, you must click on a Sheet tab at the bottom of your Excel report to display the requests associated with that sheet in the <span class="wintitle"> Request Manager</span>. L'etichetta accanto alla casella di controllo indica quale foglio della cartella di lavoro è attivo. </p> </td> 
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
   <td colname="col1"> <p>Intervallo date </p> </td> 
   <td colname="col2"> <p>Visualizza l'intervallo date specificato del report. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Granularity (Granularità) </p> </td> 
   <td colname="col2"> <p>Specifica la granularità della richiesta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Ultima esecuzione </p> </td> 
   <td colname="col2"> <p>Specifica la data dell'ultima elaborazione della richiesta da Generatore di report. A diagnostic message is also displayed in this table in the <span class="wintitle"> Last Run</span> column, if applicable. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Aggiungi </p> </td> 
   <td colname="col2"> <p>Visualizza la finestra di dialogo Richiesta guidata. See <a href="../../../analyze/report-builder/data-requests/t-create-a-data-request.md#task_65B453C8F015429A8EA73A1B64025B6C" type="task" format="dita" scope="local"> Create a Data Request</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modificare       </p> </td> 
   <td colname="col2"> <p> (o Modifica multipla) Modifica una richiesta selezionata. The system displays the <span class="wintitle"> Request Wizard</span> dialog. See <a href="../../../analyze/report-builder/manage-requests/t-edit-multiple-requests.md#task_70A13DBE43CD4BBEBE1B62459ADB3AD1" type="task" format="dita" scope="local"> Edit Multiple Requests</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Elimina </p> </td> 
   <td colname="col2"> <p>Elimina le richieste. Potete eliminare più richieste selezionate. Potete anche eliminare una richiesta nell'elenco selezionando la richiesta e premendo Elimina sulla tastiera. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Seleziona tutto </p> </td> 
   <td colname="col2"> <p>Selezionate tutte le richieste. <span class="wintitle"> Gestore richieste</span> visualizza il numero di richieste selezionate nella parte inferiore dell'elenco delle richieste. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dalla cella </p> </td> 
   <td colname="col2"> <p>Ottiene i dati per una richiesta dal foglio di lavoro. Se una richiesta è associata alla cella attualmente selezionata nel foglio di lavoro attivo, la richiesta associata nell'elenco è selezionata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Aggiorna </p> </td> 
   <td colname="col2"> <p>Aggiorna una singola richiesta o una selezione di richieste. (See <a href="../../../analyze/report-builder/manage-requests/t-refresh-a-request.md#task_96556DB051A2479A955999D3837EE609" type="task" format="dita" scope="local"> Refresh a Request</a>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Aggiorna elenco </p> </td> 
   <td colname="col2"> <p>Aggiorna tutte le richieste visualizzate. Quando aggiornate tutte le richieste, il tempo di aggiornamento delle informazioni dal server al report è direttamente proporzionale alla complessità delle richieste nel report. Per i report molto grandi, l'aggiornamento di tutte le richieste potrebbe richiedere alcuni minuti. For this reason, you may wish to update the most urgent requests individually, and select <span class="wintitle"> Refresh All</span> at another, less time-crucial moment. </p> <p> <p>Note: It is recommended that you check results often in the <span class="wintitle"> Request Manager</span> if you refresh a worksheet containing multiple requests. Se si verifica un errore di richiesta, il messaggio di errore nella colonna diagnostica aiuta a individuare l'origine dell'errore. Nella maggior parte dei casi viene visualizzato un messaggio di errore quando una richiesta non riesce, notare che talvolta non viene generato alcun messaggio di errore. Potrebbe essere notato che l'aggiornamento non aggiorna i dati di una cella contenente un riferimento, o che un aggiornamento rimuove i dati dalla cella. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

