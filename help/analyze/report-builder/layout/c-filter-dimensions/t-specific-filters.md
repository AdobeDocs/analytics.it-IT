---
description: Filtri che applicano termini di dimensione specifici.
title: Filtri specifici
uuid: b3a8187a-3d59-4da0-abca-e933664332e3
feature: Report Builder
role: User, Admin
exl-id: e5f2d67c-3add-4d51-8a76-ee3b2a6eef94
source-git-commit: fb39f906d6c08713e4dc8211c917b2942502868e
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 1%

---

# Filtri specifici

Filtri che applicano termini di dimensione specifici.

Puoi eseguire ricerche su elementi dimensionali specifici creando un filtro che corrisponda a criteri esatti. Ad esempio, puoi creare il seguente tipo di filtro: pagina in [!DNL homepage.htm], [!DNL contact_us.html], [!DNL corporate_info.html].

**Per creare un filtro specifico**

1. Creare o modificare una richiesta e passare alla [!UICONTROL Request Wizard: Step 2].

   ![Schermata che mostra le opzioni Filtra per: Applicazione, Utente e Progetto.](/help/admin/admin/assets/filter.png)

1. Il giorno [!UICONTROL Request Wizard: Step 2], fai clic sul collegamento accanto alla dimensione nella griglia, quindi scegli **[!UICONTROL Filter]**.

1. Abilita **[!UICONTROL Specific]**.

   ![Schermata della finestra di dialogo Scegli pagina con l’opzione Specifico selezionata.](assets/choose_page_specific01.png)

1. Abilita una delle seguenti opzioni specifiche:

   * **Da intervallo di celle:** Consente di selezionare i dati dalle celle. Puoi selezionare:
      * **Tutte le celle nell&#39;intervallo:** Consente di mappare ogni cella dell’intervallo. Il testo descrittivo spiega il numero di gruppi di celle da selezionare. Per eseguire il mapping di più gruppi di celle, premere il tasto Ctrl mentre si effettuano selezioni successive. Se l’intervallo da mappare contiene una sola cella, questa è l’unica opzione disponibile
      * **Prima cella dell&#39;intervallo:** È sufficiente selezionare la cella superiore sinistra dell&#39;intervallo e quindi scegliere una direzione per i dati. Inoltre, se la richiesta ha più periodi, è possibile scegliere la direzione dei periodi e scegliere se si desidera saltare un numero impostato di celle tra i periodi.
   * **Dall&#39;elenco:** Consente di selezionare i dati da un elenco a cui è possibile aggiungere dati.
1. Se si abilita **[!UICONTROL From List]**, seleziona gli elementi elencati disponibili o fai clic su **[!UICONTROL Add]**.

   Quando fai clic su **[!UICONTROL Add]**, il [!UICONTROL Select From List] form visualizza un elenco di elementi dimensionali disponibili per l’intervallo di date della richiesta corrente, limitato ai primi 10.000 elementi. Puoi eseguire ricerche tra questi elementi o fare clic su **[!UICONTROL More ...]**, che visualizza il [!UICONTROL Search Form], in modo da poter creare una ricerca più dettagliata per le dimensioni.
1. Il giorno [!UICONTROL Select From List], fai clic su **[!UICONTROL OK]**.
1. Il giorno [!UICONTROL Choose Page] , salva il filtro Specific (Specifici), se lo desideri, quindi fai clic su **[!UICONTROL OK]**.
