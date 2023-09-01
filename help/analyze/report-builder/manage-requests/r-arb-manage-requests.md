---
description: Scopri le descrizioni dei campi per Gestisci richieste nel Report Builder.
title: Come gestire le richieste nel Report Builder
uuid: 01b21d0e-c870-4df8-95b9-f4aef1f4d16b
feature: Report Builder
role: User, Admin
exl-id: fd8c0145-4c7e-4f07-aa63-656a8a20724c
source-git-commit: 66b7de0b008364e47253d319785c204ca479ab26
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 2%

---

# Gestire le richieste: definizioni

Visualizzare i dettagli dello stato di una richiesta e utilizzare le descrizioni dei campi per gestire le richieste nel Report Builder.

## Panoramica {#section_75C288C945FA4781A4EDF806711A5660}

Il [!UICONTROL Request Manager] fornisce una visualizzazione dettagliata dello stato di tutte le richieste create per tutti i fogli o solo per un foglio della cartella di lavoro attiva. Puoi anche aggiungere, modificare, aggiornare ed eliminare una richiesta. Queste funzioni sono tipicamente associate al [!UICONTROL Request Wizard] e [!UICONTROL Request Manager] quando fai clic con il pulsante destro del mouse su una cella disponibile nel foglio di calcolo Excel che contiene richieste precedenti.

Il [!UICONTROL Request Manager] viene visualizzato quando si fa clic su **[!UICONTROL Manage]**  ![](assets/edit_request.gif) nella barra degli strumenti del Report Builder.

>[!NOTE]
>
>Adobe Report Builder applica le dipendenze delle richieste solo all&#39;interno dello stesso foglio di lavoro, non tra fogli di lavoro diversi. La limitazione alle dipendenze all&#39;interno di un singolo foglio di lavoro garantisce la tempestività dell&#39;esecuzione.

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
   <td colname="col2"> <p>Visualizza le richieste da tutti i fogli della cartella di lavoro attiva. Per visualizzare le richieste da fogli specifici, disattiva questa opzione. Se si disattiva questa opzione, è necessario fare clic su una scheda Foglio nella parte inferiore del report di Excel per visualizzare le richieste associate a tale foglio nel <span class="wintitle"> Request Manager</span>. L'etichetta accanto alla casella di controllo indica quale foglio della cartella di lavoro ha attualmente lo stato attivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Foglio </p> </td> 
   <td colname="col2"> <p>Visualizza il nome dei fogli della cartella di lavoro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Suite di rapporti </p> </td> 
   <td colname="col2"> <p>Visualizza il nome della suite di rapporti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Intervallo date </p> </td> 
   <td colname="col2"> <p>Visualizza l'intervallo di date specificato del rapporto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Granularità </p> </td> 
   <td colname="col2"> <p>Specifica la granularità della richiesta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Ultima esecuzione </p> </td> 
   <td colname="col2"> <p>Specifica la data dell'ultima elaborazione della richiesta per Report Builder. In questa tabella viene inoltre visualizzato un messaggio di diagnostica nel <span class="wintitle"> Ultima esecuzione</span> colonna, se applicabile. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Add </p> </td> 
   <td colname="col2"> <p>Visualizza la finestra di dialogo Creazione guidata richieste. Consulta <a href="/help/analyze/report-builder/data-requests/t-create-a-data-request.md"   > Creare una richiesta di dati</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modifica </p> </td> 
   <td colname="col2"> <p> (O Modifica più volte) Modifica una richiesta selezionata. Il sistema visualizza <span class="wintitle"> Creazione guidata richieste</span> . Consulta <a href="/help/analyze/report-builder/manage-requests/t-edit-multiple-requests.md"   > Modifica più richieste</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Eliminazione </p> </td> 
   <td colname="col2"> <p>Elimina le richieste. Puoi eliminare più richieste selezionate. Per eliminare una richiesta dall’elenco, selezionala e premi Elimina dalla tastiera. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Seleziona tutto </p> </td> 
   <td colname="col2"> <p>Seleziona tutte le richieste. Il <span class="wintitle"> Request Manager</span> visualizza il numero di richieste selezionate nella parte inferiore dell’elenco delle richieste. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Da cella </p> </td> 
   <td colname="col2"> <p>Ottiene i dati per una richiesta dal foglio di lavoro. Se una richiesta è associata alla cella attualmente selezionata nel foglio di lavoro attivo, viene selezionata la richiesta associata nell'elenco. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Aggiornamento </p> </td> 
   <td colname="col2"> <p>Aggiorna una singola richiesta o una selezione di richieste. (vedere <a href="/help/analyze/report-builder/manage-requests/t-refresh-a-request.md"   > Aggiornare una richiesta</a>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Aggiorna elenco </p> </td> 
   <td colname="col2"> <p>Aggiorna tutte le richieste visualizzate. Quando si aggiornano tutte le richieste, il tempo necessario per aggiornare le informazioni dal server al report è direttamente proporzionale alla complessità delle richieste nel report. Per i rapporti molto grandi, l’aggiornamento di tutte le richieste potrebbe richiedere alcuni minuti. Per questo motivo, potrebbe essere utile aggiornare singolarmente le richieste più urgenti e selezionare <span class="wintitle"> Aggiorna tutto</span> in un altro momento meno cruciale. </p> <p> <p>Nota: si consiglia di controllare i risultati spesso in <span class="wintitle"> Request Manager</span> se si aggiorna un foglio di lavoro contenente più richieste. Se la richiesta non riesce, il messaggio di errore nella colonna diagnostica consente di individuare l’origine dell’errore. Sebbene nella maggior parte dei casi venga visualizzato un messaggio di errore quando una richiesta non riesce, talvolta non viene generato alcun messaggio di errore. È possibile che un aggiornamento non aggiorni i dati in una cella contenente un riferimento o che un aggiornamento rimuova i dati dalla cella. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>
