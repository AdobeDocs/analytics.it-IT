---
title: Occorrenza in arrivo
description: Scopri in che modo i feed di dati gestiscono gli hit in arrivo ritardati.
translation-type: tm+mt
source-git-commit: 7db88bce7b3d0f90fa5b50664d7c0c23904348c0

---


# Occorrenza in arrivo

I dati storici possono arrivare dopo che un processo di feed di dati ha terminato l&#39;elaborazione per una data ora o giorno, ad esempio tramite hit con marca temporale o origini dati. Gli hit in arrivo ritardati sono un’impostazione di personalizzazione back-end fornita da Adobe per facilitare l’inclusione di questi dati nei feed di dati.

## Funzionamento degli hit in arrivo

Quando un feed di dati elabora normalmente i dati, guarda solo i dati all&#39;interno della relativa finestra di reporting (in genere l&#39;ora o il giorno più recenti). Se i dati arrivano dopo che un feed ha completato l&#39;elaborazione di quella finestra di reporting, tali dati non vengono mai inclusi in alcun feed di dati.

Se gli hit di arrivo ritardati sono abilitati, il metodo di elaborazione cambia per includere questi dati. Ogni volta che un feed di dati elabora i dati, controlla tutti gli hit tardivi che sono arrivati e li mette in batch nel file di feed di dati successivo inviato al tuo sito FTP.

## Abilitazione degli hit in arrivo ritardati

Gli hit in ritardo possono essere attivati manualmente da Adobe sui singoli feed di dati. Prima di eseguire questa operazione, tenere presente quanto segue:

* I dati relativi a giorni diversi vengono visualizzati frequentemente nei feed di dati quando gli hit in arrivo ritardato sono attivati. Accertatevi che la piattaforma utilizzata per assimilare i feed di dati possa contenere dati provenienti da giorni diversi all&#39;interno dello stesso file.
* Gli hit in arrivo aumentano il tempo di elaborazione. In genere questo ritardo è inferiore all’ora, ma può essere di diverse ore o più se la suite di rapporti riceve un gran numero di hit di arrivo in ritardo. Adobe consiglia di non attivare questa impostazione se l&#39;arrivo tempestivo dei feed di dati è un fattore fondamentale per il flusso di lavoro dell&#39;organizzazione.
* Se un file di feed di dati viene rielaborato, gli hit in arrivo ritardati inclusi nel file originale non vengono inclusi nel file rielaborato.

Per abilitare gli hit di arrivo ritardato per un feed di dati ricorrente esistente, contatta l’Assistenza clienti e includi quanto segue:

* Nota che si desidera abilitare gli hit di arrivo in ritardo per un feed di dati specifico
* ID suite di rapporti
* Nome feed dati
