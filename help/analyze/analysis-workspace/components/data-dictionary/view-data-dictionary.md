---
description: Il dizionario dati in Analysis Workspace consente agli utenti di catalogare e tenere traccia dei vari componenti in Analysis Workspace, compreso l’uso previsto, che sono approvati, che sono duplicati, e così via.
title: Visualizza dizionario dati
feature: Components
role: User, Admin
source-git-commit: 5d83d2621ee5eee7dbbc2af3793a9e1d3de0f97b
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 0%

---

# Visualizzare le informazioni sui componenti nel dizionario dati

{{release-limited-testing}}

Il dizionario dati consente di visualizzare informazioni su un componente, inclusa la descrizione del componente, componenti simili, altri componenti con cui un componente viene spesso utilizzato e altro ancora.

Per visualizzare informazioni su un componente nel dizionario dati:

1. Vai al progetto Analysis Workspace che contiene il componente che desideri visualizzare.

1. Seleziona la [!UICONTROL **Dizionario dati**] nella barra a sinistra di Analysis Workspace. (I modi alternativi per accedere al dizionario dati sono descritti in &quot;Accedere al dizionario dati&quot; in [Panoramica sul dizionario dati](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md).)

   Viene visualizzata la finestra del dizionario dati.

   ![data-dizionario.png](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. Assicurati che la suite di rapporti contenente il componente che desideri visualizzare sia selezionata nel menu a discesa. Per impostazione predefinita, viene visualizzata la suite di rapporti già in uso.

1. (Facoltativo) Nel campo di ricerca, inizia a digitare il nome del componente che desideri visualizzare.

   Accanto ai nomi dei componenti vengono visualizzate delle icone per indicare il tipo di componente:

   | Icona | Significato |
   |---------|----------|
   | ![Icona Dimension](assets/dimension-icon.png) | Indica un **dimension**. I Dimension sono forniti dall&#39;Adobe. Impossibile modificare le dimensioni esistenti e creare nuove dimensioni. |
   | ![Icona della metrica](assets/default-metric-icon.png) | Indica un **metrica standard** (non calcolato). Le metriche standard vengono fornite per Adobe e non possono essere modificate. |
   | ![Icona Adobe](assets/default-calc-metric-icon.png) | Indica un **modello di metrica calcolata** o **modello di segmento**. Questi componenti sono forniti da Adobe e non possono essere modificati. |
   | ![Icona Calcolatore](assets/calculated-metric-icon-created.png) | Indica un **metrica calcolata** creato da un amministratore Analytics nella tua organizzazione. |
   | ![Icona Segmento](assets/segment-icon.png) | Indica un **segmento**. Possono essere segmenti forniti da un Adobe o creati da un amministratore Analytics nella tua organizzazione. |
   | ![Icona Intervallo date](assets/date-range-icon.png) | Indica un **intervallo date**. Possono essere intervalli di date forniti da un Adobe o creati da un amministratore Analytics nella tua organizzazione. |

{{dd-filter-criteria}}

1. Dall’elenco dei componenti, seleziona il componente da visualizzare.

   Vengono visualizzate le seguenti informazioni sul componente:

   {{dd-component-information}}

1. (Facoltativo) Trascina un componente dal dizionario dati in Analysis Workspace.