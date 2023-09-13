---
description: La gestione richieste consente di visualizzare, duplicare e ridefinire le priorità delle richieste.
title: Gestire le richieste di Data Warehouse
feature: Data Warehouse
uuid: cdeb764f-56f9-43ec-9228-8ed5a2b58909
exl-id: a399d366-8402-4f4f-9b9f-14b218cd074a
source-git-commit: 8507ce3f7e4d09956ad88c2be5335b68c8e3b8a0
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 4%

---

# Gestire le richieste di Data Warehouse

{{release-limited-testing}}

>[!NOTE]
>
>Se la tua organizzazione non dispone ancora della nuova esperienza Data Warehouse, che sarà presto disponibile per tutti i clienti, utilizza le informazioni in [Gestire le richieste Data Warehouse (vecchia esperienza)](#manage-data-warehouse-requests-old-experience)


Puoi gestire le richieste Data Warehouse che hai effettuato. Le sezioni seguenti descrivono le attività che è possibile eseguire durante la gestione delle richieste. <!-- just those you have made? I think you can see other people's requests (you can filter by them). What can you do with other people's requests? Just view them?-->

## Visualizzare richieste

1. In Adobe Analytics, seleziona [!UICONTROL **Strumenti**] > [!UICONTROL **Data Warehouse**].

   Nella pagina Data Warehouse vengono visualizzate tutte le richieste effettuate. <!-- just those you have made? -->I dati vengono visualizzati in ogni colonna. È possibile [configurare le colonne](#configure-columns) sono visibili.

   <!-- add screenshot of main page -->

<!-- describe columns? -->

1. (Facoltativo) Fai clic sul nome della richiesta per visualizzare una finestra di dialogo contenente le seguenti informazioni: <!-- Check this -->

   * Quando una richiesta ha iniziato l’elaborazione

   * Tariffa limitata: l’organizzazione ha troppe richieste Data Warehouse in esecuzione. La richiesta viene sospesa fino al completamento di altre richieste di dati.

## Modificare le richieste

Quando modifichi le richieste, tieni presente quanto segue:

* È possibile modificare solo le richieste configurate per l’esecuzione in una pianificazione.

* Non tutti i campi associati alla richiesta possono essere modificati. I campi che non possono essere modificati vengono oscurati.

Per modificare una richiesta pianificata:

1. In Adobe Analytics, seleziona [!UICONTROL **Strumenti**] > [!UICONTROL **Data Warehouse**].

1. Nella pagina Data Warehouse, seleziona la richiesta da modificare.

   ![Gestire una richiesta](assets/dw-manage-request.png)

1. Seleziona [!UICONTROL **Modifica**].

1. Modifica la richiesta come desideri. Impossibile modificare le opzioni di configurazione disattivate.

   Per informazioni su ciascuna opzione di configurazione, vedi [Creare una richiesta Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Seleziona [!UICONTROL **Salva modifiche**].

## Visualizzare la cronologia di una richiesta

Puoi visualizzare la cronologia di qualsiasi rapporto eseguito.

1. In Adobe Analytics, seleziona [!UICONTROL **Strumenti**] > [!UICONTROL **Data Warehouse**].

1. Nella pagina Data Warehouse, seleziona la richiesta di cui desideri visualizzare la cronologia.

   ![Gestire una richiesta](assets/dw-manage-request.png)

1. Seleziona [!UICONTROL **Visualizza cronologia**].

## Copiare le richieste

Quando copi una richiesta, tutte le opzioni di configurazione vengono copiate dalla richiesta originale.

1. In Adobe Analytics, seleziona [!UICONTROL **Strumenti**] > [!UICONTROL **Data Warehouse**].

1. Nella pagina Data Warehouse, seleziona la richiesta da copiare.

   ![Gestire una richiesta](assets/dw-manage-request.png)

1. Seleziona [!UICONTROL **Copia**].

   Viene visualizzata la pagina Copia richiesta Data Warehouse. Tutte le opzioni di configurazione vengono copiate dalla richiesta originale.

1. Aggiorna le opzioni di configurazione associate alla richiesta.

   Per informazioni su ciascuna opzione di configurazione, vedi [Creare una richiesta Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Seleziona [!UICONTROL **Salva modifiche**].

## Annulla richieste

È possibile annullare solo le richieste configurate per l’esecuzione secondo una pianificazione.

Per annullare una richiesta pianificata:

1. In Adobe Analytics, seleziona [!UICONTROL **Strumenti**] > [!UICONTROL **Data Warehouse**].

1. Nella pagina Data Warehouse, seleziona la richiesta da modificare.

   ![Gestire una richiesta](assets/dw-manage-request.png)

1. Seleziona [!UICONTROL **Annulla**].

   La richiesta non verrà più eseguita all&#39;ora pianificata.

## Configurare le colonne

Puoi configurare le informazioni visualizzate per ogni richiesta aggiungendo o rimuovendo colonne.

1. Seleziona la **Configurare le colonne** in alto a destra nella pagina Data Warehouse.

   ![Configurare le colonne](assets/dw-configure-columns.png)

   Sono disponibili le seguenti colonne:

   | Colonna disponibile | Descrizione |
   |---------|----------|
   | Nome richiesta | Nome della persona che ha creato la richiesta. |
   | Suite di rapporti | La suite di rapporti associata alla richiesta. |
   | Richiesto da | Utente che ha creato la richiesta. |
   | Data richiesta | Data in cui è stata effettuata la richiesta. |
   | Stato | Sono disponibili i seguenti stati:<ul><li><p>**Completato**: richiesta eseguita correttamente.</p></li><li><p>**Annullato**: la richiesta è stata annullata dall’utente.</p></li><li><p>**Pianificato**: la richiesta è configurata per l’esecuzione su una pianificazione.</p></li><!-- Are there other statuses? Failed? --> |

   {style="table-layout:auto"}

1. Assicurati che tutte le colonne che desideri visualizzare siano selezionate. Le colonne selezionate vengono visualizzate nella pagina Data Warehouse e le relative informazioni.

## Filtrare e ordinare le richieste

1. Seleziona la **Filtro** nella barra a sinistra della pagina Data Warehouse.

   ![Filtrare richieste](assets/dw-filter.png)

1. Espandi [!UICONTROL **Suite di rapporti**], [!UICONTROL **Proprietario**], o [!UICONTROL **Stato**] , quindi seleziona come filtrare le richieste.

## Cercare le richieste

1. Nel campo di ricerca nella parte superiore della pagina Data Warehouse, specifica il nome della richiesta da visualizzare.

   Le richieste vengono filtrate durante la digitazione.

## Gestire le richieste Data Warehouse (vecchia esperienza)

>[!NOTE]
>
>Le informazioni seguenti si applicano solo se l’organizzazione non dispone ancora della nuova esperienza Data Warehouse, che sarà presto disponibile per tutti i clienti Analytics.


La gestione richieste consente di visualizzare, duplicare e ridefinire le priorità delle richieste.

In Data Warehouse, seleziona la **[!UICONTROL Request Manager]** scheda.

Questa scheda consente di:

* Visualizza le richieste di rapporti recenti per nome rapporto, segmento applicato, richiedente, data richiesta e stato.
* Richieste duplicate. Clic **[!UICONTROL Duplicate]** accanto alla richiesta.

  >[!NOTE]
  >
  >Questa azione duplica solo la richiesta, non la pianificazione o i dettagli di consegna.

* Cerca i report per nome report o per nome di accesso del richiedente.
* Riassegna la priorità ai rapporti trascinandoli e rilasciandoli in una nuova posizione all’interno della coda.
* Per vedere quando ha iniziato l’elaborazione di una richiesta, fai clic su un ID di richiesta pianificato ed esamina il pop-up che si apre.

Fai clic su un processo per visualizzarne le singole richieste.

* Tariffa limitata: l’organizzazione ha troppe richieste Data Warehouse in esecuzione. La richiesta viene sospesa fino al completamento di altre richieste di dati.