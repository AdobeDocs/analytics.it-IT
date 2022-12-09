---
description: Filtri che applicano termini di dimensione specifici.
title: Filtri specifici
uuid: b3a8187a-3d59-4da0-abca-e933664332e3
feature: Report Builder
role: User, Admin
exl-id: e5f2d67c-3add-4d51-8a76-ee3b2a6eef94
source-git-commit: e7346b11a7d3eb4c18ec02df6c8a07574e02a2b4
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 2%

---

# Filtri specifici

Filtri che applicano termini di dimensione specifici.

Puoi cercare elementi dimensionali specifici creando un filtro che corrisponda a criteri esatti. Ad esempio, puoi creare il seguente tipo di filtro: in [!DNL homepage.htm], [!DNL contact_us.html], [!DNL corporate_info.html].

**Per creare un filtro specifico**

1. Crea o modifica una richiesta e passa alla [!UICONTROL Request Wizard: Step 2].

   ![Risultato del passaggio](/help/admin/admin/assets/filter.png)

1. Sulla [!UICONTROL Request Wizard: Step 2], fai clic sul collegamento accanto alla dimensione nella griglia, quindi scegli **[!UICONTROL Filter]**.

   ![Risultato del passaggio](assets/choose_page_specific01.png)

1. Abilita **[!UICONTROL Specific]**, quindi attiva una delle seguenti opzioni:

   * **Da intervallo di celle:** Consente di selezionare i dati dalle celle. Puoi selezionare:
   * **Tutte le celle nell&#39;intervallo:** Permette di mappare ogni cella per l&#39;intervallo. Il testo descrittivo spiega il numero di gruppi di celle da selezionare. Per mappare più di un gruppo di celle, premere il tasto Ctrl mentre si eseguono selezioni successive. Se l’intervallo da mappare contiene una sola cella, questa è l’unica opzione disponibile
   * **Prima cella dell&#39;intervallo:** È sufficiente selezionare la cella in alto a sinistra dell’intervallo, quindi scegliere una direzione per i dati. Inoltre, se la richiesta ha più periodi, scegli la direzione dei periodi e scegli se desideri saltare un determinato numero di celle tra i periodi.
   * **Dall’elenco:** Consente di selezionare i dati da un elenco a cui è possibile aggiungere dati.
1. Se si abilita **[!UICONTROL From List]**, seleziona gli elementi elencati disponibili o fai clic su **[!UICONTROL Add]**.

   Quando fai clic su **[!UICONTROL Add]**, [!UICONTROL Select From List] In form viene visualizzato un elenco di elementi dimensionali disponibili per l&#39;intervallo di date della richiesta corrente, limitato ai primi 10.000 elementi. Puoi eseguire ricerche tra questi elementi o fare clic su **[!UICONTROL More ...]**, che visualizza la [!UICONTROL Search Form], per creare una ricerca più dettagliata delle dimensioni.
1. Sulla [!UICONTROL Select From List], fai clic su **[!UICONTROL OK]**.
1. Sulla [!UICONTROL Choose Page] modulo, salvare il filtro specifico, se lo si desidera, quindi fare clic su **[!UICONTROL OK]**.
