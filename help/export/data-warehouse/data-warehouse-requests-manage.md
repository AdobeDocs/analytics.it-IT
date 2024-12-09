---
description: Scopri come visualizzare, duplicare e ridefinire le priorità delle richieste Data Warehouse.
title: Gestire le richieste di Data Warehouse
feature: Data Warehouse
uuid: cdeb764f-56f9-43ec-9228-8ed5a2b58909
exl-id: a399d366-8402-4f4f-9b9f-14b218cd074a
source-git-commit: d929e97a9d9623a8255f16729177d812d59cec05
workflow-type: tm+mt
source-wordcount: '1148'
ht-degree: 1%

---

# Gestire le richieste di Data Warehouse

Puoi visualizzare e gestire le richieste Data Warehouse che hai effettuato. Solo gli amministratori possono visualizzare e gestire le richieste effettuate da altri utenti dell’organizzazione.

Le sezioni seguenti descrivono le attività che è possibile eseguire durante la gestione delle richieste.

## Visualizzare richieste

Per impostazione predefinita, è possibile visualizzare solo le richieste create, a meno che gli utenti non abbiano scelto di rendere le proprie richieste visibili ad altri utenti dell&#39;organizzazione (come descritto in [Data Warehouse impostazioni generali della richiesta](/help/export/data-warehouse/create-request/dw-general-settings.md)). Gli amministratori di sistema possono visualizzare tutte le richieste.

Per visualizzare le richieste Data Warehouse:

1. In Adobe Analytics, seleziona [!UICONTROL **Strumenti**] > [!UICONTROL **Data Warehouse**].

   Nella pagina Data Warehouse vengono visualizzate tutte le richieste effettuate dall&#39;utente. I dati vengono visualizzati in ogni colonna. Puoi [configurare quali colonne](#configure-columns) sono visibili.

   <!-- add screenshot of main page -->

<!-- describe columns? -->

1. (Facoltativo) Fare clic sul nome della richiesta per visualizzare una finestra di dialogo contenente le seguenti informazioni: <!-- Check this -->

   * Quando una richiesta ha iniziato l’elaborazione

   * Tariffa limitata: l’organizzazione ha troppe richieste Data Warehouse in esecuzione. La richiesta viene sospesa fino al completamento di altre richieste di dati.

## Modificare le richieste

Quando modifichi le richieste, tieni presente quanto segue:

* È possibile modificare solo le richieste configurate per l’esecuzione in una pianificazione.

* Non tutti i campi associati alla richiesta possono essere modificati. I campi che non possono essere modificati vengono oscurati.

* Gli amministratori che modificano la richiesta di un altro utente devono scegliere un nuovo account e un percorso a cui possono accedere.

Per modificare una richiesta pianificata:

1. In Adobe Analytics, seleziona [!UICONTROL **Strumenti**] > [!UICONTROL **Data Warehouse**].

1. Nella pagina Data Warehouse, seleziona la richiesta da modificare.

   ![Gestire una richiesta](assets/dw-manage-request.png)

1. Seleziona [!UICONTROL **Modifica**].

1. Modifica la richiesta come desideri. Impossibile modificare le opzioni di configurazione disattivate.

   Per informazioni su ciascuna opzione di configurazione, vedere [Creare una richiesta Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Seleziona [!UICONTROL **Salva modifiche**].

## Visualizzare la cronologia di una richiesta

Puoi visualizzare la cronologia di qualsiasi richiesta Data Warehouse effettuata.

1. In Adobe Analytics, seleziona [!UICONTROL **Strumenti**] > [!UICONTROL **Data Warehouse**].

1. Nella pagina Data Warehouse, seleziona la richiesta di cui desideri visualizzare la cronologia.

   ![Gestire una richiesta](assets/dw-manage-request.png)

1. Selezionare [!UICONTROL **Visualizza cronologia**].

   Nella pagina [!UICONTROL **Visualizza richiesta di Data Warehouse**] è visualizzato l&#39;elenco delle singole consegne di report associate alla richiesta.

   Selezionare l&#39;icona **Configura colonna** ![Configura icona colonna](assets/configure-column-icon.png) per nascondere le colonne o visualizzarne altre non visualizzate per impostazione predefinita.

   ![Pagina cronologia richieste](assets/dw-request-history.png)

   Sono disponibili le seguenti colonne:

   | Colonna | Descrizione |
   |---------|----------|
   | [!UICONTROL **Data di creazione**] | La data e l’ora di creazione del rapporto.<p>Viene visualizzato nel fuso orario dell’utente che ha avviato la richiesta.</p> |
   | [!UICONTROL **Data di inizio**] | Data e ora di inizio del report.<p>Viene visualizzato nel fuso orario dell’utente che ha avviato la richiesta.</p> |
   | [!UICONTROL **Data completata**] | La data e l’ora in cui è stato completato il rapporto.<p>Viene visualizzato nel fuso orario dell’utente che ha avviato la richiesta.</p> |
   | [!UICONTROL **Data aggiornamento**] | La data e l’ora dell’ultimo aggiornamento del rapporto.<p>Viene visualizzato nel fuso orario dell’utente che ha avviato la richiesta.</p> |
   | [!UICONTROL **Stato**] | Stato della consegna del rapporto. Gli stati possibili sono:<ul><li>[!UICONTROL **Creato**]: il report è stato creato ma non è ancora stato elaborato.</li><li>[!UICONTROL **In sospeso**]: il report è in attesa di elaborazione.</li><li>[!UICONTROL **Elaborazione**]: report in corso.</li><li>[!UICONTROL **Completato**]: report completato ed ora disponibile.</li><li>[!UICONTROL **Pianificato**]: report pianificato ma non ancora avviato.</li><li>[!UICONTROL **Annullato**]: report annullato dall&#39;utente.</li><li>[!UICONTROL **Errore - Elaborazione**:] Il report ha rilevato un errore e non è stato possibile elaborarlo.</li><li>[!UICONTROL **Errore - Impossibile inviare**]: il report è stato generato correttamente ma non è stato possibile recapitare. Controlla la [configurazione della tua destinazione](/help/export/data-warehouse/create-request/dw-request-report-destinations.md), quindi invia nuovamente il rapporto.</li></ul>. |
   | [!UICONTROL **Da**] | Data di inizio dell’intervallo di tempo complessivo incluso nel rapporto.<p>Viene visualizzato nel fuso orario della suite di rapporti.</p> |
   | [!UICONTROL **A**] | Data di fine dell’intervallo di tempo complessivo incluso nel rapporto. <p>Viene visualizzato nel fuso orario della suite di rapporti.</p> |
   | [!UICONTROL **ID richiesta legacy**] | ID utilizzato per identificare un report nell&#39;interfaccia Data Warehouse legacy. Questo ID potrebbe essere necessario quando si contatta l’Assistenza clienti di Adobe. |
   | [!UICONTROL **ID report**] | ID utilizzato per identificare un report nell&#39;interfaccia Data Warehouse corrente. Questo ID potrebbe essere necessario quando si contatta l’Assistenza clienti di Adobe. |


1. Seleziona una consegna di rapporti, quindi seleziona una delle seguenti opzioni:

   | Opzione | Funzione |
   |---------|----------|
   | [!UICONTROL **Dettagli destinazione**] | Mostra i dettagli dell’account e dell’ubicazione associati alla richiesta. Questo è l&#39;account e il percorso configurato in precedenza, come descritto in [Configurare una destinazione di report per una richiesta Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). |
   | [!UICONTROL **Annulla report**] | Annulla il report. Impossibile annullare i report con stato [!UICONTROL **Completati**] o [!UICONTROL **Annullati**]. |
   | [!UICONTROL **Esegui nuovamente il report**] | Esegue nuovamente il report con i dati così come erano quando è stato inviato originariamente. È possibile eseguire nuovamente un report con uno dei seguenti stati: [!UICONTROL **Annullato**], [!UICONTROL **Completato**], [!UICONTROL **Errore - Elaborazione**], o [!UICONTROL **Errore - Impossibile inviare**]. |
   | [!UICONTROL **Invia di nuovo il report**] | Invia nuovamente il file del report generato in precedenza. È possibile inviare nuovamente un report con uno dei seguenti stati: [!UICONTROL **Completato**] o [!UICONTROL **Errore - Impossibile inviare**]. |

## Copiare le richieste

Quando copi una richiesta, tutte le opzioni di configurazione vengono copiate dalla richiesta originale.

1. In Adobe Analytics, seleziona [!UICONTROL **Strumenti**] > [!UICONTROL **Data Warehouse**].

1. Nella pagina Data Warehouse, seleziona la richiesta da copiare.

   ![Gestire una richiesta](assets/dw-manage-request.png)

1. Seleziona [!UICONTROL **Copia**].

   Viene visualizzata la pagina Copia richiesta Data Warehouse. Tutte le opzioni di configurazione vengono copiate dalla richiesta originale.

1. Aggiorna le opzioni di configurazione associate alla richiesta.

   Per informazioni su ciascuna opzione di configurazione, vedere [Creare una richiesta Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

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

1. Seleziona l&#39;icona **Configura colonne** in alto a destra nella pagina Data Warehouse.

   ![Configura colonne](assets/dw-configure-columns.png)

   Sono disponibili le seguenti colonne:

   | Colonna disponibile | Descrizione |
   |---------|----------|
   | Nome richiesta | Nome della persona che ha creato la richiesta. |
   | Suite di rapporti | La suite di rapporti associata alla richiesta. |
   | Richiesto da | Utente che ha creato la richiesta. |
   | Data richiesta | Data in cui è stata effettuata la richiesta. |
   | Stato | Sono disponibili i seguenti stati:<ul><li><p>**Completato**: la richiesta è stata eseguita correttamente.</p></li><li><p>**Annullata**: la richiesta è stata annullata dall&#39;utente.</p></li><li><p>**Pianificato**: la richiesta è configurata per l&#39;esecuzione secondo una pianificazione.</p></li><li><p>**Non riuscito**: impossibile completare la richiesta. Se la richiesta continua a non riuscire, contatta l’Assistenza clienti.</p></li></ul> |

   {style="table-layout:auto"}

1. Assicurati che tutte le colonne che desideri visualizzare siano selezionate. Le colonne selezionate vengono visualizzate nella pagina Data Warehouse e le relative informazioni.

## Filtrare e ordinare le richieste

1. Seleziona l&#39;icona **Filtro** nella barra a sinistra della pagina Data Warehouse.

   ![Filtra richieste](assets/dw-filter.png)

1. Espandi le sezioni [!UICONTROL **Suite per report**], [!UICONTROL **Proprietario**] o [!UICONTROL **Stato**], quindi seleziona come filtrare le richieste.

## Cercare le richieste

1. Nel campo di ricerca nella parte superiore della pagina Data Warehouse, specifica il nome della richiesta da visualizzare.

   Le richieste vengono filtrate durante la digitazione.