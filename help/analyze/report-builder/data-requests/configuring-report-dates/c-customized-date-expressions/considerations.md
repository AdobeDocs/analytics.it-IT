---
description: 'Due considerazioni importanti quando si utilizza Personalizza espressione per impostare l''intervallo di date '
solution: Analytics
title: Considerazioni sulle date personalizzate
topic: Report builder
uuid: a3bb3a63-0f15-4292-ade7-4ea852fe68c8
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Considerazioni sulle date personalizzate

Due considerazioni importanti quando si utilizza Personalizza espressione per impostare l'intervallo di date:

* Il giorno in cui viene eseguito il rapporto (A partire da) (o le richieste aggiornate) determina i dati disponibili.
* Il rollover delle date di inizio e di fine del rapporto influenza l'intervallo di date coperto dal rapporto.

Poiché la disponibilità dei dati è sensibile sia all'intervallo di tempo del rapporto che alla data in cui aggiornate le richieste nel rapporto, accertati di eseguire il rapporto il giorno appropriato per estrarre le informazioni desiderate. Gli esempi seguenti illustrano entrambe queste considerazioni.

Si supponga di effettuare una richiesta per [!UICONTROL Page Views] l’utilizzo della granularità aggregata. In Nord America, la settimana inizia la domenica. Per ottenere rapporti aggiornati per il periodo da domenica a sabato (ad esempio, dal 23 novembre al 29 novembre 2008), esegui il rapporto (richieste di aggiornamento) domenica (30 novembre) per la settimana precedente (dal 23/11/29).

Utilizzate questa espressione personalizzata:

***Da: cw-1w* To: cw-1d

Un'analisi dell'espressione di personalizzazione quando il valore incluso [!UICONTROL End Date] per la richiesta è 11/30:

** Da: cw-1w

il giorno della settimana corrente a partire da domenica, 30 novembre meno 7 giorni = il giorno della settimana precedente a partire da domenica, 23 novembre

** A: cw-1d

il giorno della settimana corrente a partire da domenica, 30 novembre meno un giorno = sabato, 29 novembre

Dopo che l'espressione personalizzata è stata mappata sul foglio di calcolo, aggiornate la richiesta utilizzando Domenica 30 novembre 2008 come elemento incluso [!UICONTROL End Date] per la richiesta mobile. I dati rifletteranno il periodo della settimana.

Se invece aggiornate l'espressione e specificate sabato 29 novembre come [!UICONTROL End Date] richiesta mobile, i dati rifletteranno la settimana 11/16-11/22. Questo perché la data di riferimento per l'aggiornamento della richiesta è un giorno precedente.

Di seguito sono riportate le differenze quando l'inclusione [!UICONTROL End Date] per la richiesta è 11/29:

** Da: cw-1w

il giorno della settimana corrente a partire da domenica, 23 novembre meno sette giorni = il giorno della settimana precedente a partire da domenica, 16 novembre

** A: cw-1d

il giorno della settimana corrente a partire da domenica, 23 novembre meno un giorno = sabato, 22 novembre

In Europa e in altri paesi, la settimana inizia il lunedì, anziché la domenica. In questo caso, potete personalizzare il calendario per modificare la data di inizio. (Vedere Calendario [](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md)personalizzato.)
