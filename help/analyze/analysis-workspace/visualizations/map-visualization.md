---
description: Utilizza la visualizzazione mappa per tracciare i dati su una visualizzazione mappa geografica.
title: Mappa
uuid: 6038f336-62a3-4efa-8316-4d7792468db3
feature: Visualizations
role: User, Admin
exl-id: a60544b4-27b6-413a-96ce-ab9487594422
source-git-commit: 8b1e25b9633b6db3e49da079f7014e6b7b595474
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 18%

---

# Mappa {#map}

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_button"
>title="Mappa"
>abstract="Questa visualizzazione rappresenta le metriche sovrapponendole su una mappa. Questa visualizzazione è utile per identificare i dati tra diverse aree geografiche."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_bubbles"
>title="Bolle"
>abstract="Traccia gli eventi utilizzando le bolle."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_heatmap"
>title="Heatmap"
>abstract="Traccia gli eventi utilizzando una mappa termica."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Questo articolo documenta la visualizzazione Mappa in_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**._<br/>_Consulta la [Mappa](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/map) per_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** versione di questo articolo._

>[!ENDSHADEBOX]



Visualizzazione ![Globe](/help/assets/icons/Globe.svg) **[!UICONTROL Map]** in Analysis Workspace

* consente di creare una mappa visiva di qualsiasi metrica (comprese le metriche calcolate),
* è utile per identificare e confrontare dati metrici tra diverse aree geografiche,
* può supportare 2 origini di dati: latitudine/longitudine per utilizzo mobile o dimensione geografica per utilizzo web,
* supporta l’esportazione in PDF e
* utilizza WebGL per la visualizzazione grafica. Se i driver di grafica non supportano il rendering WebGL, potrebbe essere necessario aggiornare i driver.


>[!BEGINSHADEBOX]

Per un video dimostrativo, consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Visualizzazione mappa in Analysis Workspace](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/visualizations/map-visualization){target="_blank"}.

>[!ENDSHADEBOX]


## Utilizzo

1. Aggiungi una visualizzazione ![Mappa](/help/assets/icons/Globe.svg) [!UICONTROL Map]. Vedi [Aggiungere una visualizzazione a un pannello](freeform-analysis-visualizations.md#add-visualizations-to-a-panel). Puoi trascinare una visualizzazione Mappa solo sopra una tabella a forma libera.

   ![Configurazione mappa](assets/map-configuration.png){width="50%"}

1. Seleziona una metrica dall’elenco a discesa. Oppure trascina una metrica dall’elenco delle metriche (comprese le metriche calcolate).
1. Specificare l&#39;origine dati da cui si desidera disegnare. Questa finestra di dialogo viene visualizzata solo se il tracciamento della posizione è abilitato per i dati delle app mobili.

   | Origine | Descrizione |
   | --- | --- |
   | **[!UICONTROL Mobile Lat/Long]** | Questa opzione rappresenta i dati delle app mobili. Questa opzione è disponibile solo se è stata abilitata per la suite di rapporti in [!UICONTROL Analytics] > [!UICONTROL Admin] > [!UICONTROL Report Suites] > (seleziona una suite di rapporti) > [!UICONTROL Edit Settings] > [!UICONTROL Mobile Management] > [!UICONTROL Enable Location Tracking]. Questa è l&#39;impostazione predefinita (se è abilitato il tracciamento della posizione). |
   | **[!UICONTROL Geographic Dimension]** | Questa opzione rappresenta i dati di segmentazione geografica sulla posizione del visitatore in base all’indirizzo IP del visitatore. Questi dati vengono trasformati in [!UICONTROL Country], [!UICONTROL Region] e [!UICONTROL City]. Si noti che non passa al livello DMA o Codice postale. Questa dimensione è abilitata in quasi tutte le suite di rapporti. In caso contrario, contatta l’Assistenza clienti di Adobe per far sì che i rapporti geografici siano abilitati. |

1. Seleziona **[!UICONTROL Build]**.

   Viene generata una visualizzazione con mappa del mondo con bolle.

   ![](assets/bubble-world-view.png)

1. Ora puoi:

   * **Ingrandisci** la mappa per ingrandire alcune aree facendo doppio clic sulla mappa o utilizzando la rotellina di scorrimento. La mappa si ingrandisce in base alla posizione del cursore. Attraverso l’interazione di zoom, la dimensione richiesta (paese > stato > città) viene aggiornata automaticamente, in base al livello di zoom.
   * **Confronta** due o più visualizzazioni mappa nello stesso progetto posizionandole una accanto all&#39;altra.
   * **Mostra confronti periodo su periodo (ad esempio anno su anno)**:

      * Mostra numeri negativi: ad esempio, per una metrica su base annua, la mappa può visualizzare -33% su New York.
      * Con metriche di tipo *percent*, il clustering calcola la media delle percentuali insieme.
      * Schema di colori verde/rosso: positivo/negativo

   * **Ruota** la mappa in 2D o 3D tenendo premuto il tasto [!UICONTROL Ctrl] mentre sposti la mappa.

   * **Attiva** una visualizzazione diversa, ad esempio la mappa di calore, utilizzando le [impostazioni](/help/analyze/analysis-workspace/visualizations/map-visualization.md#section_5F89C620A6AA42BC8E0955478B3A427E) descritte di seguito. La vista a bolle è l&#39;impostazione di default.

1. **Salva** il progetto per salvare tutte le impostazioni della mappa (coordinate, zoom, rotazione).
1. La tabella a forma libera, sotto la visualizzazione, può essere compilata trascinando dimensioni e metriche della posizione dalla barra a sinistra.



## Configurare

Per riconfigurare la visualizzazione Mappa, seleziona ![Modifica](/help/assets/icons/Edit.svg).


## Impostazioni

Per definire le impostazioni per la visualizzazione, seleziona ![Impostazione](/help/assets/icons/Setting.svg).

| Impostazione | Descrizione |
|--- |--- |
| **[!UICONTROL Map type]** | |
| **[!UICONTROL Bubbles] | Traccia gli eventi utilizzando le bolle. Un grafico a bolle è un grafico a più variabili che è un incrocio tra un grafico a dispersione e un grafico ad area proporzionale. Questa è l&#39;impostazione predefinita. |
| [!UICONTROL Heatmap] | Traccia gli eventi utilizzando una mappa di calore. Una mappa di calore è una rappresentazione grafica dei dati in cui i singoli valori contenuti in una matrice sono rappresentati come colori. |
| **[!UICONTROL Styles]** | |
| [!UICONTROL Color theme] | Mostra la combinazione di colori per la mappa di calore e le bolle. Puoi scegliere tra Coral, Reds, Greens o Blues. L&#39;impostazione predefinita è Coral. |
| [!UICONTROL Map style] | È possibile scegliere tra Basic, Streets, Bright, Light, Dark e Satellite. |
| **[!UICONTROL Cluster Radius]** | Raggruppa i punti dati che rientrano nel numero di pixel specificato. Il valore predefinito è 50. |
| **[!UICONTROL Custom Max Value]** | Permette di modificare la soglia del valore massimo per la mappa. Quando regoli questo valore, viene regolata la scala dei valori per le bolle o la mappa di calore (colore e dimensioni) rispetto al valore massimo personalizzato impostato. |

<!--
## Build a time-parting heatmap

Here is a video on the topic:

>[!VIDEO](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/visualizations/build-a-time-parting-heatmap)

-->

