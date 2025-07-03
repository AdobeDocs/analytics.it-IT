---
description: Utilizza la visualizzazione mappa per tracciare i dati su una visualizzazione mappa geografica.
title: Mappa
uuid: 6038f336-62a3-4efa-8316-4d7792468db3
feature: Visualizations
role: User, Admin
exl-id: a60544b4-27b6-413a-96ce-ab9487594422
source-git-commit: bf8bc40e3ec325e8e70081955fb533eee66a1734
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 54%

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

_Questo articolo documenta la visualizzazione Mappa in_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**._<br/>_Nessuna visualizzazione Mappa attualmente disponibile in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**._

>[!ENDSHADEBOX]



Visualizzazione ![Globe](/help/assets/icons/Globe.svg) **[!UICONTROL Map]** in Analysis Workspace

* consente di creare una mappa visiva di qualsiasi metrica (comprese le metriche calcolate),
* è utile per identificare e confrontare dati metrici tra diverse aree geografiche,
* può supportare 2 origini di dati: latitudine/longitudine per utilizzo mobile o dimensione geografica per utilizzo web,
* supporta l’esportazione in PDF e
* utilizza WebGL per la visualizzazione grafica. se il driver della scheda grafica non supporta il rendering WebGL, può essere necessario aggiornare i driver.


>[!BEGINSHADEBOX]

Per un video dimostrativo, consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Visualizzazione mappa in Analysis Workspace](https://video.tv.adobe.com/v/23559/?quality=12){target="_blank"}.

>[!ENDSHADEBOX]


## Utilizzo

1. Aggiungi una visualizzazione ![Mappa](/help/assets/icons/Globe.svg) [!UICONTROL Map]. Vedi [Aggiungere una visualizzazione a un pannello](freeform-analysis-visualizations.md#add-visualizations-to-a-panel). Puoi trascinare una visualizzazione Mappa solo sopra una tabella a forma libera.

   ![Configurazione mappa](assets/map-configuration.png){width="50%"}

1. Seleziona una metrica dall’elenco a discesa. Oppure trascina una metrica dall’elenco delle metriche (comprese le metriche calcolate).
1. Specificare l&#39;origine dati da cui si desidera disegnare. Questa finestra di dialogo viene visualizzata solo se il tracciamento della posizione è abilitato per i dati delle app mobili.

   | Origine | Descrizione |
   | --- | --- |
   | **[!UICONTROL Mobile Lat/Long]** | Questa opzione rappresenta i dati delle app mobili. Questa opzione è disponibile solo se è stata abilitata per la suite di rapporti in [!UICONTROL Analytics] > [!UICONTROL Admin] > [!UICONTROL Report Suites] > (seleziona una suite di rapporti) > [!UICONTROL Edit Settings] > [!UICONTROL Mobile Management] > [!UICONTROL Enable Location Tracking]. Questa è l&#39;impostazione predefinita (se è abilitato il tracciamento della posizione). |
   | **[!UICONTROL Geographic Dimension]** | Questa opzione rappresenta i dati per segmentazione geografica sulla posizione del visitatore, in base al suo indirizzo IP. Questi dati vengono trasformati in [!UICONTROL Country], [!UICONTROL Region] e [!UICONTROL City]. Si noti che non passa al livello DMA o Codice postale. Questa dimensione è abilitata per quasi tutte le suite di rapporti. Se non lo è, contatta l’Assistenza clienti Adobe e richiedi che vengano abilitati i rapporti geografici. |

1. Seleziona **[!UICONTROL Build]**.

   Viene generata una visualizzazione con mappa del mondo con bolle.

   ![](assets/bubble-world-view.png)

1. Ora puoi:

   * Fai uno **zoom** nella mappa per ingrandire l’area che ti interessa, facendo doppio clic o utilizzando la rotellina del mouse. La mappa viene ingrandita sul punto in cui si trova il cursore. Quando esegui lo zoom, la dimensione richiesta viene automaticamente aggiornata (Paese > stato/provincia > città), a seconda del livello di zoom.
   * **Confronta** due o più visualizzazioni mappa nello stesso progetto, affiancandole.
   * **Mostra i dati a confronto per specifici periodi (ad esempio, su base annua)**:

      * Mostra numeri negativi: ad esempio, per una metrica su base annua, la mappa può visualizzare -33% su New York.
      * Con metriche di tipo *percent*, il clustering calcola la media delle percentuali insieme.
      * Schema di colori verde/rosso: positivo/negativo

   * **Ruota** la mappa in 2D o 3D tenendo premuto il tasto [!UICONTROL Ctrl] mentre sposti la mappa.

   * **Passa** a un’altra vista, ad esempio una mappa di calore, utilizzando le [impostazioni](/help/analyze/analysis-workspace/visualizations/map-visualization.md#section_5F89C620A6AA42BC8E0955478B3A427E) descritte di seguito. La vista predefinita è la mappa a bolle.

1. **Salva** il progetto per salvare tutte le impostazioni della mappa (coordinate, zoom, rotazione).
1. La tabella a forma libera, sotto la visualizzazione, può essere compilata trascinando dimensioni e metriche della posizione dalla barra a sinistra.



## Configurare

Per riconfigurare la visualizzazione Mappa, seleziona ![Modifica](/help/assets/icons/Edit.svg).


## Impostazioni

Per definire le impostazioni per la visualizzazione, seleziona ![Impostazione](/help/assets/icons/Setting.svg).

| Impostazione | Descrizione |
|--- |--- |
| **[!UICONTROL Map type]** | |
| **[!UICONTROL Bubbles] | Traccia gli eventi tramite una rappresentazione a bolle. Un grafico a bolle è un grafico con più variabili, un incrocio tra un grafico a dispersione e un grafico a superfici proporzionali. Questa è l&#39;impostazione predefinita. |
| [!UICONTROL Heatmap] | Traccia gli eventi tramite una mappa di calore. Si tratta di una rappresentazione grafica in cui i singoli valori di una matrice sono rappresentati da colori. |
| **[!UICONTROL Styles]** | |
| [!UICONTROL Color theme] | Mostra lo schema di colori utilizzato per la mappa di calore e le bolle. Puoi scegliere tra Corallo, Rossi, Verdi e Blu. L&#39;impostazione predefinita è Coral. |
| [!UICONTROL Map style] | È possibile scegliere tra Basic, Streets, Bright, Light, Dark e Satellite. |
| **[!UICONTROL Cluster Radius]** | Raggruppa i dati che si trovano entro un certo numero di pixel. Il valore predefinito è 50. |
| **[!UICONTROL Custom Max Value]** | Permette di modificare la soglia del valore massimo per la mappa. Quando regoli questo valore, viene regolata la scala dei valori per le bolle o la mappa di calore (colore e dimensioni) rispetto al valore massimo personalizzato impostato. |

<!--
## Build a time-parting heatmap

Here is a video on the topic:

>[!VIDEO](https://video.tv.adobe.com/v/26991/?quality=12)

-->

