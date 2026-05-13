---
description: Due considerazioni importanti sull’utilizzo dell’espressione Personalizza per impostare l’intervallo di date
title: Considerazioni sulle date personalizzate
uuid: a3bb3a63-0f15-4292-ade7-4ea852fe68c8
feature: Report Builder
role: User, Admin
exl-id: 66b817b3-7e9e-4030-92f3-797e730f9661
TQID: https://experienceleague.adobe.com/7PLNffmZnNnQ2X0HgnqYa8R3zWQvFPMSM8sbWocmxH4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 405
ht-degree: 0%

---

# Considerazioni sulle date personalizzate

{{legacy-arb}}

Due considerazioni importanti sull’utilizzo dell’espressione Personalizza per impostare l’intervallo di date:

* Il giorno in cui il rapporto (A partire da) viene eseguito (o le richieste vengono aggiornate) determina quali dati sono disponibili.
* Il rollover delle date di inizio e di fine del rapporto influisce sull’intervallo di date coperto dal rapporto.

Poiché la disponibilità dei dati è sensibile sia all’intervallo di tempo del rapporto che alla data di aggiornamento delle richieste nel rapporto, assicurati di eseguire il rapporto nel giorno appropriato per estrarre le informazioni desiderate. Gli esempi che seguono dimostrano entrambe queste considerazioni.

Si supponga di effettuare una richiesta per [!UICONTROL Page Views] utilizzando la granularità aggregata. In Nord America, la settimana inizia la domenica. Per ottenere rapporti aggiornati per il periodo da domenica a sabato (ad esempio, dal 23 novembre al 29 novembre 2008), esegui il rapporto (richieste di aggiornamento) domenica 30 novembre per la settimana precedente (dal 23 novembre all’11/29).

Usa questa espressione personalizzata:

*Da:* cw-1w *A:* cw-1d

Un&#39;analisi dell&#39;espressione di personalizzazione quando il [!UICONTROL End Date] incluso per la richiesta è 11/30:

*Da:* cw-1w

il giorno della settimana corrente che inizia domenica 30 novembre meno sette giorni = il giorno della settimana precedente che inizia domenica 23 novembre

*A:* cw-1d

il giorno della settimana corrente a partire da domenica 30 novembre meno un giorno = sabato 29 novembre

Dopo aver mappato l&#39;espressione personalizzata sul foglio di calcolo, aggiornare la richiesta utilizzando domenica 30 novembre 2008 come [!UICONTROL End Date] inclusi per la richiesta mobile. I dati rifletteranno il periodo di una settimana.

Se invece aggiorni l’espressione e specifichi sabato 29 novembre come [!UICONTROL End Date] per la richiesta mobile, i dati rifletteranno le settimane dal 11/16 all’11/22. Questo perché la data di riferimento per l’aggiornamento della richiesta è un giorno prima.

Di seguito sono riportate le differenze quando [!UICONTROL End Date] inclusi per la richiesta è 11/29:

*Da:* cw-1w

il giorno della settimana corrente che inizia domenica 23 novembre meno sette giorni = il giorno della settimana precedente che inizia domenica 16 novembre

*A:* cw-1d

il giorno della settimana corrente a partire da domenica 23 novembre meno un giorno = sabato 22 novembre

In Europa e in altri paesi, la settimana inizia lunedì, anziché domenica. In questo caso, è possibile personalizzare il calendario per modificare la data di inizio. (Vedi [Calendario personalizzato](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/custom-calendar.md).)
