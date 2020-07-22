---
description: Filtri che applicano termini di dimensione specifici.
title: Filtri specifici
topic: Report builder
uuid: b3a8187a-3d59-4da0-abca-e933664332e3
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 2%

---


# Filtri specifici

Filtri che applicano termini di dimensione specifici.

Potete eseguire ricerche su elementi dimensionali specifici creando un filtro che corrisponda a criteri esatti. Ad esempio, potete creare il seguente tipo di filtro: pagina in [!DNL homepage.htm], [!DNL contact_us.html], [!DNL corporate_info.html].

**Per creare un filtro specifico**

1. Create o modificate una richiesta e passate al [!UICONTROL Request Wizard: Step 2].

   ![Risultato passaggio](assets/dimension_filter.png)

1. Fare clic sul [!UICONTROL Request Wizard: Step 2]collegamento accanto alla quota nella griglia, quindi scegliere **[!UICONTROL Filter]**.

   ![Risultato passaggio](assets/choose_page_specific01.png)

1. Attiva **[!UICONTROL Specific]**, quindi abilita una delle seguenti opzioni:

   * **Dall&#39;intervallo di celle:** Consente di selezionare i dati dalle celle. Potete selezionare:
   * **Tutte le celle nell&#39;intervallo:** Consente di mappare ogni cella per l&#39;intervallo. Il testo descrittivo spiega il numero di gruppi di celle da selezionare. Per mappare più di un gruppo di celle, premere il tasto Ctrl mentre si eseguono le selezioni successive. Se l&#39;intervallo da mappare contiene una sola cella, questa è l&#39;unica opzione disponibile
   * **Prima cella dell&#39;intervallo:** È sufficiente selezionare la cella in alto a sinistra dell’intervallo e quindi scegliere una direzione per i dati. Inoltre, se la richiesta ha più periodi, potete scegliere la direzione dei periodi e scegliere se ignorare un determinato numero di celle tra i periodi.
   * **Da elenco:** Consente di selezionare i dati da un elenco a cui è possibile aggiungere i dati.
1. Se si abilita **[!UICONTROL From List]**, selezionare gli elementi elencati disponibili o fare clic su **[!UICONTROL Add]**.

   Quando si fa clic **[!UICONTROL Add]**, nel [!UICONTROL Select From List] modulo viene visualizzato un elenco degli elementi dimensionali disponibili per l&#39;intervallo di date della richiesta corrente, limitato ai primi 10.000 elementi. Potete eseguire una ricerca tra questi elementi o fare clic **[!UICONTROL More ...]**, per visualizzare il [!UICONTROL Search Form]contenuto, in modo da creare una ricerca più dettagliata delle dimensioni.
1. On the [!UICONTROL Select From List], click **[!UICONTROL OK]**.
1. Sul [!UICONTROL Choose Page] modulo, salvare il filtro Specifico, se lo si desidera, quindi fare clic su **[!UICONTROL OK]**.
