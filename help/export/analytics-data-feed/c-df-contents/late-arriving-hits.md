---
title: Hit in arrivo
description: Scopri come i feed di dati trattano gli hit in arrivo tardivo.
feature: Data Feeds
exl-id: c99a702b-2aaa-47a6-958a-1e5ab66961ba
source-git-commit: 4d0007d1a23a81f0d5ba60541b4f7b9ac7b00ace
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 0%

---

# Occorrenza in arrivo {#late-arriving-hits}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datafeed_late_hits"
>title="Consenti hit in arrivo"
>abstract="Seleziona questa opzione per includere i dati ricevuti dopo il completamento dell’elaborazione dei dati da parte del processo di feed dati all’interno della frequenza di reporting impostata (in genere giornaliera o oraria). Con questa opzione abilitata, ogni volta che un feed di dati elabora i dati, esamina eventuali hit in ritardo arrivati e li inserisce in batch con il successivo file di feed di dati inviato."

<!-- markdownlint-enable MD034 -->

## Comprendere gli hit in arrivo

I dati storici possono arrivare dopo che un processo di feed dati termina l’elaborazione per una determinata ora o giorno, ad esempio tramite hit con marca temporale o origini dati.

Quando un feed di dati elabora normalmente i dati, esamina solo i dati all’interno dell’intervallo di reporting (in genere l’ora o il giorno più recenti). Se i dati arrivano dopo che un feed ha completato l’elaborazione di tale intervallo di reporting, tali dati non vengono mai inclusi in alcun feed di dati.

Se sono abilitati gli hit in arrivo, il metodo di elaborazione cambia per includere questi dati. Ogni volta che un feed di dati elabora i dati, esamina tutti gli hit in ritardo che sono arrivati e li batch nel successivo file di feed di dati inviato.

## Abilita hit in arrivo

Prima di abilitare l’opzione per consentire hit in ritardo per un feed di dati, considera quanto segue:

* I dati per giorni diversi vengono spesso visualizzati nei feed di dati quando sono abilitati gli hit in ritardo. Assicurati che la piattaforma utilizzata per acquisire i feed di dati possa contenere dati di giorni diversi all’interno dello stesso file.
* Se un file di feed dati viene rielaborato, gli hit in ritardo che erano inclusi nel file originale vengono inclusi nel file rielaborato quando la rielaborazione avviene entro i primi 5 giorni. Dopo 5 giorni, gli hit in arrivo tardivo non sono inclusi nel file rielaborato.

È possibile abilitare gli hit in ritardo durante la creazione o la modifica di un feed di dati abilitando l&#39;opzione **[!UICONTROL Allow late-arriving hits]**, come descritto in [Creare un feed di dati](/help/export/analytics-data-feed/create-feed.md).
