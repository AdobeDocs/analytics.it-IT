---
description: Passaggi che descrivono come creare una richiesta di Data Warehouse.
title: Data Warehouse impostazioni generali della richiesta
feature: Data Warehouse
exl-id: f564d5a9-78a2-431e-987a-78c4b0b9d31e
source-git-commit: 1e1a26b8595ca026fb049322125a6f91d9d5513c
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 16%

---

# Data Warehouse impostazioni generali della richiesta

Durante la creazione di una richiesta di Data Warehouse, sono disponibili varie opzioni di configurazione. Le informazioni seguenti descrivono come configurare le impostazioni generali per la richiesta.

Per informazioni su come iniziare a creare una richiesta, nonché collegamenti ad altre importanti opzioni di configurazione, consulta [Creare una richiesta di Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Per configurare le impostazioni generali per una richiesta Data Warehouse:

1. Inizia a creare una richiesta Data Warehouse in Adobe Analytics selezionando **[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Aggiungi**].

   Per ulteriori dettagli, consulta [Creare una richiesta di Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Nella pagina Nuova richiesta Data Warehouse selezionare la scheda [!UICONTROL **Impostazioni generali**].

   ![Scheda Destinazione rapporto](assets/dw-general-settings.png)

1. Completa i campi seguenti:

   | Opzione | Funzione |
   |---------|----------|
   | Nome richiesta | Questo nome viene visualizzato nella pagina della Data Warehouse principale durante la gestione delle richieste. |
   | Intervalli di date | Seleziona l’intervallo di date da includere nel rapporto. <p>Puoi scegliere date personalizzate o un intervallo di date predefinito. Gli intervalli di predefiniti sono relativi alla data di invio del rapporto.</p><p>Sono disponibili le seguenti opzioni predefinite:</p><ul><li>Oggi</li><li>Ieri</li><li>Ultimi 7 giorni</li><li>Ultimi 30 giorni</li><li>Questa settimana</li><li>Ultima settimana</li><li>Ultime 2 settimane</li><li>Ultime 3 settimane</li><li>Ultime 4 settimane</li><li>Questo mese</li><li>Ultimo mese</li><li>Ultima ora</li></ul> |
   | Granularità | Granularità temporale. I valori validi sono Nessuno, Ora, Giorno, Settimana, Mese, Trimestre e Anno.<p>La granularità del reporting richiede un tempo di elaborazione aggiuntivo. Se generi rapporti con granularità mensile per un intero anno, l’elaborazione dei rapporti sarà molto più rapida se invii una richiesta di rapporto per ogni mese.</p><p>**Nota:** quando si applica la granularità in una richiesta Data Warehouse, la colonna &quot;Data&quot; viene aggiunta al report. A seconda della granularità selezionata, il formato della data cambia come segue:</p><ul><li>**Granularità oraria**:<ul> <li>**Formato**: `mmmm d, yyyy` Ora `H`</li><li>**Esempio**: 1 gennaio, 20XX, ora 0 </li></ul><li>**Granularità giornaliera**:<ul> <li>**Formato**: `mmmm d, yyyy`</li><li>**Esempio**: 1 gennaio 20XX</li></ul><li>**Granularità settimanale**:<ul> <li>**Formato**: Settimana `w, yyyy`</li><li>**Esempio**: settimana 1, 20XX </li></ul><li>**Granularità mensile**:<ul> <li>**Formato**: `mmmm yyyy`</li><li>**Esempio**: 20XX gennaio </li></ul><li>**Granularità trimestrale**:<ul> <li>**Formato**: `q` Trimestre `yyyy`</li><li>**Esempio**: 1° trimestre 20XX </li></ul><li>**Granularità annuale**:<ul> <li>**Formato**: `yyyy`</li><li>**Esempio**: 20XX</li></ul> |
   | Rendi disponibile agli utenti della tua organizzazione | Tutte le richieste di data warehouse sono visibili solo a te e agli amministratori di sistema. Abilita questa opzione se desideri che la richiesta sia visibile a tutti gli utenti dell’organizzazione. <p>L’abilitazione di questa opzione è utile se desideri che altri utenti dell’organizzazione contribuiscano a creare o aggiornare la richiesta.</p> |

   {style="table-layout:auto"}

1. Continua a configurare la tua richiesta Data Warehouse nella scheda [!UICONTROL **Genera il tuo report**]. Per ulteriori informazioni, vedere [Generare un report per una richiesta Data Warehouse](/help/export/data-warehouse/create-request/dw-request-build-report.md).
