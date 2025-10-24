---
title: Gestione processi di classificazione
description: Scopri come visualizzare i processi di classificazione correnti e completati generati dai set di classificazione.
exl-id: 0470e131-79c6-4906-85f0-530d360ac227
feature: Classifications
source-git-commit: 77599d015ba227be25b7ebff82ecd609fa45a756
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 3%

---

# Visualizza e intervieni sui processi di classificazione

Gestione processi di classificazione mostra i processi di classificazione correnti e completati generati per i set di classificazione. Puoi anche utilizzare il gestore per scaricare i dati o i modelli di classificazione per un particolare processo.

Per visualizzare i processi di classificazione e agire di conseguenza:

1. Seleziona **[!UICONTROL Components]** nell’interfaccia principale, quindi seleziona **[!UICONTROL Classification sets]**.
1. In **[!UICONTROL Classification Sets]**, selezionare la scheda **[!UICONTROL Jobs]**.

## Gestione processi di classificazione

Il gestore **[!UICONTROL Classification Sets - Jobs]** dispone dei seguenti elementi dell&#39;interfaccia:

![Set di classificazioni - Gestione processi](manage/assets/classifications-sets-jobs.png)



### Elenco processi di classificazione

L&#39;elenco **[!UICONTROL Classification Jobs]** ➊ visualizza i processi di classificazione. L’elenco dispone delle seguenti colonne:

| Colonna | Descrizione |
|---|---|
| **[!UICONTROL Job Id]** | Identificatore del processo di classificazione. |
| **[!UICONTROL Classification Set]** | Set di classificazione associato al processo di classificazione. |
| **[!UICONTROL Size]** | Dimensione del file esportato o importato come parte del processo di classificazione. |
| **[!UICONTROL Status]** | Stato del processo di classificazione. I valori possibili sono: **[!UICONTROL Created]**, **[!UICONTROL Queued]**, **[!UICONTROL Validated]**, **[!UICONTROL Failed validation]**, **[!UICONTROL Processing]**, **[!UICONTROL Done processing]**, **[!UICONTROL Failed processing]**, **[!UICONTROL Completed]** o **[!UICONTROL Progress]**. |
| **[!UICONTROL File Name]** | Identifica il nome o la funzionalità utilizzati per importare o esportare il file come parte del processo di classificazione. I valori possibili sono: <ul><li>*nessun valore*</li><li>Nome del file elaborato come parte del processo di classificazione.</li><li>**[!UICONTROL SAINT Export]**: il processo è un&#39;esportazione dall&#39;[interfaccia classificazioni legacy](/help/components/classifications/importer/c-working-with-saint.md).</li><li>**[!UICONTROL export for _set di classificazione _in_timestamp_]**: il processo è un download dall&#39;interfaccia [schema](manage/schema.md#download).</li></ul> |
| **[!UICONTROL Job Type]** | Tipo di processo di classificazione. I valori possibili sono: **[!UICONTROL Import]** o **[!UICONTROL Export]**. |
| **[!UICONTROL Source]** | Origine del processo di classificazione. I valori possibili sono: **[!UICONTROL Web API]**, **[!UICONTROL Direct API Upload]**, **[!UICONTROL Adobe]**, **[!UICONTROL SAINT]** o **[!UICONTROL Unknown]**. |
| **[!UICONTROL Modified Lines]** | Il numero di righe modificate dal processo di classificazione. |
| **[!UICONTROL Total Lines]** | Numero di righe totali elaborate dal processo di classificazione. |
| **[!UICONTROL Completion Time]** | L’ora di completamento del processo di classificazione. |
| **[!UICONTROL File Download]** | Utilizza ![Scarica](/help/assets/icons/Download.svg) per scaricare il file (modello o dati) associato al processo di classificazione. |

Per ridimensionare una colonna nell’elenco dei processi di classificazione, puoi:

* Passa il puntatore del mouse sul separatore di colonne e trascina il separatore di colonne fino alla larghezza desiderata.
* Selezionare ![ChevronDown](/help/assets/icons/ChevronDown.svg) e selezionare **[!UICONTROL Resize column]**. Una linea verticale con il pulsante di ridimensionamento consente di ridimensionare la colonna nel modo desiderato con.

Per ordinare una colonna nell’elenco dei processi di classificazione

* Selezionare ![ChevronDown](/help/assets/icons/ChevronDown.svg) e selezionare **[!UICONTROL Sort Ascending]** o **[!UICONTROL Sort Descending]**. Una freccia (↑↓) indica quale colonna e come è ordinata.


### Pulsanti di ricerca e

Nell&#39;area ➋ sopra l&#39;elenco dei processi di classificazione è possibile:

* Cerca in ![Ricerca](/help/assets/icons/Search.svg) i processi di classificazione. I risultati vengono visualizzati nell’elenco dei processi di classificazione. Selezionare ![CrossSize200](/help/assets/icons/CrossSize200.svg) per cancellare la ricerca.
* Rimuovi eventuali filtri applicati all’elenco dei processi di classificazione. Selezionare ![CrossSize100](/help/assets/icons/CrossSize100.svg) per rimuovere un filtro.
* Seleziona ![AltroCerchio](/help/assets/icons/MoreCircle.svg) per caricare altri 1000 processi di classificazione. Inizialmente, nell’elenco delle serie di classificazioni vengono visualizzati fino a 1000 processi di classificazione.
* Definisci le colonne dell’elenco dei processi dei set di classificazione. Seleziona ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) e nella finestra di dialogo **[!UICONTROL Customize table]** seleziona le colonne da visualizzare sotto **[!UICONTROL Select columns to show]**. Selezionare **[!UICONTROL Apply]** per applicare le impostazioni della colonna.



### Pannello dei filtri

Seleziona ![Filtro](/help/assets/icons/Filter.svg) per visualizzare il pannello dei filtri ➌ che ti consente di filtrare l&#39;elenco dei processi di classificazione. Puoi filtrare in base a:

* **[!UICONTROL Classification Set]**. Seleziona uno o più set di classificazione per filtrare l’elenco dei processi di classificazione.
* **[!UICONTROL Completion Time]**. Seleziona uno dei valori possibili per filtrare l’elenco dei processi di classificazione al momento del completamento.
* **[!UICONTROL Status]**. Seleziona uno dei valori possibili per filtrare l’elenco dei processi di classificazione in base allo stato.
* **[!UICONTROL Job Type]**. Seleziona uno dei valori possibili per filtrare l’elenco dei processi di classificazione in base al tipo di processo.
* **[!UICONTROL Source]**. Seleziona uno dei valori possibili per filtrare l’elenco dei processi di classificazione sull’origine.


Seleziona ![Filtro](/help/assets/icons/Filter.svg) **[!UICONTROL Hide filters]** per nascondere il pannello dei filtri.

I filtri visualizzati nel pannello filtri riflettono le opzioni per i processi di classificazione precaricati.


<!--

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Jobs]**

You cannot create jobs from this interface. Create jobs by uploading data to a classification set (either manually or through a configured external location), requesting a download file, or requesting a template file.

## Filter classification sets

The left side of the Classification set job manager provides filter settings to locate the desired job. Clicking the filter icon toggles the filter settings visibility. You can filter Classification sets by **[!UICONTROL Classification set]**, **[!UICONTROL Completion time]**, **[!UICONTROL Status]**, **[!UICONTROL Job Type]**, or **[!UICONTROL Source]**.

![Classification set job filters](../assets/classification-set-job-filters.png)

Additional filter options are available above the Classification set job manager columns:

* **[!UICONTROL Search by title]**: Search for jobs by filename.
* **[!UICONTROL Load more]**: The Classification set job manager initially displays up to 1000 jobs. If more jobs exist, click this button to load 1000 more jobs.
* **Show/Hide columns**: Toggle visibility for any column besides [!UICONTROL Filename] and [!UICONTROL Completion time].

## Classification set job manager columns

The following columns are available in the Classification set job manager:

* **[!UICONTROL Filename]**: The name of the upload or download file.
* **[!UICONTROL Classification set]**: The name of the Classification set that the file applies to. You can click the Classification set name to reach the Classification set's [Settings](manage/settings.md).
* **[!UICONTROL Size]**: The size of the file.
* **[!UICONTROL Status]**: The status of the job processing the file.
  * **[!UICONTROL Created]**: The job was submitted.
  * **[!UICONTROL Queued]**: The file is ready to be processed, and is waiting for a classification server to process the file.
  * **[!UICONTROL Validated]**: The file is valid and is waiting to be processed.
  * **[!UICONTROL Failed validation]**: The file is formatted incorrectly or otherwise invalid. The file does not go through processing.
  * **[!UICONTROL Processing]**: The file is actively being processed by Adobe.
  * **[!UICONTROL Failed processing]**: The file failed processing.
  * **[!UICONTROL Complete]**: Processing is complete. Classification data is visible in reporting.
  * **[!UICONTROL Failed]**: Generic failure not related to validation or processing.
* **[!UICONTROL Job type]**: The type of job.
* **[!UICONTROL Source]**: The job source.
* **[!UICONTROL File download]**: Only applies to download jobs, such as downloading classification data or downloading templates. When a download is ready, this column provides a download link.
* **[!UICONTROL Modified lines]**: The number of modified lines.
* **[!UICONTROL Completed lines]**: The number of completed lines.
* **[!UICONTROL Completion time]**: The date and time that the job completed (or failed).
-->