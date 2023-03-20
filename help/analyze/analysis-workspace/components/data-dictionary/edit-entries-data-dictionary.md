---
description: Il dizionario dati in Analysis Workspace consente agli utenti di catalogare e tenere traccia dei vari componenti in Analysis Workspace, compreso l’uso previsto, che sono approvati, che sono duplicati, e così via.
title: Modificare le voci nel dizionario dati
feature: Components
role: Admin
source-git-commit: 8edd7b1b90e2ac3137bea734e5a0f1cb8004e743
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 0%

---

# Modificare le voci del componente nel dizionario dati

{{release-limited-testing}}

Gli amministratori di Analytics possono modificare le voci dei componenti nel dizionario dati per una determinata suite di rapporti. Tutte le modifiche apportate sono visibili a tutti gli utenti della suite di rapporti.

Per modificare un componente nel dizionario dati:

1. Vai al progetto Analysis Workspace che contiene il componente da modificare.

1. Seleziona la **Dizionario dati** nella barra a sinistra di Analysis Workspace. (I modi alternativi per accedere al dizionario dati sono descritti in &quot;Accedere al dizionario dati&quot; in [Panoramica sul dizionario dati](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md).)

   Viene visualizzata la finestra del dizionario dati.

   ![Visualizzazione amministratore del dizionario dati](assets/data-dictionary-admin.png)

1. Assicurati che nel menu a discesa sia selezionata la suite di rapporti corretta. Per impostazione predefinita, viene visualizzata la suite di rapporti già in uso.

1. (Facoltativo) Nel campo di ricerca, inizia a digitare il nome del componente da modificare.

   Accanto ai nomi dei componenti vengono visualizzate delle icone per indicare il tipo di componente:

   | Icona | Significato |
   |---------|----------|
   | ![Icona Dimension](assets/dimension-icon.png) | Indica un **dimension**. I Dimension sono forniti dall&#39;Adobe. Impossibile modificare le dimensioni esistenti e creare nuove dimensioni. |
   | ![Icona della metrica](assets/default-metric-icon.png) | Indica un **metrica standard** (non calcolato). Le metriche standard vengono fornite per Adobe e non possono essere modificate. |
   | ![Icona Adobe](assets/default-calc-metric-icon.png) | Indica un **modello di metrica calcolata**. Si tratta di metriche calcolate fornite da Adobe e che non possono essere modificate. |
   | ![Icona Calcolatore](assets/calculated-metric-icon-created.png) | Indica un **metrica calcolata** creato da un amministratore Analytics nella tua organizzazione. <!-- Delete all the comments... Components with this icon can be modified by an Analytics administrator. New calculated metrics can be created by an Analytics administrator, as described in [Metrics](/help/analyze/analysis-workspace/components/apply-create-metrics.md). --> |
   | ![Icona Segmento](assets/segment-icon.png) | Indica un **segmento**. Possono essere segmenti forniti da un Adobe o creati da un amministratore Analytics nella tua organizzazione.<!-- Segments that were created byComponents with this icon can be modified by an Analytics administrator, as described in [Edit component entries in the Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md). New calculated metrics can also be created by an Analytics administrator, as described in [Metrics](/help/analyze/analysis-workspace/components/apply-create-metrics.md). --> |
   | ![Icona Intervallo date](assets/date-range-icon.png) | Indica un **intervallo date**. Possono essere intervalli di date forniti da un Adobe o creati da un amministratore Analytics nella tua organizzazione. <!-- Components with this icon can be modified by an Analytics administrator. New date ranges can also be created by an Analytics administrator, as described in [Create custom date ranges](/help/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.md). --> |

{{dd-filter-criteria}}

1. Dall’elenco dei componenti, seleziona il componente da modificare.

1. Seleziona la **Modifica** icona ![Icona Modifica dizionario dati](assets/data-dictionary-edit-icon.png) accanto al nome del componente.

1. Modifica una delle seguenti informazioni sul componente:

   {{dd-component-information}}

1. Fai clic sul pulsante **Salva** icona ![Icona Salva dizionario dati](assets/data-dictionary-save-icon.png) per salvare le modifiche.
