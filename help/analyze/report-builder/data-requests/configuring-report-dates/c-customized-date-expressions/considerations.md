---
description: 'Due importanti considerazioni quando si utilizza Personalizza espressione per impostare l’intervallo di date '
title: Considerazioni sulle date personalizzate
uuid: a3bb3a63-0f15-4292-ade7-4ea852fe68c8
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 0%

---


# Considerazioni sulle date personalizzate

Due importanti considerazioni quando si utilizza Personalizza espressione per impostare l’intervallo di date:

* Il giorno in cui viene eseguito il rapporto (A partire da) (o le richieste aggiornate) determina i dati disponibili.
* Il rollover delle date di inizio e di fine del rapporto influisce sull’intervallo di date coperto dal rapporto.

Poiché la disponibilità dei dati è sensibile sia all’intervallo di tempo del rapporto che alla data in cui aggiorni le richieste nel rapporto, assicurati di eseguire il rapporto il giorno appropriato per estrarre le informazioni desiderate. Gli esempi seguenti illustrano entrambe queste considerazioni.

Supponiamo di effettuare una richiesta per [!UICONTROL Page Views] utilizzando la granularità aggregata. In Nord America la settimana inizia la domenica. Per ottenere rapporti aggiornati per il periodo da domenica a sabato (ad esempio, dal 23 novembre al 29 novembre 2008), esegui il rapporto (richieste di aggiornamento) domenica (30 novembre) per la settimana precedente (dal 23/11/29).

Utilizzare questa espressione personalizzata:

*Da:* cw-1w  *a:* cw-1d

Un&#39;analisi dell&#39;espressione Customize quando il valore [!UICONTROL End Date] incluso per la richiesta è 11/30:

*Da:* cw-1w

il giorno della settimana corrente a partire da domenica 30 novembre meno sette giorni = il giorno della settimana precedente a partire da domenica 23 novembre

*A:* cw-1d

il giorno della settimana corrente a partire da domenica 30 novembre meno un giorno = sabato 29 novembre

Dopo aver mappato l’espressione personalizzata sul foglio di calcolo, aggiorna la richiesta utilizzando domenica 30 novembre 2008 come elemento [!UICONTROL End Date] inclusivo per la richiesta mobile. I dati riflettono il periodo di una settimana.

Se invece aggiorni l’espressione e specifichi sabato 29 novembre come [!UICONTROL End Date] per la richiesta mobile, i dati riflettono la settimana dal 16/11/22. Questo perché la data di riferimento per l’aggiornamento della richiesta è un giorno precedente.

Di seguito sono riportate le differenze quando il [!UICONTROL End Date] inclusivo per la richiesta è il 29/11:

*Da:* cw-1w

il giorno della settimana corrente a partire da domenica 23 novembre meno sette giorni = il giorno della settimana precedente a partire da domenica 16 novembre

*A:* cw-1d

il giorno della settimana corrente a partire da domenica 23 novembre meno un giorno = sabato 22 novembre

In Europa e in altri paesi la settimana inizia il lunedì, non la domenica. In questo caso, puoi personalizzare il calendario per modificare la data di inizio. (Vedere [Calendario personalizzato](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md).)
