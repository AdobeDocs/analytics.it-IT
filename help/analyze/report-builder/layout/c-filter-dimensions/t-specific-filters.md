---
description: Filtri che applicano termini di dimensione specifici.
seo-description: Filtri che applicano termini di dimensione specifici.
seo-title: Filtri specifici
solution: Analytics
title: Filtri specifici
topic: Generatore di report
uuid: b 3 a 8187 a -3 d 59-4 da 0-abca-e 933664332 e 3
translation-type: tm+mt
source-git-commit: dcddb02157ac3e62781b602c5e6c7de3ef79b4fc

---


# Filtri specifici

Filtri che applicano termini di dimensione specifici.

Puoi cercare su elementi dimensionali specifici creando un filtro che corrisponda ai criteri esatti. For example, you can create the following type of filter: page in [!DNL homepage.htm], [!DNL contact_us.html], [!DNL corporate_info.html].

**Per creare un filtro specifico**

1. Create or edit a request, and advance to the [!UICONTROL Request Wizard: Step 2].

   ![Risultato passaggio](assets/dimension_filter.png)

1. On the [!UICONTROL Request Wizard: Step 2], click the link next to the dimension in the grid, then choose **[!UICONTROL Filter]**.

   ![Risultato passaggio](assets/choose_page_specific01.png)

1. Enable **[!UICONTROL Specific]**, then enable one of the following options:

   * **Da Intervallo di celle:** Consente di selezionare i dati dalle celle. Potete selezionare:
   * **Tutte le celle nell'intervallo:** Consente di mappare ogni cella per l'intervallo. Il testo descrittivo indica il numero di gruppi di celle da selezionare. Per mappare più di un gruppo di celle, premere il tasto Ctrl mentre si effettuano selezioni successive. Se l'intervallo che deve essere mappato contiene solo una cella, questa è l'unica opzione disponibile
   * **Prima cella di intervallo:** È sufficiente selezionare la cella in alto a sinistra dell'intervallo, quindi scegliere una direzione per i dati. Inoltre, se la richiesta ha più periodi, scegliete la direzione dei punti e scegliete se saltare un numero di celle tra periodi.
   * **Da Elenco:** Consente di selezionare i dati da un elenco a cui è possibile aggiungere dati.
1. If you enable **[!UICONTROL From List]**, select any available listed items or click **[!UICONTROL Add]**.

   When you click **[!UICONTROL Add]**, the [!UICONTROL Select From List] form displays a list of available dimension values for the current request date range, limited to the first 10,000 items. You can search across these items or click **[!UICONTROL More ...]**, which displays the [!UICONTROL Search Form], so that you can create a more detailed search for dimensions.
1. On the [!UICONTROL Select From List], click **[!UICONTROL OK]**.
1. On the [!UICONTROL Choose Page] form, save your Specific filter if you want, then click **[!UICONTROL OK]**.
