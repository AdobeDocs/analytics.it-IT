---
title: Occorrenza in arrivo
description: Scopri in che modo i feed di dati gestiscono gli hit in arrivo.
feature: Data Feeds
exl-id: c99a702b-2aaa-47a6-958a-1e5ab66961ba
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 1%

---

# Occorrenza in arrivo

I dati storici possono arrivare al termine dell’elaborazione di un processo di feed di dati per una data ora o giorno, ad esempio tramite hit con marca temporale o origini dati. Gli hit in ritardo sono un’impostazione di personalizzazione back-end fornita da Adobe per facilitare l’inclusione di tali dati nei feed di dati.

## Funzionamento degli hit in arrivo

Quando un feed di dati elabora normalmente i dati, esamina solo i dati all’interno del relativo intervallo di reporting (in genere l’ora o il giorno più recenti). Se i dati arrivano dopo che un feed ha completato l’elaborazione di tale intervallo di reporting, tali dati non vengono mai inclusi in alcun feed di dati.

Se gli hit in arrivo sono abilitati, il metodo di elaborazione cambia per includere questi dati. Ogni volta che un feed di dati elabora i dati, esamina tutti gli hit in ritardo arrivati e li invia in batch nel file di feed di dati successivo inviato al tuo sito FTP.

## Abilitazione degli hit in arrivo

Gli hit in ritardo possono essere attivati manualmente da un Adobe sui singoli feed di dati. Prima di eseguire questa operazione, considera quanto segue:

* I dati per giorni diversi vengono spesso visualizzati nei feed di dati quando gli hit in arrivo sono abilitati. Assicurati che la piattaforma utilizzata per acquisire i feed di dati possa contenere dati di giorni diversi all’interno dello stesso file.
* Gli hit in ritardo aumentano il tempo di elaborazione. In genere questo ritardo è inferiore all’ora, ma può essere di diverse ore o più se la suite di rapporti riceve un gran numero di hit in arrivo in ritardo. L’Adobe consiglia di non abilitare questa impostazione se l’arrivo tempestivo dei feed di dati è fondamentale per il flusso di lavoro della tua organizzazione.
* Se un file di feed di dati viene rielaborato, gli hit in arrivo ritardati inclusi nel file originale non vengono inclusi nel file rielaborato.

Se desideri abilitare gli hit in arrivo per un feed di dati ricorrente esistente, contatta l’Assistenza clienti e includi quanto segue:

* Nota che desideri abilitare gli hit in arrivo per un feed di dati specifico
* ID suite di rapporti
* Nome feed dati
