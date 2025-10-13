---
description: Scopri come utilizzare le impostazioni di riga e come variano a seconda del componente trascinato in una tabella a forma libera in Analysis Workspace.
title: Impostazioni riga
uuid: f30c31d5-1fd4-4b93-94c3-ca441099fe2e
feature: Freeform Tables
role: User, Admin
exl-id: 9057e930-b4c6-439e-b82a-8ab9828de91d
source-git-commit: f258a1150a4bee11f5922d058930dc38b1ddfa14
workflow-type: tm+mt
source-wordcount: '906'
ht-degree: 18%

---


# Impostazioni riga


>[!BEGINSHADEBOX]

Per un video demo, vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Impostazioni riga e colonna in una tabella a forma libera](https://video.tv.adobe.com/v/328590/?quality=12&learn=on&captions=ita){target="_blank"}.

>[!ENDSHADEBOX]

Le Impostazioni riga variano a seconda del componente che hai trascinato all’interno della tabella. Per accedere alle impostazioni delle righe della tabella, selezionare ![Impostazione](/help/assets/icons/Setting.svg) **[!UICONTROL Settings]** accanto a una dimensione, un filtro, una metrica, un periodo di tempo o un raggruppamento all&#39;interno di ciascuno di questi oggetti.

![Tabella a forma libera che evidenzia l&#39;icona Impostazioni per le metriche](assets/row-settings.png)

| Impostazione | Descrizione |
| --- | --- |
| **[!UICONTROL Breakdown by position]** | Per impostazione predefinita, questa impostazione è disabilitata e i raggruppamenti sono fissati su elementi di riga statici. Ad esempio, immagina di suddividere i primi 3 elementi dimensionali di pagina (Home page, Risultati ricerca, Pagamento) per canale di marketing. Poi abbandoni il progetto per due settimane. Quando lo riapri, le prime 3 pagine sono cambiate e ora Home page, Risultati ricerca e Pagamento sono le prime 4-6 pagine. Per impostazione predefinita, i raggruppamenti per canale di marketing vengono ancora visualizzati in Home page, Risultati ricerca e Pagamento, anche se ora si trovano nelle righe 4-6. <br> Al contrario, **Raggruppamento per posizione** raggrupperà sempre i primi 3 elementi, indipendentemente da quali siano. Facendo riferimento all’esempio, quando riapri il progetto, i raggruppamenti per canale di marketing sono legati alle prime 3 pagine della tabella. E non alla homepage, ai risultati della ricerca e al checkout, che ora si trovano nelle righe 4-6. |
| **[!UICONTROL Percentages]** | **Calcola percentuali per colonna** (impostazione predefinita): le percentuali visibili in una cella vengono calcolate in base al totale della colonna. <br>**Calcola percentuali per riga**: le percentuali nelle celle vengono calcolate in una riga, anziché in una colonna, con il totale complessivo come denominatore. Questo calcolo è utile per le percentuali di tendenza. |
| **[!UICONTROL Column totals]** | Queste impostazioni sono disponibili solo per le [righe statiche](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md). <br> **Mostra come somma delle righe correnti** mostra una somma lato client delle righe nella tabella, il che significa che il totale *non* deduplica metriche quali visite o persone. <br> **Mostra totale** mostra una somma lato server, che indica il totale delle metriche deduplicate. |

## Modificare conteggio righe

Per modificare il numero di righe visualizzate:

1. Fare clic sul numero accanto a **[!UICONTROL Rows]** nella parte superiore della prima colonna della tabella.

   ![Tabella a forma libera che mostra l&#39;elenco a discesa di per il numero di righe visualizzate. 400 righe selezionate.](assets/change-row-count.gif)

1. Dall’elenco a discesa, seleziona il numero di righe che si desidera visualizzare nella tabella.


## Menu di scelta rapida

Quando si seleziona l’intestazione della dimensione, sono disponibili le seguenti opzioni del menu di scelta rapida.

| Opzione | Descrizione |
| --- | --- |
| **[!UICONTROL Copy selection to clipboard]** | Copia la selezione dalla visualizzazione negli appunti. |
| **[!UICONTROL Download items as CSV (*nome dimensione *)]** | Scarica immediatamente gli elementi dimensionali (fino a un massimo di 50.000) della visualizzazione sul dispositivo locale. Un massimo di 50.000 elementi dimensionali per la dimensione selezionata. |
| **[!UICONTROL Download selection as CSV]** | Scarica immediatamente gli elementi dimensionali della visualizzazione sul dispositivo locale. |
| **[!UICONTROL Create hyperlink for all dimension items]** | Crea collegamenti ipertestuali per tutti gli elementi dimensionali. Vedi [Collegamenti ipertestuali per le dimensioni in una tabella a forma libera](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Edit hyperlink for all dimension items]** | Modifica i collegamenti ipertestuali per tutti gli elementi dimensionali. Vedi [Collegamenti ipertestuali per le dimensioni in una tabella a forma libera](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Remove hyperlink for all dimension items]** | Rimuove i collegamenti ipertestuali per tutti gli elementi dimensionali. Vedi [Collegamenti ipertestuali per le dimensioni in una tabella a forma libera](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Delete]** | Elimina la dimensione dalla tabella. |
| **[!UICONTROL Visualize]** | Visualizza la dimensione utilizzando una qualsiasi delle visualizzazioni disponibili. |
| **[!UICONTROL Display only selected rows]** | Visualizza solo gli elementi selezionati nella visualizzazione. |
| **[!UICONTROL Create annotation from selection]** | Apri **[!UICONTROL Annotation details]** per aggiungere un&#39;annotazione. |


Quando si selezionano uno o più elementi dimensionali (prima colonna) o una o più celle singole nella tabella a forma libera, sono disponibili le seguenti opzioni aggiuntive del menu di scelta rapida.

| Opzione | Descrizione |
| --- | --- |
| **[!UICONTROL Create hyperlink]** | Crea un collegamento ipertestuale per l&#39;elemento. Vedi [Collegamenti ipertestuali per le dimensioni in una tabella a forma libera](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Edit hyperlink]** | Modificare un collegamento ipertestuale per l&#39;elemento. Vedi [Collegamenti ipertestuali per le dimensioni in una tabella a forma libera](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Remove hyperlink]** | Rimuove un collegamento ipertestuale per l&#39;elemento. Vedi [Collegamenti ipertestuali per le dimensioni in una tabella a forma libera](../freeform-table-hyperlinks.md) |
| **[!UICONTROL Breakdown]** | Suddividi l’elemento dimensione. Selezionare dall&#39;elenco di **[!UICONTROL Dimensions]**, **[!UICONTROL Metrics]**, **[!UICONTROL Filters]** o **[!UICONTROL Date ranges]**. Ricerca alternativa per un componente, utilizzando *Ricerca*. |
| **[!UICONTROL Delete selected]** | Elimina le righe (elementi) selezionate. |
| **[!UICONTROL Trend selection]** | Crea una visualizzazione con grafico a linee di tendenza per la selezione. |
| **[!UICONTROL Display only selected rows]** | Visualizza solo le righe selezionate nella visualizzazione. |
| **[!UICONTROL Display all rows]** | Visualizza tutte le righe della visualizzazione. |
| **[!UICONTROL Create filter from selection]** | Apri **[!UICONTROL Filter builder]** per creare un filtro dalla selezione. |
| **[!UICONTROL Create audience from selection]** | Apri la finestra di dialogo **[!UICONTROL Create audience]** per creare un pubblico dalla selezione. |

Quando si seleziona un’intestazione di colonna di una metrica, sono disponibili le seguenti opzioni aggiuntive del menu di scelta rapida.

| Opzione | Descrizione |
|---|---|
| **[!UICONTROL Create metric from selection]** | Crea una nuova metrica dalla metrica selezionata. La metrica può essere Media, Media, Colonna max, Colonna min, Somma colonna. Puoi anche selezionare Apri nel generatore di metriche calcolate per creare una metrica calcolata. |
| **[!UICONTROL Add time period column]** | Aggiungi una colonna Periodo di tempo. Sono disponibili diverse opzioni, in cui l&#39;intervallo di calendario del pannello determina l&#39;*intervallo di date*: <li>**[!UICONTROL Prior *intervallo di date *a questo intervallo di date]**</li><li>**[!UICONTROL These *intervallo di date *a questo intervallo di date]**.</li><li>**[!UICONTROL Custom date range to this date range]**. Apre **[!UICONTROL Date range builder]** per specificare l&#39;intervallo di date.</li>Per ulteriori informazioni, consulta [Confronto date](/help/analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md). |
| **[!UICONTROL Compare time periods]** | Aggiunge le colonne del periodo di tempo di confronto. Disponibile solo quando la dimensione non è basata sul tempo. Sono disponibili diverse opzioni che determinano l&#39;*intervallo di date*: <li>**[!UICONTROL Prior *intervallo di date *a questo intervallo di date]**</li><li>**[!UICONTROL Custom date range to this date range]**. Apre **[!UICONTROL Date range builder]** per specificare l&#39;intervallo di date.</li>Per ulteriori informazioni, consulta [Confronto date](/help/analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md). |
| **[!UICONTROL Modify attribution models]** | Modifica il modello di attribuzione per la colonna. |
| **[!UICONTROL Compare attribution model]** | Specifica un nuovo modello di attribuzione e confrontalo con il modello di attribuzione per la colonna selezionata. Viene aggiunta una nuova colonna con le nuove metriche del modello di attribuzione. Inoltre, viene aggiunta una colonna Percentuale di variazione per il confronto. |
| **[!UICONTROL Reset column widths]** | Ripristina la larghezza predefinita delle colonne. |
| **[!UICONTROL Create annotation from selection]** | Apri **[!UICONTROL Annotation details]** per aggiungere un&#39;annotazione. |
| **[!UICONTROL Create filter from selection]** | Apri **[!UICONTROL Filter builder]** per creare un filtro dalla selezione. |
| **[!UICONTROL Create audience from selection]** | Apri la finestra di dialogo **[!UICONTROL Create audience]** per creare un pubblico dalla selezione. |

## Modificare l&#39;altezza delle righe

È possibile impostare la densità di visualizzazione [1 di un progetto su &#x200B;](/help/analyze/analysis-workspace/build-workspace-project/view-density.md), **[!UICONTROL Compact]** e **[!UICONTROL Comfortable]**.**[!UICONTROL Expanded]**
