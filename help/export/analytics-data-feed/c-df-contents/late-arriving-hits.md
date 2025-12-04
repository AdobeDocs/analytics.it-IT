---
title: Occorrenza in arrivo
description: Scopri come i feed di dati trattano gli hit in arrivo tardivo.
feature: Data Feeds
exl-id: c99a702b-2aaa-47a6-958a-1e5ab66961ba
source-git-commit: 5816868d3899d2938330471d1e59757141b16c69
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 2%

---

# Occorrenza in arrivo {#late-arriving-hits}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datafeed_late_hits"
>title="Consenti hit in arrivo"
>abstract="Seleziona questa opzione per includere i dati arrivati dopo che il processo di feed dati ha completato l’elaborazione dei dati all’interno della frequenza di reporting impostata (giornaliera, oraria o ogni 15 minuti). Con questa opzione abilitata, ogni volta che un feed di dati elabora i dati, esamina eventuali hit in ritardo arrivati e li inserisce in batch con il successivo file di feed di dati inviato."

<!-- markdownlint-enable MD034 -->

I dati storici possono arrivare dopo che un processo di feed dati termina l’elaborazione per una determinata ora o giorno, ad esempio tramite hit con marca temporale o origini dati. Gli hit in arrivo tardivo sono un’impostazione di personalizzazione del back-end fornita da Adobe per facilitare l’inclusione di questi dati nei feed di dati.

## Funzionamento degli hit in arrivo

Quando un feed di dati elabora normalmente i dati, esamina solo i dati all’interno dell’intervallo di reporting (in genere l’ora o il giorno più recenti). Se i dati arrivano dopo che un feed ha completato l’elaborazione di tale intervallo di reporting, tali dati non vengono mai inclusi in alcun feed di dati.

Con l’abilitazione degli hit in arrivo tardivo, il metodo di elaborazione cambia per includere questi dati. Ogni volta che un feed di dati elabora i dati, esamina tutti gli hit in ritardo che sono arrivati e li batch nel file di feed di dati successivo inviato al sito FTP.

## Abilitazione degli hit in arrivo ritardato

Gli hit in arrivo possono essere abilitati manualmente da Adobe sui singoli feed di dati. Prima di procedere, considera quanto segue:

* I dati per giorni diversi vengono spesso visualizzati nei feed di dati quando sono abilitati gli hit in ritardo. Assicurati che la piattaforma utilizzata per acquisire i feed di dati possa contenere dati di giorni diversi all’interno dello stesso file.
* Se un file di feed dati viene rielaborato, gli hit in arrivo in ritardo inclusi nel file originale vengono inclusi nel file rielaborato quando la rielaborazione avviene entro i primi 5 giorni. Dopo 5 giorni, gli hit in arrivo tardivo non sono inclusi nel file rielaborato.

Se desideri abilitare gli hit in arrivo ritardato per un feed di dati ricorrente esistente, rivolgiti a un contatto utente supportato all’Assistenza clienti e includi quanto segue:

* Una nota che desideri abilitare gli hit in arrivo tardivo per un feed di dati specifico
* ID suite di rapporti
* Nome feed dati
