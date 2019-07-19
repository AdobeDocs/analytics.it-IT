---
description: Creare, gestire e visualizzare l'utilizzo di origini dati in una suite di rapporti.
seo-description: Creare, gestire e visualizzare l'utilizzo di origini dati in una suite di rapporti.
seo-title: Origini dati Manager
solution: Analytics
subtopic: Origini dati
title: Origini dati Manager
topic: Sviluppatore e implementazione
uuid: ccfa 4 a 1 c -7 c 56-421 b -8 ee 6-a 42 b 334659 b 1
translation-type: tm+mt
source-git-commit: 887f48d2ea5f21b7db95a1a8f716f7da9cf43662

---


# Origini dati Manager

Creare, gestire e visualizzare l'utilizzo di origini dati in una suite di rapporti.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Data Sources]**.

## Scheda Crea {#section_74603FDA3D8842E49F1A51624A06DE20}

The [!UICONTROL Create] tab lets you configure a new data source for the currently selected report suite. When you activate a data source, the [!UICONTROL Data Sources Wizard] guides you through the process of creating a Data Sources template, and creates an FTP location for uploading data.

La selezione eseguita nella scheda Crea determina i campi iniziali nel modello creato. See [Generating an Import File Template](../../import/c-data-sources/datasrc-template/t-datasrc-creating-data-sources-file.md#task_A2F150D9DC1A4D338E878534FA506267).

## Scheda Gestisci {#section_DD559A6701CA45F1A85E56F840F48DBE}

<table id="table_F74696EC855441328CFE0BF49C20D9B0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Opzione </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Restart Processing (Riavvia elaborazione) </p> </td> 
   <td colname="col2"> <p>Riavvia l'elaborazione dell'origine dati precedentemente interrotta a causa di errori o avvisi. L'elaborazione continua fino al rilevamento dell'errore successivo. Origini dati interrompe l'elaborazione di un file Origini dati solo quando selezioni <span class="uicontrol">Stop Processing on Errors</span> (Interrompi elaborazione in caso di errori). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Complete Processing (Completa elaborazione) </p> </td> 
   <td colname="col2"> <p>Indica a Origini dati di chiudere qualsiasi visita aperta nel file e di terminare l'elaborazione del file Origini dati come se fosse stata completata. Questa opzione è utile in presenza di visite che si estendono in più file Origini dati. This applies only to <a href="../../import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#concept_975B1BB9981D49139B4EE09C78CDE6ED" type="concept" format="dita" scope="local"> Full Processing</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Disattiva </p> </td> 
   <td colname="col2"> <p> La disattivazione di un'origine dati la eliminerà. Se l'elaborazione di file sul server è iniziata, continuerà fino al termine. I file per i quali non è ancora iniziata l'elaborazione non saranno elaborati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stop processing on errors/warnings (Interrompi elaborazione in caso di errori/avvisi) </p> </td> 
   <td colname="col2"> <p> Indica al motore di elaborazione di Origini dati di interrompere l'elaborazione quando viene rilevato un errore. L'elaborazione dell'origine dati non riprende fino a quando non selezioni Restart Processing (Riavvia elaborazione). The Stop processing on warnings option applies only to <a href="../../import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#concept_975B1BB9981D49139B4EE09C78CDE6ED" type="concept" format="dita" scope="local"> Full Processing</a>. </p> <p>Quando Origini dati rileva un errore del file, ti avvisa dell'errore. Il sistema sposta il file Origini dati con l'errore in una cartella denominata <span class="filepath">files_with_errors</span> sul server FTP. Dopo aver risolto il problema, rinvia il file Origini dati per l'elaborazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configure (Configura) </p> </td> 
   <td colname="col2"> <p>Ti consente di configurare il modello origine dati o altre impostazioni specifiche di questa origine dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FTP Info (Info FTP) </p> </td> 
   <td colname="col2"> <p>Visualizza le informazioni FTP per questa origine dati. Usa queste informazioni per accedere al modello origine dati e inviare i dati Origini dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome file </p> </td> 
   <td colname="col2"> <p>Il nome del file caricato </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stato </p> </td> 
   <td colname="col2"> <p> Lo stato corrente del file. I valori di stato possibili includono quanto segue: </p> 
    <ul id="ul_56A0BF8C1BE249F6BB39B0D11DA3997F"> 
     <li id="li_BAB359E08EDE4E0298C0362258789603">In coda (fase 1 di 3): il file esiste, ma l'elaborazione non è iniziata. Se il file non viene visualizzato entra 30 minuti, controllare che sia presente il file associato <span class="filepath">.fin</span>. </li> 
     <li id="li_A09A14F42CB74F01B694799740B3DA17">Preparazione (fase 2 di 3): il file è in fase di controllo per verificare la presenza di errori o avvisi. </li> 
     <li id="li_793FDCDB64CF434D82CAF5B6E9BDE557">Elaborazione (fase 3 di 3): il file è in fase di elaborazione. </li> 
     <li id="li_1D8C4B241FF0453EAF7DDFD8354C5573">Non riuscito: il file non è stato elaborato a causa di errori </li> 
     <li id="li_A52507602FB4492B83A70AF6449A539A">Riuscito: il file è stato elaborato completamente. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Scheda Registro file {#section_B7AC7EE8CAD740A59DD53CF1919373F0}

Il registro file include una funzione di ricerca che ti consente di cercare le informazioni per nome origine dati, tipo di origine dati, nome file, data di ricezione o stato.
