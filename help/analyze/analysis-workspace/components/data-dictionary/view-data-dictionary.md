---
description: Il dizionario dei dati in Analysis Workspace consente agli utenti di catalogare e tenere traccia dei vari componenti in Analysis Workspace, incluso l’uso previsto, quali sono approvati, quali sono duplicati e così via.
title: Visualizzare il dizionario dei dati
feature: Components
role: User, Admin
exl-id: 68f68ea4-f0a6-4937-bf8f-aecfa28572bb
source-git-commit: a6805f0944570bee265d5db9a159ae24e0694837
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 100%

---

# Visualizzare le informazioni sui componenti nel dizionario dati

Il dizionario dei dati consente di visualizzare informazioni su un componente, tra cui la sua descrizione, componenti simili, altri componenti con cui viene utilizzato di frequente e altro ancora.

Per visualizzare informazioni su un componente nel dizionario dei dati:

1. Vai al progetto Analysis Workspace che contiene il componente che desideri visualizzare.

1. Seleziona l’icona [!UICONTROL **Dizionario dei dati**] nella barra a sinistra di Analysis Workspace. I modi alternativi per accedere al dizionario dati sono descritti in “Accedere al dizionario dei dati” in [Panoramica del dizionario dei dati](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md).

   Viene visualizzata la finestra Dizionario dei dati.

   ![data-dictionary.png](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. Assicurati che la suite di rapporti contenente il componente che desideri visualizzare sia selezionata nel menu a discesa. Per impostazione predefinita, viene visualizzata la suite di rapporti in cui ti trovi già.

1. (Facoltativo) Nel campo di ricerca, inizia a digitare il nome del componente che desideri visualizzare.

   Il tipo di componente può essere identificato sia dal colore che dall’icona. **Dimensioni** ![icona Dimensione](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) sono arancioni, **Segmenti** ![icona Segmento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) sono blu, **Intervalli di date** ![icona Intervallo di date](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) sono viola, e **Metriche** ![icona Metrica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) sono verdi. L’icona Adobe indica un modello di metrica calcolata o un modello di segmento, e l’icona della calcolatrice ![icona Calcolatrice](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indica una metrica calcolata creata da un amministratore Analytics della tua organizzazione.

{{dd-filter-criteria}}

1. (Facoltativo) Seleziona l’icona **Ordina** ![icona Ordina componenti](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg) e quindi una delle seguenti opzioni per filtrare l’elenco dei componenti:

   {{components-sort-options}}

1. Dall’elenco dei componenti, seleziona il componente che desideri visualizzare.

   Vengono visualizzate le seguenti informazioni sul componente:

   {{dd-component-information}}

1. (Facoltativo) Trascina un componente dal dizionario dei dati ad Analysis Workspace.
