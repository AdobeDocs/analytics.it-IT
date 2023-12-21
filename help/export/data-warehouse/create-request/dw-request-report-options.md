---
description: Passaggi che descrivono come creare una richiesta Data Warehouse.
title: Configurare le opzioni di rapporto per una richiesta Data Warehouse
feature: Data Warehouse
exl-id: b273bddb-431c-44d9-82a5-cb088829b3a3
source-git-commit: 1bd46f104c5ebcca78d624b49c56b2992c3d62cb
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 1%

---

# Configurare le opzioni di rapporto per una richiesta Data Warehouse

Durante la creazione di una richiesta Data Warehouse sono disponibili varie opzioni di configurazione. Le informazioni seguenti descrivono come configurare le opzioni di rapporto per la richiesta.

Per informazioni su come iniziare a creare una richiesta, nonché collegamenti ad altre importanti opzioni di configurazione, vedi [Creare una richiesta Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Per configurare le opzioni di report per una richiesta Data Warehouse:

1. Inizia a creare una richiesta in Adobe Analytics selezionando **[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Aggiungi**].

   Per ulteriori dettagli, vedi [Creare una richiesta Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Nella pagina Nuova richiesta Data Warehouse, seleziona la [!UICONTROL **Opzioni di report**] scheda.

   ![Scheda Destinazione rapporto](assets/dw-report-options.png) <!-- update screenshot to include Sort by metrics -->

1. Completa i campi seguenti:

   | Opzione | Funzione |
   |---------|----------|
   | [!UICONTROL **Nome file**] | Identifica il rapporto. <p>Se nel nome del file viene utilizzato uno dei seguenti caratteri speciali, la richiesta non può essere salvata: <code>! &quot; # $ &amp; &#39; ( ) * + , / : ; > = &lt; ? @ [ ] \ ^ ` { } \| ~</code> </p><p>Il carattere % può essere utilizzato solo se è seguito da &quot;R&quot;, &quot;rsid&quot; o &quot;id&quot;, come segue: <code>%R</code>, <code>%rsid</code>, e <code>%id</code>.</p> |
   | [!UICONTROL **Aggiungi intervallo di date rapporto al nome file**] | Aggiunge l’intervallo di date al nome del file del rapporto. <p>Ad esempio, se richiedi dati dal 1° maggio 2024 al 7 maggio 2024, il nome del file includerà l’intervallo di date 20240501 - 20240507.</p> |
   | [!UICONTROL **CSV**] | Fornisce rapporti in formato CSV per la visualizzazione dei dati in un foglio di calcolo. |
   | [!UICONTROL **Tableau (TDE)**] | Fornisce rapporti in formato TDE (Tableau Data Extract), che può essere utilizzato per visualizzare dati e livelli in dati aggiuntivi all’interno di Tableau. |
   | [!UICONTROL **Invia rapporto come file compresso (ZIP)**] | Fornisce rapporti in formato file compresso (ZIP). È consigliabile abilitare questa opzione quando si utilizza l’e-mail come [destinazione del rapporto](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). |
   | [!UICONTROL **Restituisci tutte le righe**] | Quando questa opzione è attivata, tutte le righe vengono incluse nel rapporto. Disattiva questa opzione per specificare il numero di righe da includere. |
   | [!UICONTROL **Inizio dei commenti del rapporto**] | Aggiungere i commenti che si desidera includere nel report. I commenti vengono visualizzati all&#39;inizio del report. |
   | [!UICONTROL **Ordinare per metriche**] | Fornisce rapporti con raggruppamenti classificati in Date Warehouse, ordinati per valore di metrica decrescente. L’ordinamento per metrica semplifica l’interpretazione dei rapporti Data Warehouse e ne agevola la comparazione con altre visualizzazioni di reporting di suddivisione di Analytics.<p>Per ulteriori informazioni, consulta [Ordina per metrica](/help/export/data-warehouse/sorting-by-metric.md).</p> |
   | [!UICONTROL **Inviare un file manifesto**] | Include i metadati sui file inclusi nel rapporto.<!-- What kind of metadata is included in the manifest file? --> |
   | [!UICONTROL **Inviare un file di firma digitale**] | Consente ai destinatari dei report di verificare che il file provenga da Adobe e che non sia stato modificato. |
   | [!UICONTROL **Invia un file vuoto se il report non contiene dati**] | Invia un report anche quando il report non contiene dati. |

   {style="table-layout:auto"}

1. Continua a configurare la richiesta Data Warehouse in [!UICONTROL **Opzioni di pianificazione**] scheda. Per ulteriori informazioni, consulta [Configurare le opzioni di pianificazione per una richiesta Data Warehouse](/help/export/data-warehouse/create-request/dw-request-scheduling.md).
