---
title: Gestire i set di classificazione
description: Gestisci i set di classificazione in Adobe Analytics.
exl-id: b1a6721b-8e5d-4ee6-af6b-cda31c9f8b00
feature: Classifications
source-git-commit: eb12185be8d6e2e6dc15df9da17ce34b5f6b9c80
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 3%

---

# Gestire i set di classificazione

Puoi creare, rinominare, modificare, consolidare, eliminare e assegnare tag ai set di classificazione nell’interfaccia di gestione dei set di classificazione. Puoi anche filtrare e cercare set di classificazione specifici.

Per gestire i set di classificazione:

1. Seleziona **[!UICONTROL Components]** dalla barra dei menu superiore di Adobe Analytics, quindi seleziona **[!UICONTROL Classification sets]**.
1. In **[!UICONTROL Classification Sets]**, selezionare la scheda **[!UICONTROL Classification Sets]**.

## Gestione set di classificazione

Il gestore **[!UICONTROL Classification Sets]** dispone dei seguenti elementi dell&#39;interfaccia:

![Gestione set di classificazione](assets/classification-sets-manage.png)


### Elenco dei set di classificazione

Nell&#39;elenco **[!UICONTROL Classification Sets]** ➊ vengono visualizzati tutti i set di classificazione. L’elenco dispone delle seguenti colonne:

| Colonna | Descrizione |
|---|---|
| **[!UICONTROL Classification Set]** | Nome del set di classificazione. Selezionare il nome per [modificare il set di classificazione](create-set.md#edit-a-classification-set). |
| **[!UICONTROL Subscriptions]** | Il numero di abbonamenti a cui si applica il set di classificazione. |
| **[!UICONTROL Classifications]** | Il numero di dimensioni di classificazione contenute nel set di classificazione. |
| **[!UICONTROL Automated]** | Il set di classificazione è configurato per importare automaticamente o meno dati da una posizione cloud? Questa automazione può essere configurata come parte dello schema [set di classificazione](manage/schema.md). |
| **[!UICONTROL Last modified]** | La marca temporale dell’ultima modifica del set di classificazione. |

Per ridimensionare una colonna nell’elenco dei set di classificazione, puoi:

* Passa il puntatore del mouse sul separatore di colonne e trascina il separatore di colonne fino alla larghezza desiderata.
* Selezionare ![ChevronDown](/help/assets/icons/ChevronDown.svg) e selezionare **[!UICONTROL Resize column]**. Una linea verticale con il pulsante di ridimensionamento consente di ridimensionare la colonna nel modo desiderato con.

Per ordinare una colonna nell&#39;elenco dei set di classificazione

* Selezionare ![ChevronDown](/help/assets/icons/ChevronDown.svg) e selezionare **[!UICONTROL Sort Ascending]** o **[!UICONTROL Sort Descending]**. Una freccia (↑↓) indica quale colonna e come è ordinata.

### Pulsanti di ricerca e

Nell&#39;area ➋ sopra l&#39;elenco dei set di classificazione è possibile:

* Cerca in ![Search](/help/assets/icons/Search.svg) i set di classificazione. I risultati vengono visualizzati nell’elenco dei set di classificazione. Selezionare ![CrossSize200](/help/assets/icons/CrossSize200.svg) per cancellare la ricerca.
* Rimuovi eventuali filtri applicati all’elenco dei set di classificazione. Selezionare ![CrossSize100](/help/assets/icons/CrossSize100.svg) per rimuovere un filtro.
* Seleziona ![AltroCerchio](/help/assets/icons/MoreCircle.svg) per caricare altri 1000 set di classificazione. Inizialmente, nell’elenco delle serie di classificazioni vengono visualizzate fino a 1000 serie di classificazioni.
* Selezionare ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL New]** per [creare un nuovo set di classificazione](create-set.md#create-a-classification-set).
* Definisci le colonne dell’elenco dei set di classificazione. Seleziona ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) e nella finestra di dialogo **[!UICONTROL Customize table]** seleziona le colonne da visualizzare sotto **[!UICONTROL Select columns to show]**. Selezionare **[!UICONTROL Apply]** per applicare le impostazioni della colonna.


### Barra delle azioni

Quando selezioni uno o più set di classificazione nell&#39;elenco dei set di classificazione, viene visualizzata una barra blu delle azioni ➌. Nella barra delle azioni sono disponibili le azioni seguenti:

| Icona | Azione | Descrizione |
|---|---|---|
| ![Modifica](/help/assets/icons/Edit.svg) | **[!UICONTROL Edit]** | [Modifica il set di classificazione](create-set.md#edit-a-classification-set) nel generatore di set di classificazione. |
| ![Rinomina](/help/assets/icons/Rename.svg) | **[!UICONTROL Rename]** | Rinomina un set di classificazione.<br/>Nella finestra di dialogo **[!UICONTROL Rename: _set di classificazione_]** immettere un nuovo nome e selezionare **[!UICONTROL Rename]**. |
| ![Unione](/help/assets/icons/Merge.svg) | **[!UICONTROL Consolidate]** | [Consolidare i set di classificazione](/help/components/classifications/sets/consolidations/manage.md). |
| ![Elimina](/help/assets/icons/Delete.svg) | **[!UICONTROL Delete]** | Elimina un set di classificazione.<br/>Il **[!UICONTROL Delete _set di classificazione _?Viene visualizzata la finestra di dialogo]**. L’eliminazione di un set di classificazione non può essere annullata. Tutti i progetti o i consolidamenti programmati che utilizzano questa serie di classificazione continuano a utilizzare la definizione di questa serie di classificazione fino a quando non vengono salvati nuovamente i progetti programmati o non vengono convalidati nuovamente i consolidamenti programmati. Selezionare **[!UICONTROL Delete]**per eliminare il set di classificazione. |
| ![Etichetta](/help/assets/icons/Label.svg) | **[!UICONTROL Tag]** | Assegna tag al set di classificazione.<br/>Nella finestra di dialogo **[!UICONTROL Tag: _set di classificazione_]**, seleziona uno o più tag dal menu a discesa **[!UICONTROL Tags]** per aggiungere i tag. Oppure immetti uno o più nuovi tag. Utilizza ![CrossSize100](/help/assets/icons/CrossSize100.svg) per rimuovere un tag. <br/>Selezionare **[!UICONTROL Save]** per salvare i tag. |


### Pannello dei filtri

Seleziona ![Filtro](/help/assets/icons/Filter.svg) per visualizzare il pannello dei filtri ➍ che ti consente di filtrare l&#39;elenco dei set di classificazione. Puoi filtrare in base a:

* **[!UICONTROL Tags]**. Seleziona uno o più tag per filtrare l’elenco dei set di classificazione sui tag.
* **[!UICONTROL Report Suite]**. Seleziona una o più suite di rapporti per filtrare l’elenco delle serie di classificazioni in base alle suite di rapporti.

Seleziona ![Filtro](/help/assets/icons/Filter.svg) **[!UICONTROL Hide filters]** per nascondere il pannello dei filtri.

I filtri visualizzati nel pannello filtri riflettono le opzioni per i set di classificazione precaricati.
