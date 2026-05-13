---
description: Passaggi che descrivono come creare una richiesta di Data Warehouse.
title: Configurare le opzioni di rapporto per una richiesta Data Warehouse
feature: Data Warehouse
exl-id: b273bddb-431c-44d9-82a5-cb088829b3a3
TQID: https://experienceleague.adobe.com/WngJlzAVsWsC9dzQ2Dg-78FqUjXxkU9SUnJVzhFECXs
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 451
ht-degree: 16%

---

# Configurare le opzioni di rapporto per una richiesta Data Warehouse

Durante la creazione di una richiesta di Data Warehouse, sono disponibili varie opzioni di configurazione. Le informazioni seguenti descrivono come configurare le opzioni di rapporto per la richiesta.

Per informazioni su come iniziare a creare una richiesta, nonché collegamenti ad altre importanti opzioni di configurazione, consulta [Creare una richiesta di Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Per configurare le opzioni di report per una richiesta Data Warehouse:

1. Se non l’hai ancora fatto, inizia a creare una richiesta in Adobe Analytics selezionando **[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **Aggiungi**].

   Per ulteriori dettagli, consulta [Creare una richiesta di Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Nella pagina Nuova richiesta Data Warehouse, seleziona la scheda [!UICONTROL **Opzioni report**].

   ![Scheda destinazione report](assets/dw-report-options.png) <!-- update screenshot to include Sort by metrics -->

1. Completa i campi seguenti:

   | Opzione | Funzione |
   |---------|----------|
   | [!UICONTROL **Nome file**] | Identifica il rapporto. <p>Impossibile salvare la richiesta se nel nome file viene utilizzato uno dei seguenti caratteri speciali: <code>! &quot; # $ &amp; &#39; ( ) * + , / : ; > = &lt; ? @ [ ] \ ^ ` { } \| ~</code> </p><p>Il carattere % può essere utilizzato solo se è seguito da &quot;R&quot;, &quot;rsid&quot; o &quot;id&quot;, come segue: <code>%R</code>, <code>%rsid</code>, e <code>%id</code>.</p> |
   | [!UICONTROL **Aggiungi intervallo di date del report al nome file**] | Aggiunge l’intervallo di date al nome del file del rapporto. <p>Ad esempio, se richiedi dati dal 1° maggio 2024 al 7 maggio 2024, il nome del file includerà l’intervallo di date 20240501 - 20240507.</p> |
   | [!UICONTROL **CSV**] | Fornisce rapporti in formato CSV per la visualizzazione dei dati in un foglio di calcolo. |
   | [!UICONTROL **Tableau (TDE)**] | Fornisce rapporti in formato TDE (Tableau Data Extract), che può essere utilizzato per visualizzare dati e livelli in dati aggiuntivi all’interno di Tableau. |
   | [!UICONTROL **Invia report come file compresso (ZIP)**] | Fornisce rapporti in formato file compresso (ZIP). È consigliabile abilitare questa opzione quando si utilizza la posta elettronica come [destinazione report](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). |
   | [!UICONTROL **Restituisci tutte le righe**] | Quando questa opzione è attivata, tutte le righe vengono incluse nel rapporto. Disattiva questa opzione per specificare il numero di righe da includere. |
   | [!UICONTROL **Inizio dei commenti del report**] | Aggiungere i commenti che si desidera includere nel report. I commenti vengono visualizzati all&#39;inizio del report. |
   | [!UICONTROL **Ordina per metriche**] | Fornisce rapporti con raggruppamenti classificati in Data Warehouse, ordinati per valore di metrica decrescente. L’ordinamento per metrica semplifica l’interpretazione dei rapporti di Data Warehouse e il confronto con altre visualizzazioni di rapporti di suddivisione di Analytics.<p>Per ulteriori informazioni, vedere [Ordinare per metrica](/help/export/data-warehouse/sorting-by-metric.md).</p> |
   | [!UICONTROL **Invia un file manifesto**] | Include metadati sui file inclusi nel report.<!-- What kind of metadata is included in the manifest file? --> |
   | [!UICONTROL **Invia un file di firma digitale**] | Consente ai destinatari dei rapporti di verificare che il file provenga da Adobe e che non sia stato modificato. |
   | [!UICONTROL **Invia un file vuoto quando non sono presenti dati nel report**] | Invia un report anche quando il report non contiene dati. |

   {style="table-layout:auto"}

1. Continua a configurare la richiesta Data Warehouse nella scheda [!UICONTROL **Opzioni di pianificazione**]. Per ulteriori informazioni, vedere [Configurare le opzioni di pianificazione per una richiesta Data Warehouse](/help/export/data-warehouse/create-request/dw-request-scheduling.md).
