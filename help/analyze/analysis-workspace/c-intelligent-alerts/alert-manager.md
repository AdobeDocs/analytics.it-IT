---
description: Crea, modifica o elimina gli avvisi.
title: Gestione avvisi (Analysis Workspace)
feature: Alerts
role: User, Admin
exl-id: c33a9a30-f53f-443c-96b7-6a87d03573c7
source-git-commit: 58e1d3025b455de7fa07037b3b0659330c8324c7
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 5%

---


# Gestire gli avvisi

È possibile gestire gli avvisi esistenti nella Gestione avvisi. È possibile eseguire varie attività di gestione sugli avvisi, ad esempio assegnare tag, rinominare, eliminare e altro ancora.

La gestione avvisi è strutturata in modo analogo alla [gestione segmenti](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=it) e alla [gestione metriche calcolate](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=it).

## Creare avvisi

Per creare avvisi da Gestione avvisi:

1. Selezionare **[!UICONTROL Components]** > **[!UICONTROL Alerts]** per accedere alla Gestione avvisi in Adobe Analytics.

   ![](assets/alert-manager.png)

1. Seleziona [!UICONTROL **Aggiungi**] (o [!UICONTROL **Crea nuovo avviso**] se non hai avvisi esistenti).

1. Selezionare il tipo di avviso corrispondente all&#39;avviso che si desidera creare:

   * [!UICONTROL **Avviso dati di Analytics**]: un avviso per avvisarti quando si verificano eventi anomali nei tuoi dati.

     Se selezioni questa opzione, continua con [Crea avvisi](/help/analyze/analysis-workspace/c-intelligent-alerts/alert-builder.md) per ulteriori dettagli sulla creazione di avvisi.

   * [!UICONTROL **Avviso sull&#39;utilizzo delle chiamate al server**]: un avviso per notificare il rischio o il verificarsi di un superamento nei dati relativi al consumo e all&#39;impegno delle chiamate al server.

     Se si seleziona questa opzione, continuare con [Avvisi di utilizzo delle chiamate server](/help/admin/admin/c-server-call-usage/scu-alerts.md).

     >[!NOTE]
     >
     >Per poter accedere all’utilizzo delle chiamate al server, devi essere un amministratore di Analytics o un utente con l’autorizzazione di utilizzo delle chiamate al server.




## Gestire gli avvisi esistenti

Per gestire gli avvisi esistenti in Gestione avvisi:

1. Selezionare **[!UICONTROL Components]** > **[!UICONTROL Alerts]** per accedere alla Gestione avvisi in Adobe Analytics.

   ![](assets/alert-manager.png)

1. Seleziona uno o più avvisi da gestire.

   ![](assets/alert-manager-tasks.png)

1. Nella barra delle azioni, seleziona una delle opzioni seguenti:

   | Azione | Funzione |
   |---------|----------|
   | [!UICONTROL **Tag**] | Applicare un tag a un avviso. In questo modo è possibile organizzare gli avvisi in modo semplice e intuitivo. |
   | [!UICONTROL **Elimina**] | Elimina l’avviso. |
   | [!UICONTROL **Rinomina**] | Rinomina l&#39;avviso. |
   | [!UICONTROL **Approva**] | Contrassegna l&#39;avviso come Approvato. |
   | [!UICONTROL **Copia**] | Crea una copia (duplicata) dell&#39;avviso. |
   | [!UICONTROL **Disattiva**] | Disattiva un avviso attualmente abilitato. |
   | [!UICONTROL **Abilita**] | Abilita un avviso attualmente disabilitato. |
   | [!UICONTROL **Rinnova**] | Rinnova la data di scadenza dell’avviso. Questa funzione sposta la data di scadenza a 1 anno dal giorno in cui hai selezionato questa opzione, indipendentemente dalla data di scadenza originale. |
   | [!UICONTROL **Esporta in CSV**] | Esporta l&#39;avviso in un file CSV. |
