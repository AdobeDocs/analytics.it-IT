---
description: Descrizioni dei campi per Gestione richieste in Report Builder.
title: 'Gestire le richieste: definizioni'
uuid: 01b21d0e-c870-4df8-95b9-f4aef1f4d16b
feature: Report Builder
role: Business Practices, amministratore
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 4%

---


# Gestire le richieste: definizioni

Descrizioni dei campi per Gestione richieste in Report Builder.

## Panoramica {#section_75C288C945FA4781A4EDF806711A5660}

La sezione [!UICONTROL Request Manager] fornisce una visualizzazione dettagliata dello stato di tutte le richieste create per tutti i fogli o solo un foglio della cartella di lavoro attiva. Puoi anche aggiungere, modificare, aggiornare ed eliminare una richiesta (funzioni generalmente associate alle [!UICONTROL Request Wizard] e [!UICONTROL Request Manager]) facendo clic con il pulsante destro del mouse su una cella disponibile nel foglio di calcolo Excel che contiene richieste precedenti.

Il [!UICONTROL Request Manager] viene visualizzato quando si fa clic su **[!UICONTROL Manage]** ( ![](assets/edit_request.gif) nella barra degli strumenti del Report Builder.

>[!NOTE]
>
>Adobe Report Builder applica le dipendenze richieste solo all&#39;interno dello stesso foglio di lavoro, non tra i fogli di lavoro. La limitazione alle dipendenze all&#39;interno di un singolo foglio di lavoro garantisce la tempestività dell&#39;esecuzione.

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
   <td colname="col1"> <p>Tutto Fogli </p> </td> 
   <td colname="col2"> <p>Visualizza le richieste da tutti i fogli della cartella di lavoro attiva. Per visualizzare le richieste da fogli specifici, disattiva questa opzione. Se si disattiva questa opzione, è necessario fare clic su una scheda Foglio nella parte inferiore del rapporto Excel per visualizzare le richieste associate a tale foglio nel <span class="wintitle"> Request Manager</span>. L'etichetta accanto alla casella di controllo indica quale foglio della cartella di lavoro è attualmente attivo. </p> </td> 
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
   <td colname="col2"> <p>Visualizza l'intervallo di date specificato nel rapporto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Granularity (Granularità) </p> </td> 
   <td colname="col2"> <p>Specifica la granularità della richiesta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Ultima esecuzione </p> </td> 
   <td colname="col2"> <p>Specifica la data dell’ultima elaborazione della richiesta da parte del Report Builder. In questa tabella viene inoltre visualizzato un messaggio di diagnostica nella colonna <span class="wintitle"> Ultima esecuzione</span> , se applicabile. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Add </p> </td> 
   <td colname="col2"> <p>Visualizza la finestra di dialogo Creazione guidata richieste. Consulta <a href="/help/analyze/report-builder/data-requests/t-create-a-data-request.md"   > Creare una richiesta di dati</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modificare </p> </td> 
   <td colname="col2"> <p> (O Modifica multipla) Modifica una richiesta selezionata. Il sistema visualizza la finestra di dialogo <span class="wintitle"> Richiesta guidata</span>. Consulta <a href="/help/analyze/report-builder/manage-requests/t-edit-multiple-requests.md"   > Modificare più richieste</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Elimina </p> </td> 
   <td colname="col2"> <p>Elimina le richieste. Puoi eliminare più richieste selezionate. È inoltre possibile eliminare una richiesta dall’elenco selezionando la richiesta e premendo Elimina sulla tastiera. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Seleziona tutto </p> </td> 
   <td colname="col2"> <p>Seleziona tutte le richieste. Il <span class="wintitle"> Request Manager</span> visualizza il numero di richieste selezionate nella parte inferiore dell'elenco di richieste. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Da cella </p> </td> 
   <td colname="col2"> <p>Ottiene i dati di una richiesta dal foglio di lavoro. Se una richiesta è associata alla cella attualmente selezionata nel foglio di lavoro attivo, viene selezionata la richiesta associata nell'elenco. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Aggiorna </p> </td> 
   <td colname="col2"> <p>Aggiorna una singola richiesta o una selezione di richieste. (Consulta <a href="/help/analyze/report-builder/manage-requests/t-refresh-a-request.md"   > Aggiornare una richiesta</a>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Aggiorna elenco </p> </td> 
   <td colname="col2"> <p>Aggiorna tutte le richieste visualizzate. Quando aggiorni tutte le richieste, il tempo necessario per aggiornare le informazioni dal server al report è direttamente proporzionale alla complessità delle richieste nel report. Per i rapporti di grandi dimensioni, l’aggiornamento di tutte le richieste potrebbe richiedere diversi minuti. Per questo motivo, è possibile aggiornare le richieste più urgenti singolarmente e selezionare <span class="wintitle"> Aggiorna tutto</span> in un altro momento meno cruciale in termini di tempo. </p> <p> <p>Nota: È consigliabile controllare spesso i risultati in <span class="wintitle"> Request Manager</span> se si aggiorna un foglio di lavoro contenente più richieste. Se si verifica un errore di richiesta, il messaggio di errore nella colonna diagnostica ti aiuta a individuare l’origine dell’errore. Nella maggior parte dei casi viene visualizzato un messaggio di errore in caso di errore di una richiesta, ma talvolta non viene generato alcun messaggio di errore. È possibile notare che un aggiornamento non aggiorna i dati di una cella contenente un riferimento o che un aggiornamento rimuove i dati dalla cella. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

