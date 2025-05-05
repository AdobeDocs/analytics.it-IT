---
title: Tabella a forma libera
description: Le tabelle a forma libera sono alla base dell’analisi dei dati in Workspace
feature: Freeform Tables
role: User, Admin
exl-id: 7a0432f9-2cab-47be-bbd6-ede96cb840a3
source-git-commit: bb3e8b030af78f0d7758b4cff41d66f20695e11e
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 27%

---

# Tabella a forma libera {#freeform-table-overview}


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_button"
>title="Tabella a forma libera"
>abstract="Crea una visualizzazione vuota delle tabelle a forma libera che puoi realizzare utilizzando dimensioni, segmenti, metriche e intervalli di date. Puoi utilizzare la tabella a forma libera come base per altre visualizzazioni."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Questo articolo documenta la visualizzazione a forma libera in_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**._<br/>_Consulta la [tabella a forma libera](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-workspace/visualizations/freeform-table/freeform-table) per_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**versione del Customer Journey Analytics** di questo articolo._

>[!ENDSHADEBOX]


In Analysis Workspace, una visualizzazione ![Tabella](/help/assets/icons/Table.svg) **[!UICONTROL Freeform table]** è la base per l&#39;analisi dei dati interattivi. Puoi trascinare una combinazione di [componenti](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) nelle righe e nelle colonne per creare una tabella personalizzata per l’analisi. Man mano che ciascun componente viene rilasciato, la tabella viene aggiornata immediatamente per consentirti di analizzare e approfondire rapidamente.

![Tabella a forma libera che mostra i componenti nelle righe e nelle colonne, incluse le visite e gli ordini in linea per più pagine Web.](assets/opening-section.png)

Per creare e configurare [!UICONTROL Freeform table]:

* Aggiungi una visualizzazione ![Tabella](/help/assets/icons/Table.svg) **[!UICONTROL Freeform table]**. Vedi [Aggiungere una visualizzazione a un pannello](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

## Tabelle automatizzate

Il modo più rapido per creare una tabella consiste nel trascinare i componenti direttamente in un progetto o pannello vuoto o in una tabella a forma libera. Una tabella a forma libera viene creata automaticamente in un formato consigliato. [Guarda il tutorial](https://experienceleague.adobe.com/it/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/auto-build-freeform-tables-in-analysis-workspace).

![Un nuovo pannello con il componente Visite è stato rilasciato nell&#39;area di lavoro.](assets/automated-table.png)

## Generatore di tabelle a forma libera

Se prima preferisci aggiungere diversi componenti alla tabella, quindi eseguire il rendering dei dati, puoi selezionare **[!UICONTROL Enable table builder]**. Con il generatore abilitato, puoi trascinare dimensioni, raggruppamenti, metriche e filtri per creare tabelle che rispondano a domande più complesse. I dati vengono aggiornati dopo la selezione di **[!UICONTROL Build]**.

![Un generatore di tabelle a forma libera mostra ](assets/table-builder.png)

## Interazioni

Puoi interagire con una tabella a forma libera e personalizzarla in diversi modi:

### Filtra e ordina

* Puoi [filtrare e ordinare](filter-and-sort.md) i dati in una tabella.

### Righe

* Puoi [creare rapidamente una nuova visualizzazione](../freeform-analysis-visualizations.md#visualize) da una o più righe utilizzando ![GraphBarVerticalAdd](/help/assets/icons/GraphBarVerticalAdd.svg).
* È possibile inserire più righe in una singola schermata regolando la [densità di visualizzazione](/help/analyze/analysis-workspace/build-workspace-project/view-density.md) del progetto.
* Prima dell’impaginazione ogni riga delle dimensioni può visualizzare fino a 400 righe. Selezionare il numero accanto a **[!UICONTROL Rows]** nell&#39;intestazione della prima colonna per visualizzare più righe in una pagina. Passa a una pagina diversa utilizzando ![ChevronRight](/help/assets/icons/ChevronRight.svg) nell&#39;intestazione della prima colonna.
* Puoi suddividere le righe per componenti aggiuntivi. Per suddividere più righe alla volta, seleziona più righe e trascina il componente successivo sopra le righe selezionate. Scopri di più sulle [suddivisioni](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md).
* Le righe possono essere [filtrate](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md) per visualizzare un set ridotto di elementi. Sono disponibili altre impostazioni in [Impostazioni riga](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md).

### Colonne

* I componenti possono essere impilati all’interno di colonne per creare metriche filtrate, analisi incrociate e altro ancora.
* La visualizzazione di ogni colonna può essere regolata nelle [impostazioni della colonna](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md).
* Sono disponibili diverse azioni tramite il [menu di scelta rapida](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu). Il menu fornisce azioni diverse a seconda che sia selezionata l’intestazione della tabella, le righe o le colonne.


## Impostazioni

Selezionare ![Impostazione](/help/assets/icons/Setting.svg) per visualizzare **[!UICONTROL Table settings]**. Sono disponibili le seguenti [impostazioni](../freeform-analysis-visualizations.md#settings) di visualizzazione specifiche:

### Origine dati

| Opzione | Descrizione |
|---|---|
| **[!UICONTROL Linked visualizations]**. | Elenca tutte le visualizzazioni collegate. |
| **[!UICONTROL Show data source]** | Se questa opzione è deselezionata, la tabella a forma libera che funge da origine dati per la visualizzazione è nascosta in Workspace. |

### Impostazioni

| Opzione | Descrizione |
|---|---|
| **[!UICONTROL Align dates from each columns to all start on the same row]** | Per allineare o non allineare le date di ogni colonna affinché inizino tutte sulla stessa riga. |


## Menu di scelta rapida

Le seguenti opzioni del [menu di scelta rapida](../freeform-analysis-visualizations.md#context-menu) sono disponibili nell&#39;intestazione della visualizzazione:

| Opzione | Descrizione |
| --- | --- |
| **[!UICONTROL Insert copied visualization]**&#x200B;n | Incolla (inserisci) una visualizzazione copiata in un’altra posizione all’interno del progetto o in un progetto completamente diverso. |
| **[!UICONTROL Copy data to clipboard]** | Copia i dati dalla visualizzazione negli Appunti. |
| **[!UICONTROL Copy selection to clipboard]** | Copia la selezione dalla visualizzazione negli Appunti. |
| **[!UICONTROL Download items as CSV (*nome dimensione *)]** | Scarica immediatamente gli elementi dimensionali (fino a un massimo di 50.000) della visualizzazione sul dispositivo locale. Massimo 50.000 elementi dimensionali per la dimensione selezionata. |
| **[!UICONTROL Copy visualization]** | Copia la visualizzazione in modo da poterla inserire in un’altra posizione all’interno del progetto o in un progetto completamente diverso. |
| **[!UICONTROL Download data CSV]** | Scarica immediatamente i dati visualizzati della visualizzazione sul dispositivo locale. |
| **[!UICONTROL Duplicate visualization]** | Crea un duplicato esatto della visualizzazione. |
| **[!UICONTROL Edit description]** | Aggiungi (o modifica) un testo descrittivo per la visualizzazione. Vedi [Testo](../text.md). |
| **[!UICONTROL Get visualization link]** | Copia e condividi un collegamento direttamente alla visualizzazione. La finestra di dialogo Condividi collegamento consente di visualizzare il collegamento. Seleziona Copia per copiare il collegamento negli Appunti. |
| **[!UICONTROL Start over]** | Elimina la configurazione per la visualizzazione corrente in modo da poterla riconfigurare da zero. |



## Video

>[!BEGINSHADEBOX]

Per un video dimostrativo, consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Panoramica del generatore di tabelle a forma libera](https://video.tv.adobe.com/v/35891?quality=12&learn=on&captions=ita){target="_blank"}.

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

Per un video demo, vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Filtri per tabelle a forma libera](https://video.tv.adobe.com/v/329390?quality=12&learn=on&captions=ita){target="_blank"}.

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

Per un video demo, vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Totali tabelle a forma libera](https://video.tv.adobe.com/v/39247?quality=12&learn=on&captions=ita){target="_blank"}.

>[!ENDSHADEBOX]


>[!MORELIKETHIS]
>
>[Aggiungi una visualizzazione a un pannello](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Impostazioni visualizzazione](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu di scelta rapida visualizzazione](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>



