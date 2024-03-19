---
description: Data warehouse rimanda alla copia dei dati di Analytics per l’archiviazione e i rapporti personalizzati, che puoi eseguire filtrando i dati. È possibile richiedere rapporti per visualizzare relazioni avanzate tra i dati, da dati non elaborati in base a domande specifiche. I rapporti data warehouse vengono inviati tramite e-mail o a un provider di archiviazione cloud e la loro elaborazione può richiedere fino a 72 ore. Il tempo di elaborazione dipende dalla complessità della query e dalla quantità di dati richiesti.
title: Panoramica di Data Warehouse
feature: Data Warehouse
uuid: 768557dd-1644-4ce6-bfc2-8c46dd6e1cd1
exl-id: 6a051d53-397b-4a55-9cca-1c83b31c9448
source-git-commit: 3af2cca02675e424b3f704a95d46de92886a88d8
workflow-type: ht
source-wordcount: '351'
ht-degree: 100%

---

# Panoramica di Data Warehouse

Data warehouse consente di copiare i dati di Adobe Analytics per l’archiviazione e per la creazione di rapporti personalizzati, che si possono eseguire filtrando i dati.

## Panoramica sui rapporti

I rapporti di Data Warehouse possono visualizzare relazioni avanzate tra dati da dati non elaborati in base a domande specifiche. Possono includere un numero illimitato di righe in un’unica richiesta (per singoli rapporti pianificati e scaricati).

>[!NOTE]
>
>Data warehouse riporta il primo valore rilevato nel periodo di reporting.

>[!IMPORTANT]
>
>Durante la segmentazione di valori classificati, Analysis Workspace e Data Warehouse trattano i valori “non specificati” in modo diverso. “Non specificato” in Workspace fa riferimento a valori non classificati, mentre “Non specificato” in Data Warehouse fa riferimento a valori che hai classificato come “Non specificato”.

## Panoramica della consegna

I rapporti Data Warehouse vengono inviati tramite e-mail o a un provider di archiviazione cloud e la loro elaborazione può richiedere fino a 72 ore. Il tempo di elaborazione dipende dalla complessità della query e dalla quantità di dati richiesti.

Data warehouse comprime automaticamente qualsiasi file di dimensioni superiori a 1 MB. La dimensione massima dell’allegato e-mail è 10 MB.

## Accesso

Adobe abilita Data Warehouse solo per gli utenti a livello di amministratore, per suite di rapporti specifiche. (Può essere abilitato per le suite di rapporti globali e secondarie, ma non per le suite di rapporti di aggregazione dati.) L’amministratore può creare un gruppo con accesso a Data Warehouse e quindi associare al gruppo utenti non amministratori.

Consulta [Gestire le autorizzazioni di Data Warehouse](/help/export/data-warehouse/t-dw-group.md).

## Creare una richiesta di Data Warehouse

Per informazioni sulla creazione di una richiesta di Data Warehouse, consulta [Creare una richiesta di Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

## Gestire le richieste di Data Warehouse

Per informazioni su come gestire le richieste di Data Warehouse, consulta [Gestire le richieste di Data Warehouse](/help/export/data-warehouse/data-warehouse-requests-manage.md).

## Domande frequenti

Per un elenco delle domande frequenti, consulta [Domande frequenti relativa a Data Warehouse](/help/export/data-warehouse/faq.md).