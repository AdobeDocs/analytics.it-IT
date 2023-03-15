---
title: Occorrenza in arrivo
description: Scopri come i feed di dati trattano gli hit in arrivo tardivo.
feature: Data Feeds
exl-id: c99a702b-2aaa-47a6-958a-1e5ab66961ba
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 1%

---

# Occorrenza in arrivo

I dati storici possono arrivare dopo che un processo di feed dati termina l’elaborazione per una determinata ora o giorno, ad esempio tramite hit con marca temporale o origini dati. Gli hit in arrivo tardivo sono un’impostazione di personalizzazione del back-end fornita da Adobe per includere tali dati nei feed di dati.

## Funzionamento degli hit in arrivo

Quando un feed di dati elabora normalmente i dati, esamina solo i dati all’interno dell’intervallo di reporting (in genere l’ora o il giorno più recenti). Se i dati arrivano dopo che un feed ha completato l’elaborazione di tale intervallo di reporting, tali dati non vengono mai inclusi in alcun feed di dati.

Con l’abilitazione degli hit in arrivo tardivo, il metodo di elaborazione cambia per includere questi dati. Ogni volta che un feed di dati elabora i dati, esamina tutti gli hit in ritardo che sono arrivati e li batch nel file di feed di dati successivo inviato al sito FTP.

## Abilitazione degli hit in arrivo ritardato

Gli hit in arrivo con ritardo possono essere abilitati manualmente da Adobe sui singoli feed di dati. Prima di procedere, considera quanto segue:

* I dati per giorni diversi vengono spesso visualizzati nei feed di dati quando sono abilitati gli hit in ritardo. Assicurati che la piattaforma utilizzata per acquisire i feed di dati possa contenere dati di giorni diversi all’interno dello stesso file.
* Gli hit in arrivo tardi aumentano il tempo di elaborazione. In genere questo ritardo è inferiore alle ore, ma può essere di diverse ore o più se la suite di rapporti riceve un numero elevato di hit in arrivo tardivo. L’Adobe consiglia di non abilitare questa impostazione se l’arrivo tempestivo dei feed di dati è fondamentale per il flusso di lavoro della tua organizzazione.
* Se un file di feed dati viene rielaborato, gli hit in arrivo in ritardo inclusi nel file originale non vengono inclusi nel file rielaborato.

Se desideri abilitare gli hit in arrivo ritardato per un feed di dati ricorrente esistente, rivolgiti a un contatto utente supportato all’Assistenza clienti e includi quanto segue:

* Una nota che desideri abilitare gli hit in arrivo tardivo per un feed di dati specifico
* ID suite di rapporti
* Nome feed dati
