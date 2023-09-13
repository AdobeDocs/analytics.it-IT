---
description: Data warehouse rimanda alla copia dei dati di Analytics per l’archiviazione e i rapporti personalizzati, che puoi eseguire filtrando i dati. È possibile richiedere rapporti per visualizzare relazioni avanzate tra i dati, da dati non elaborati in base a domande specifiche. I rapporti data warehouse vengono inviati tramite e-mail o a un provider di archiviazione cloud e l’elaborazione può richiedere fino a 72 ore. Il tempo di elaborazione dipende dalla complessità della query e dalla quantità di dati richiesti.
title: Panoramica di Data Warehouse
feature: Data Warehouse
uuid: 768557dd-1644-4ce6-bfc2-8c46dd6e1cd1
exl-id: 6a051d53-397b-4a55-9cca-1c83b31c9448
source-git-commit: 3af2cca02675e424b3f704a95d46de92886a88d8
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 25%

---

# Panoramica di Data Warehouse

Data Warehouse consente di copiare i dati di Adobe Analytics per l’archiviazione e per la creazione di rapporti personalizzati, che possono essere eseguiti filtrando i dati.

## Panoramica sui report

I report Data Warehouse possono visualizzare relazioni avanzate tra i dati, da dati non elaborati in base a domande specifiche. Possono includere un numero illimitato di righe in una singola richiesta (per rapporti singoli, pianificati e scaricati).

>[!NOTE]
>
>Data Warehouse riporta il primo valore rilevato nel periodo di reporting.

>[!IMPORTANT]
>
>Quando si segmentano valori classificati, Analysis Workspace e Data Warehouse trattano i valori &quot;non specificati&quot; in modo diverso. &#39;Non specificato&#39; in Workspace fa riferimento a valori non classificati, mentre &#39;Non specificato&#39; nella Data Warehouse fa riferimento a valori classificati come &quot;Non specificato&quot;.

## Panoramica della consegna

I report Data Warehouse vengono inviati tramite e-mail o a un provider di archiviazione cloud e l’elaborazione può richiedere fino a 72 ore. Il tempo di elaborazione dipende dalla complessità della query e dalla quantità di dati richiesti.

Data Warehouse comprime automaticamente qualsiasi file di dimensioni superiori a 1 MB. La dimensione massima dell&#39;allegato e-mail è 10 MB.

## Accedere ad

L’Adobe abilita Data Warehouse solo per gli utenti a livello di amministratore, per suite di rapporti specifiche. Può essere abilitata per le suite di rapporti globali e secondarie, ma non per le suite di rapporti di aggregazione dati. L&#39;amministratore può creare un gruppo con accesso a Data Warehouse e quindi associare al gruppo utenti non amministratori.

Consulta [Gestire le autorizzazioni Data Warehouse](/help/export/data-warehouse/t-dw-group.md).

## Create a Data Warehouse Request (Creare una richiesta di archivio dati)

Per informazioni sulla creazione di una richiesta Data Warehouse, consulta [Creare una richiesta Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

## Gestire le richieste di Data Warehouse

Per informazioni su come gestire le richieste Data Warehouse, consulta [Gestire le richieste Data Warehouse](/help/export/data-warehouse/data-warehouse-requests-manage.md).

## Domande frequenti

Per un elenco delle domande frequenti, consulta [DATA WAREHOUSE DOMANDE FREQUENTI](/help/export/data-warehouse/faq.md).