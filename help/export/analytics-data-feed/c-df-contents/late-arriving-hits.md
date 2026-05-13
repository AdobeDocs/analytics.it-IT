---
title: Hit in arrivo
description: Scopri come i feed di dati trattano gli hit in arrivo tardivo.
feature: Data Feeds
exl-id: c99a702b-2aaa-47a6-958a-1e5ab66961ba
TQID: https://experienceleague.adobe.com/eNLHiK8xI-O-E7UDfIkxEfFB0oAQoum6lTXH7OFQJ3c
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 313
ht-degree: 20%

---

# Occorrenza in arrivo {#late-arriving-hits}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datafeed_late_hits"
>title="Consenti hit con arrivo in ritardo"
>abstract="Seleziona questa opzione per includere i dati arrivati dopo il completamento dell’elaborazione dei dati da parte del processo di feed dati, entro la frequenza di reporting impostata (in genere giornaliera o oraria). Quando questa opzione è abilitata, ogni volta che un feed di dati elabora i dati, eventuali hit arrivati in ritardo vengono individuati e quindi inseriti in batch nel prossimo file di feed dati che viene inviato."

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
