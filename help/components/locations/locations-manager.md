---
description: Configura l’account di importazione cloud e il percorso in cui è possibile caricare i dati di classificazione
keywords: Analysis Workspace
title: Gestione posizioni
feature: Classifications
exl-id: ace70568-220a-44e8-8e5f-f73002b9e2a2
source-git-commit: 273fea86cde8880d9c9e03ac9c6a99b75f70f6cd
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 1%

---

# Gestione posizioni

Gestione posizioni consente di visualizzare, creare, modificare o eliminare conti e posizioni. Possono essere utilizzati per uno dei seguenti scopi:

* Esportazione di file tramite [Feed dati](/help/export/analytics-data-feed/create-feed.md)
* Esportazione di rapporti tramite [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
* Importazione degli schemi tramite [Set di classificazione](/help/components/classifications/sets/overview.md)

## Visualizzare, filtrare e cercare i percorsi

Il gestore posizioni consente di visualizzare tutte le posizioni create. Gli amministratori di sistema possono visualizzare le posizioni create da tutti gli utenti.

1. Per accedere al gestore delle posizioni in Adobe Analytics, seleziona **[!UICONTROL Components]** > **[!UICONTROL Locations]**.

1. (Condizionale) Se sei un amministratore di sistema, puoi abilitare [!UICONTROL **Visualizza posizioni per tutti gli utenti**] per visualizzare le posizioni create da tutti gli utenti dell’organizzazione. <!-- Maybe add a screenshot? This is new functionality -->

1. Filtra o cerca nell’elenco delle posizioni:

   * **Filtro:** Seleziona l’icona Filtro per filtrare l’elenco delle posizioni.

     Puoi filtrare le posizioni per **[!UICONTROL Location Type]**, **[!UICONTROL Account]**, o **[!UICONTROL Created By]**.

     ![Filtri posizioni](assets/locations-filters.png)

   * **Cerca:** Nel campo di ricerca, inizia a digitare il nome della posizione che desideri visualizzare. I risultati vengono filtrati durante la digitazione. La ricerca viene eseguita nelle colonne seguenti: **Nome posizione**, **Tipo di posizione**, **Account**, e **Creato da**.

1. (Facoltativo) Se disponi di più di 1.000 posizioni, vengono visualizzate solo le prime 1.000. Seleziona [!UICONTROL **Carica di più**] per caricare altre 1.000 posizioni.

## Configurare le colonne nel gestore Posizioni

Le colonne seguenti sono disponibili in Gestione posizioni. Per personalizzare le colonne visualizzate nella tabella, selezionare **Personalizza tabella** icona ![Icona Personalizza tabella](assets/customize-table-icon.png).

* **[!UICONTROL Location name]**: nome della posizione. Seleziona il menu a 3 punti accanto al nome di una posizione per: [modifica la posizione](/help/components/locations/configure-import-locations.md) o eliminarlo.
* **[!UICONTROL Location type]**: tipo di account associato alla posizione.
* **[!UICONTROL Account]**: l’account specifico associato alla posizione.
* **Applicazione**: tipo di applicazione con cui può essere utilizzata la posizione (ad esempio Feed dati, Data Warehouse o Set di classificazione).
* **[!UICONTROL Last used]**: data dell’ultimo utilizzo della posizione.
* **[!UICONTROL Created by]**: utente che ha creato la posizione.
* **[!UICONTROL Date created]**: data di creazione della posizione.

## Creare e gestire le posizioni

Puoi creare, modificare ed eliminare le posizioni.

### Creare una posizione

Per informazioni su come creare una posizione, consulta [Configurare i percorsi di importazione ed esportazione cloud](/help/components/locations/configure-import-locations.md).

<!-- Do I need to add some steps here about how to create a location and then assign that location to be used with DF, DW, or Classifications sets? Need to hear back from Ron and team whether we are including this functionality -->

### Modificare una posizione

Per informazioni su come modificare una posizione, consulta [Configurare i percorsi di importazione ed esportazione cloud](/help/components/locations/configure-import-locations.md).

### Eliminare una posizione

>[!IMPORTANT]
>
>Se una posizione viene eliminata, eventuali file di feed dati, rapporti di Data Warehouse o schemi di set di classificazione associati alla posizione eliminata non riusciranno al successivo utilizzo.
>
>Se elimini una posizione, devi [modificare i feed dati](/help/export/analytics-data-feed/create-feed.md), [Data Warehouse rapporti](/help/export/data-warehouse/create-request/dw-request-report-destinations.md), e [Schemi dei set di classificazione](/help/components/classifications/sets/manage/schema.md) per utilizzare una posizione funzionante.

Per eliminare una posizione nel gestore Posizioni in Adobe Analytics:

1. Seleziona **[!UICONTROL Components]** > **[!UICONTROL Locations]**, quindi seleziona la [!UICONTROL **Posizioni**] scheda.

1. Selezionare il menu a 3 punti nella [!UICONTROL **Nome posizione**] per la posizione da eliminare.

1. Seleziona [!UICONTROL **Elimina**].

## Modificare un account

1. Per modificare gli account nel gestore Posizioni in Adobe Analytics, seleziona **[!UICONTROL Components]** > **[!UICONTROL Locations]**, quindi seleziona la [!UICONTROL **Account ubicazione**] scheda.

1. (Condizionale) Se sei un amministratore di sistema, puoi abilitare [!UICONTROL **Visualizza account per tutti gli utenti**] per visualizzare le posizioni create da tutti gli utenti dell’organizzazione. <!-- Maybe add a screenshot? This is new functionality -->


1. Seleziona [!UICONTROL **Visualizza dettagli**] sull&#39;account che si desidera modificare.

1. Apporta le modifiche desiderate, quindi seleziona [!UICONTROL **Salva**].

## Visualizza chiavi account

Dopo aver creato un account, puoi visualizzare tutte le chiavi di account associate per tale account. Potrebbe essere necessario visualizzare queste informazioni se non hai completato la configurazione dell’account con il provider cloud quando [ha configurato originariamente l’account](/help/components/locations/configure-import-accounts.md).

Per visualizzare le chiavi associate a un account di esportazione:

1. In Adobe Analytics, seleziona **[!UICONTROL Components]** > **[!UICONTROL Locations]**, quindi seleziona la [!UICONTROL **Account ubicazione**] scheda.

1. Seleziona l’icona a tre punti sull’account da modificare, quindi seleziona [!UICONTROL **Chiavi account**].

## Eliminare un account

1. In Adobe Analytics, seleziona **[!UICONTROL Components]** > **[!UICONTROL Locations]**, quindi seleziona la [!UICONTROL **Account ubicazione**] scheda.

1. Seleziona l’icona a tre punti sull’account da modificare, quindi seleziona [!UICONTROL **Elimina account**]
