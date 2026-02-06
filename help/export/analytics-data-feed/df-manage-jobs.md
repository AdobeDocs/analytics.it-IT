---
title: Gestisci processi feed dati
description: Scopri come gestire singoli lavori nei feed dati. Naviga nell’interfaccia, utilizza i filtri e cerca, quindi trova le definizioni delle colonne.
feature: Data Feeds
exl-id: b17e333e-290f-42e4-b304-1e34282237a7
source-git-commit: d042bdb680504fdbf0ba346e5829713e529bd543
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 4%

---

# Gestire i processi per feed dati

I job sono singole attività che generano un file compresso. Sono create e gestite dai feed.

È possibile visualizzare la cronologia dei processi per ogni feed di dati, inviare nuovamente i processi o rielaborare i processi.

## Visualizzare la cronologia dei processi per un feed di dati

Puoi visualizzare un elenco di processi di feed dati per un dato feed dati, insieme alle informazioni su ciascun processo.

Per visualizzare la cronologia dei processi per un feed di dati:

1. Accedi a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) utilizzando le credenziali Adobe ID.

1. Seleziona l&#39;icona a 9 quadrati in alto a destra, quindi seleziona [!UICONTROL **Analytics**].

1. Nella barra di navigazione superiore, passa a [!UICONTROL **Amministratore**] > [!UICONTROL **Feed dati**].

   Vengono visualizzati i feed di dati per tutte le suite di rapporti a cui hai accesso. Oppure, se non è stato configurato alcun feed, la pagina mostra un pulsante **[!UICONTROL Create data feed]**.

   ![Gestione feed dati](assets/data-feed-manager.png)

1. Selezionare la casella di controllo accanto al feed di dati contenente i processi che si desidera visualizzare, quindi selezionare [!UICONTROL **Cronologia processi**].

   Viene visualizzata la cronologia dei processi di feed dati, con le informazioni su ciascun processo nelle colonne disponibili.

1. (Facoltativo) Per regolare le colonne visibili nella tabella, seleziona l&#39;icona della colonna ![Icona della colonna](assets/customize-columns-icon.png) in alto a destra, quindi nella finestra di dialogo Personalizza tabella seleziona ogni colonna che desideri visualizzare e deseleziona ogni colonna che desideri nascondere.

   Sono disponibili le seguenti colonne:

   * **[!UICONTROL Request period begin]**

   * **[!UICONTROL Request period end]**

   * **[!UICONTROL Scheduled]**

   * **[!UICONTROL Started]**

   * **[!UICONTROL Finished]**

   * **[!UICONTROL Run #]**

   * **[!UICONTROL Status]**

   * **[!UICONTROL Error code]**

   * **[!UICONTROL Error message]**

## Invia di nuovo processi feed dati

Quando invii nuovamente un processo di feed dati, questo invia nuovamente il file di feed dati con gli stessi dati ed elaborazione di quando è stato inviato originariamente. In alternativa, è possibile [rielaborare un processo di feed dati](#reprocess-data-feed-jobs).

Per inviare nuovamente uno o più processi di feed dati:

1. In Adobe Analytics, seleziona [!UICONTROL **Amministratore**] > [!UICONTROL **Feed dati**].

1. Selezionare la casella di controllo accanto al feed di dati contenente i processi che si desidera inviare di nuovo, quindi selezionare [!UICONTROL **Cronologia processi**].

1. Selezionare la casella di controllo accanto a uno o più processi di feed dati, quindi selezionare **[!UICONTROL Resend]**. <!-- What does the status need to be? Error, ... -->

   ![Rielabora processo feed dati](assets/data-feed-job-resend.png)

## Rielabora processi feed dati

Quando si rielabora un processo di feed dati, questi rielabora i dati di origine di un processo di feed dati e li invia nuovamente con i dati rielaborati. In alternativa, è possibile [inviare nuovamente un processo di feed dati](#resend-data-feed-jobs).

Per rielaborare uno o più processi di feed dati:

1. In Adobe Analytics, seleziona [!UICONTROL **Amministratore**] > [!UICONTROL **Feed dati**].

1. Selezionare la casella di controllo accanto al feed di dati contenente i processi che si desidera rielaborare, quindi selezionare [!UICONTROL **Cronologia processi**].

1. Selezionare la casella di controllo accanto a uno o più processi di feed dati, quindi selezionare **[!UICONTROL Reprocess]**. <!-- What does the status need to be? Error, ... -->

   ![Rielabora processo feed dati](assets/data-feed-job-reprocess.png)
