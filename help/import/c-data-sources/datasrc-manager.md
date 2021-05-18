---
description: Creare, gestire e visualizzare l'utilizzo di origini dati in una suite di rapporti.
subtopic: Data sources
title: Origini dati Manager
topic-fix: Developer and implementation
uuid: ccfa4a1c-7c56-421b-8ee6-a42b334659b1
exl-id: a63137b8-deeb-4865-9be9-322416b00186
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 82%

---

# Origini dati Manager

Creare, gestire e visualizzare l&#39;utilizzo di origini dati in una suite di rapporti.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Data sources]**.

## Scheda Crea {#section_74603FDA3D8842E49F1A51624A06DE20}

La scheda [!UICONTROL Create] ti consente di configurare una nuova origine dati per la suite di rapporti attualmente selezionata. Quando attivi un’origine dati, il percorso [!UICONTROL Data Sources Wizard] ti guida attraverso il processo di creazione di un modello Origini dati e crea una posizione FTP per il caricamento dei dati.

La selezione eseguita nella scheda Crea determina i campi iniziali nel modello creato. Vedere [Generazione di un modello di file di importazione](/help/import/c-data-sources/datasrc-template/t-datasrc-creating-data-sources-file.md).

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
   <td colname="col2"> <p>Indica a Origini dati di chiudere qualsiasi visita aperta nel file e di terminare l'elaborazione del file Origini dati come se fosse stata completata. Questa opzione è utile in presenza di visite che si estendono in più file Origini dati. Questo vale solo per <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md"   > Full Processing</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Disattiva </p> </td> 
   <td colname="col2"> <p> La disattivazione di un'origine dati la eliminerà. Se l'elaborazione di file sul server è iniziata, continuerà fino al termine. I file per i quali non è ancora iniziata l'elaborazione non saranno elaborati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stop processing on errors/warnings (Interrompi elaborazione in caso di errori/avvisi) </p> </td> 
   <td colname="col2"> <p> Indica al motore di elaborazione di Origini dati di interrompere l'elaborazione quando viene rilevato un errore. L'elaborazione dell'origine dati non riprende fino a quando non selezioni Restart Processing (Riavvia elaborazione). L'opzione Interrompi elaborazione in caso di avvisi si applica solo a <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md"   > Elaborazione completa</a>. </p> <p>Quando Origini dati rileva un errore del file, ti avvisa dell'errore. Il sistema sposta il file Origini dati con l'errore in una cartella denominata <span class="filepath">files_with_errors</span> sul server FTP. Dopo aver risolto il problema, rinvia il file Origini dati per l'elaborazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configura </p> </td> 
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
     <li id="li_BAB359E08EDE4E0298C0362258789603">In coda (fase 1 di 3): il file esiste, ma l'elaborazione non è iniziata. Se il file non viene visualizzato entro 30 minuti, verifica che il file associato <span class="filepath"> .fin</span> sia presente </li> 
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
