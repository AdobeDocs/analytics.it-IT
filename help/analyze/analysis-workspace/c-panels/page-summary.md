---
description: Il pannello di riepilogo mostra le informazioni di riepilogo per una pagina a scelta.
title: Pannello Riepilogo pagina
feature: Panels
role: User, Admin
exl-id: f0b7cd92-17b2-452d-9aab-f78629360ab8
source-git-commit: 2aaa8c0d13755b40ec701ca6342ab773103a0422
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 31%

---

# Pannello Riepilogo pagina {#page-summary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_pagesummary_button"
>title="Riepilogo pagina"
>abstract="Rivedi rapidamente alcune delle metriche di alto livello e lo spostamento da e verso una pagina specifica."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_pagesummary_panel"
>title="Pannello Riepilogo pagina"
>abstract="Rivedi rapidamente alcune delle metriche di alto livello e lo spostamento da e verso una pagina specifica.<br/><br/>**Parametri **<br/>**Aggiungi un elemento dimensione pagina**: apri la barra dei componenti, individua la dimensione della pagina ed espandila facendo clic sulla freccia per visualizzare gli elementi della dimensione. Quindi, trascina nel generatore la pagina specifica di cui desideri ottenere informazioni. Dopo aver trascinato l’elemento della dimensione, il rapporto verrà compilato automaticamente con le informazioni chiave sulla pagina."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Questo articolo documenta il pannello di riepilogo delle pagine in_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_Nessun pannello equivalente in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._

>[!ENDSHADEBOX]

Un pannello **[!UICONTROL Page summary]** consente di esplorare le statistiche chiave relative a pagine specifiche.

## Utilizzo

Per usare un pannello **[!UICONTROL Page summary]**:

1. Crea un pannello **[!UICONTROL Page summary]**. Per informazioni su come creare un pannello, consulta [Creare un pannello](panels.md#create-a-panel).

1. Specifica l’[input](#panel-input) per il pannello.

1. Osserva l’[output](#panel-output) per il pannello.



Puoi accedere al pannello da [!UICONTROL Reports] o da [!UICONTROL Workspace].

| Punto di accesso | Descrizione |
| --- | --- |
| [!UICONTROL Reports] | <ul><li>Il pannello è già stato rilasciato in un progetto.</li><li>La barra a sinistra è compressa.</li><li>È supportata solo la dimensione Pagina.</li><li>È già stata applicata un&#39;impostazione predefinita, in questo caso la pagina visitata più in alto per la dimensione [!UICONTROL Page]. Puoi modificare questa impostazione.</li></ul> |
| Workspace | Crea un nuovo progetto e seleziona l’icona Pannello nella barra a sinistra. Trascina il pannello [!UICONTROL Page summary] sopra la tabella a forma libera. Il campo Pagina [!UICONTROL Dimension Item] viene lasciato vuoto. Seleziona un elemento dimensione dall’elenco a discesa. |

### Input del pannello {#panel-input}

Puoi configurare il pannello [!UICONTROL Page summary] usando le seguenti impostazioni di input:

![Riepilogo input pagina](assets/page-summary-input.png)

| Input | Descrizione |
| --- | --- |
| **[!UICONTROL Page]** | Seleziona una dimensione di pagina per la quale desideri esplorare le statistiche chiave. |

{style="table-layout:auto"}


Seleziona **[!UICONTROL Build]** per creare il pannello.

### Output del pannello {#panel-output}

Il pannello [!UICONTROL Page summary] restituisce un set completo di dati e visualizzazioni di metriche per consentirti di comprendere meglio le statistiche relative a pagine specifiche.

![Pannello Riepilogo pagina](assets/page-summary-output.png)

| Visualizzazione | Descrizione |
| --- | --- |
| **[!UICONTROL Page views]- Mese corrente (finora)** | Una visualizzazione [Summary number](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) che mostra il numero di visualizzazioni di pagina per questa pagina per il mese corrente. |
| **[!UICONTROL Page views]- 4 settimane prima** | Una visualizzazione [Summary number](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) che mostra il numero di visualizzazioni di pagina per questa pagina nell&#39;ultimo mese. |
| **[!UICONTROL Page views]- 52 settimane prima** | Una visualizzazione [Summary number](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) che mostra il numero di visualizzazioni di pagina per questa pagina nell&#39;ultimo anno. |
| **[!UICONTROL Trend]** | Visualizzazione [Line](/help/analyze/analysis-workspace/visualizations/line.md) con tendenze per le visualizzazioni di pagina per il mese corrente, 4 settimane precedenti e 52 settimane precedenti. |
| **[!UICONTROL Percentage of all page views]** | Un numero di riepilogo per la percentuale di tutte le visualizzazioni di pagina che hanno visitato questa pagina. |
| **[!UICONTROL Time spent on page]** | Visualizzazione [Barra orizzontale](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md) che mostra il tempo trascorso su questa pagina. |
| **[!UICONTROL Single page visits]** | [Numero di riepilogo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) che mostra il numero di visualizzazioni di pagina in cui questa pagina è stata l&#39;unica visitata. |
| **[!UICONTROL Reloads]** | [Numero di riepilogo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) che indica il numero di volte in cui un elemento dimensione è stato presente durante un ricaricamento. In genere un ricaricamento si verifica quando un visitatore aggiorna la finestra del browser. |
| **[!UICONTROL Entries]** | Un [Numero di riepilogo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) che mostra il numero di volte in cui un dato elemento dimensione viene acquisito come primo valore in una visita. |
| **[!UICONTROL Exits]** | Un [Numero di riepilogo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) che mostra il numero di volte in cui un dato elemento dimensione viene acquisito come ultimo valore in una visita. |
| **[!UICONTROL Flow]** | Visualizzazione [Flusso](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) con la pagina selezionata come punto focale. Puoi approfondire i dati come in qualsiasi visualizzazione di [Flusso](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md). |

{style="table-layout:auto"}

Utilizza ![Modifica](/help/assets/icons/Edit.svg) per riconfigurare e ricreare il pannello.
