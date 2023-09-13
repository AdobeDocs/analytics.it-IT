---
description: Passaggi che descrivono come creare una richiesta Data Warehouse.
title: Data Warehouse impostazioni generali della richiesta
feature: Data Warehouse
source-git-commit: c63e5d5f1065aabdbbd5471d6a2e702f9f099396
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 3%

---

# Data Warehouse impostazioni generali della richiesta

{{release-limited-testing}}

Durante la creazione di una richiesta Data Warehouse sono disponibili varie opzioni di configurazione. Le informazioni seguenti descrivono come configurare le impostazioni generali per la richiesta.

Per informazioni su come iniziare a creare una richiesta, nonché collegamenti ad altre importanti opzioni di configurazione, vedi [Creare una richiesta Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Per configurare le impostazioni generali per una richiesta Data Warehouse:

1. Inizia a creare una richiesta Data Warehouse in Adobe Analytics selezionando **[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Aggiungi**].

   Per ulteriori dettagli, vedi [Creare una richiesta Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Nella pagina Nuova richiesta Data Warehouse, seleziona la [!UICONTROL **Impostazioni generali**] scheda.

   ![Scheda Destinazione rapporto](assets/dw-general-settings.png)

1. Completa i campi seguenti:

   | Opzione | Funzione |
   |---------|----------|
   | Nome richiesta | Questo nome viene visualizzato nella pagina della Data Warehouse principale durante la gestione delle richieste. |
   | Intervalli di date | Seleziona l’intervallo di date da includere nel rapporto. <p>Puoi scegliere date personalizzate o un intervallo di date predefinito. Gli intervalli di predefiniti sono relativi alla data di invio del rapporto.</p><p>Sono disponibili le seguenti opzioni predefinite:</p><ul><li>Oggi</li><li>Ieri</li><li>Ultimi 7 giorni</li><li>Ultimi 30 giorni</li><li>Questa settimana</li><li>Ultima settimana</li><li>Ultime 2 settimane</li><li>Ultime 3 settimane</li><li>Ultime 4 settimane</li><li>Questo mese</li><li>Ultimo mese</li><li>Ultima ora</li><li>Oggi</li><li>Oggi</li></ul> |
   | Granularità | <!--what does this setting do? It's not the schedule/frequency... --> Granularità temporale. I valori validi sono Nessuno, Ora, Giorno, Settimana, Mese, Trimestre e Anno.<p>La granularità del reporting richiede un tempo di elaborazione aggiuntivo. Se generi rapporti con granularità mensile per un intero anno, l’elaborazione dei rapporti sarà molto più rapida se invii una richiesta di rapporto per ogni mese.</p> |

   {style="table-layout:auto"}

1. Continua a configurare la richiesta Data Warehouse in [!UICONTROL **Creare il rapporto**] scheda. Per ulteriori informazioni, consulta [Creare un rapporto per una richiesta Data Warehouse](/help/export/data-warehouse/create-request/dw-request-build-report.md).