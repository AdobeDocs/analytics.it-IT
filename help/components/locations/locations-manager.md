---
description: Configura l’account di importazione cloud e il percorso in cui è possibile caricare i dati di classificazione
keywords: Analysis Workspace
title: Gestione posizioni
feature: Classifications
exl-id: ace70568-220a-44e8-8e5f-f73002b9e2a2
source-git-commit: c42ad8d3e0c21cc1fb13f9a8993aca4825286d4f
workflow-type: tm+mt
source-wordcount: '1446'
ht-degree: 1%

---

# Gestione posizioni

Gestione posizioni consente di visualizzare, creare, modificare o eliminare conti e posizioni. Possono essere utilizzati per uno dei seguenti scopi:

* Esportazione di file tramite [Feed dati](/help/export/analytics-data-feed/create-feed.md)
* Esportazione di rapporti tramite [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
* Importazione degli schemi tramite [Set di classificazione](/help/components/classifications/sets/overview.md)

## Visualizzare, filtrare e cercare i percorsi

Il gestore delle posizioni consente di visualizzare tutte le posizioni create dall&#39;utente o condivise con l&#39;organizzazione. Gli amministratori di sistema possono visualizzare le posizioni create da tutti gli utenti, indipendentemente dal fatto che siano condivisi.

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

Una posizione può essere modificata solo dall’utente che l’ha creata o da un amministratore di sistema.

Per informazioni su come modificare una posizione, consulta [Configurare i percorsi di importazione ed esportazione cloud](/help/components/locations/configure-import-locations.md).

### Eliminare una posizione

>[!IMPORTANT]
>
>Se una posizione viene eliminata, eventuali file di feed dati, rapporti di Data Warehouse o schemi di set di classificazione associati alla posizione eliminata non riusciranno al successivo utilizzo.
>
>Se elimini una posizione, devi [modificare i feed dati](/help/export/analytics-data-feed/create-feed.md), [Data Warehouse rapporti](/help/export/data-warehouse/create-request/dw-request-report-destinations.md), e [Schemi dei set di classificazione](/help/components/classifications/sets/manage/schema.md) per utilizzare una posizione funzionante.

Una posizione può essere eliminata solo dall’utente che l’ha creata o da un amministratore di sistema.

Per eliminare una posizione nel gestore Posizioni in Adobe Analytics:

1. Seleziona **[!UICONTROL Components]** > **[!UICONTROL Locations]**, quindi seleziona la [!UICONTROL **Posizioni**] scheda.

1. Selezionare il menu a 3 punti nella [!UICONTROL **Nome posizione**] per la posizione da eliminare.

1. Seleziona [!UICONTROL **Elimina**].

## Creare e gestire gli account

Puoi creare, modificare ed eliminare gli account.

### Creare un account

Per informazioni su come creare un account, consulta [Configurare account di importazione ed esportazione cloud](/help/components/locations/configure-import-accounts.md).

### Modificare un account

Un account può essere modificato solo dall’utente che lo ha creato o da un amministratore di sistema.

Per informazioni su come modificare un account, consulta [Configurare account di importazione ed esportazione cloud](/help/components/locations/configure-import-accounts.md).

### Visualizza chiavi account

Dopo aver creato un account, puoi visualizzare tutte le chiavi di account associate per tale account. Potrebbe essere necessario visualizzare queste informazioni se non hai completato la configurazione dell’account con il provider cloud quando [ha configurato originariamente l’account](/help/components/locations/configure-import-accounts.md).

Per visualizzare le chiavi associate a un account di esportazione:

1. In Adobe Analytics, seleziona **[!UICONTROL Components]** > **[!UICONTROL Locations]**, quindi seleziona la [!UICONTROL **Account ubicazione**] scheda.

1. (Condizionale) Se sei un amministratore di sistema, puoi abilitare [!UICONTROL **Visualizza posizioni per tutti gli utenti**] per visualizzare le posizioni create da tutti gli utenti dell’organizzazione. <!-- Maybe add a screenshot? This is new functionality -->

1. Seleziona l’icona a tre punti sull’account da modificare, quindi seleziona [!UICONTROL **Chiavi account**].

### Eliminare un account

>[!IMPORTANT]
>
>Gli account possono essere eliminati solo se non sono presenti ubicazioni che li utilizzano. Prima di eliminare un account, è necessario eliminare tutte le posizioni dell&#39;account, come descritto in [Eliminare una posizione](#delete-a-location).

Un account può essere eliminato solo dall’utente che lo ha creato o da un amministratore di sistema.

Per eliminare un account:

1. In Adobe Analytics, seleziona **[!UICONTROL Components]** > **[!UICONTROL Locations]**, quindi seleziona la [!UICONTROL **Account ubicazione**] scheda.

1. (Condizionale) Se sei un amministratore di sistema, puoi abilitare [!UICONTROL **Visualizza account per tutti gli utenti**] per visualizzare le posizioni create da tutti gli utenti dell’organizzazione.

1. Seleziona l’icona a tre punti sull’account da modificare, quindi seleziona [!UICONTROL **Elimina account**]

## Configurare le impostazioni a livello di società (solo amministratori)

{{release-limited-testing-section}}

Gli amministratori di sistema possono impedire agli utenti di creare account e posizioni, oppure limitare i tipi di account che gli utenti possono creare e utilizzare.

![Scheda Impostazioni amministratore](assets/locations-admin-settings.png)

### Stabilire se gli utenti possono creare e modificare gli account

Per impostazione predefinita, tutti gli utenti dell’organizzazione possono creare account e modificarli nell’ambiente Adobe Analytics, come descritto in [configurare account di importazione ed esportazione cloud](/help/components/locations/configure-import-accounts.md).

Puoi impedire agli utenti di creare account. In questo caso, gli utenti possono comunque utilizzare gli account già creati, ma non possono più modificarli. È possibile eliminare gli account creati dagli utenti, come descritto in [Eliminare un account](#delete-an-account).

Per impedire a tutti gli utenti di creare e modificare account:

1. In Adobe Analytics, seleziona **[!UICONTROL Components]** > **[!UICONTROL Locations]**, quindi seleziona la [!UICONTROL **Impostazioni di amministrazione**] scheda.

1. In [!UICONTROL **Account posizioni**] , deseleziona l’opzione, [!UICONTROL **Consenti agli utenti di creare e gestire account di posizione**].

1. Seleziona [!UICONTROL **Salva**].

1. (Facoltativo) Elimina tutti gli account creati dagli utenti che non desideri più utilizzare, come descritto in [Eliminare un account](#delete-an-account).

### Stabilire se gli utenti possono creare e modificare le posizioni

Per impostazione predefinita, tutti gli utenti dell’organizzazione possono creare posizioni e modificarle nell’ambiente Adobe Analytics, come descritto in [configurare i percorsi di importazione ed esportazione cloud](/help/components/locations/configure-import-locations.md).

Puoi impedire agli utenti di creare posizioni. In questo caso, gli utenti possono comunque utilizzare le posizioni già create, ma non possono più modificarle. È possibile eliminare le posizioni create dagli utenti, come descritto in [Elimina posizioni](#delete-a-location).

Per impedire a tutti gli utenti di creare e modificare posizioni:

1. In Adobe Analytics, seleziona **[!UICONTROL Components]** > **[!UICONTROL Locations]**, quindi seleziona la [!UICONTROL **Impostazioni di amministrazione**] scheda.

1. In [!UICONTROL **Posizioni**] , deseleziona l’opzione, [!UICONTROL **Consenti agli utenti di creare e gestire posizioni**].

1. Seleziona [!UICONTROL **Salva**].

1. (Facoltativo) Eliminare le posizioni create dagli utenti che non si desidera più utilizzare, come descritto in [Eliminare una posizione](#delete-a-location).

### Limitare i tipi di account che gli utenti possono creare e utilizzare

Puoi limitare i tipi di account visualizzati dagli utenti nelle seguenti circostanze:

* Quando [creazione di nuovi account](/help/components/locations/configure-import-accounts.md).

* Quando si sceglie quali account utilizzare per l&#39;esportazione di file tramite [Feed dati](/help/export/analytics-data-feed/create-feed.md), esportazione di report tramite [Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md), o l&#39;importazione di schemi tramite [Set di classificazione](/help/components/classifications/sets/overview.md).

Quando si limitano i tipi di account come descritto in questa sezione, tutti gli account del tipo limitato non sono più visibili agli utenti. Ciò significa che non è possibile creare nuovi account di quel tipo e che non è possibile utilizzare account esistenti di quel tipo durante la creazione di feed di dati, Date Warehouse o set di classificazione.

Tuttavia, gli account esistenti configurati per le esportazioni pianificate devono essere eliminati se si desidera impedirne l&#39;utilizzo.

#### Assicurati che gli account non vengano utilizzati per le esportazioni pianificate

Quando si limitano i tipi di conto, gli account esistenti vengono nascosti, non eliminati.

Se le pianificazioni sono già configurate per l&#39;invio di dati a un account del tipo limitato, le pianificazioni continueranno a essere eseguite anche dopo aver limitato il tipo di account e i dati continueranno a essere inviati all&#39;account.  Ad esempio, se un feed di dati è pianificato per l’invio di dati a un tipo di account limitato, la pianificazione continuerà a essere eseguita.

Se è necessario assicurarsi che i conti di un determinato tipo non vengano utilizzati nelle esportazioni programmate, è possibile eliminarli prima di [limitare i tipi di account](#limit-the-account-types-that-are-available-to-users).

Per eliminare gli account:

1. Individuare i conti del tipo di conto che si prevede di limitare e che vengono utilizzati per le esportazioni programmate.

1. Eliminare gli account come descritto in [Eliminare un account](#delete-an-account).

1. Procedi alla sezione seguente, [Limita i tipi di account disponibili per gli utenti](#limit-the-account-types-that-are-available-to-users).

#### Limita i tipi di account disponibili per gli utenti

Per limitare i tipi di account disponibili per gli utenti durante la creazione e l&#39;utilizzo degli account:

1. In Adobe Analytics, seleziona **[!UICONTROL Components]** > **[!UICONTROL Locations]**, quindi seleziona la [!UICONTROL **Impostazioni di amministrazione**] scheda.

1. Individua il [!UICONTROL **Tipi di account consentiti**] sezione.

   I seguenti tipi di account sono disponibili per impostazione predefinita per gli utenti. Deseleziona uno di questi tipi di account che desideri impedire agli utenti di utilizzare.

   * [!UICONTROL **ARN per ruolo Amazon S3**]

   * [!UICONTROL **Piattaforma Google Cloud**]

   * [!UICONTROL **SAS di Azure**]

   * [!UICONTROL **RBAC di Azure**]

   * [!UICONTROL **E-mail**]

   * Tipi di account legacy, inclusi [!UICONTROL **Amazon S3**], [!UICONTROL **Azure**], [!UICONTROL **FTP**], e [!UICONTROL **SFTP**]

1. Seleziona [!UICONTROL **Salva**].


