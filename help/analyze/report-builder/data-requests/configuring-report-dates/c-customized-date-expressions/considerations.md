---
description: 'Due considerazioni importanti quando si usa l''espressione Personalizza per impostare l''intervallo di date '
seo-description: 'Due considerazioni importanti quando si usa l''espressione Personalizza per impostare l''intervallo di date '
seo-title: Considerazioni
solution: Analytics
title: Considerazioni sulle date personalizzate
topic: Generatore di report
uuid: a 3 bb 3 a 63-0 f 15-4292-ade 7-4 ea 852 fe 68 c 8
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Considerazioni sulle date personalizzate

Due considerazioni importanti quando si usa l'espressione Personalizza per impostare l'intervallo di date:

* Il giorno in cui viene eseguito il rapporto (con le richieste) determina quali dati sono disponibili.
* Il rollover delle date di inizio e di fine del report incide sull'intervallo di date coperto dal report.

Poiché la disponibilità dei dati è sensibile sia all'intervallo temporale del rapporto che alla data in cui aggiornate le richieste nel rapporto, assicuratevi di eseguire il rapporto nel giorno appropriato per estrarre le informazioni desiderate. Gli esempi seguenti illustrano entrambe queste considerazioni.

Assume you make a request for [!UICONTROL Page Views] using Aggregated granularity. In America del Nord, la settimana inizia domenica. Per ottenere rapporti aggiornati per il periodo da domenica a sabato (ad esempio, dal 23 novembre al 29 novembre 2008), esegui il rapporto (richiesta di aggiornamento) domenica (30 novembre) per la settimana precedente (da 11/23 a 11/29).

Utilizzate questa espressione personalizzata:

*Da:* cw -1 w *to:* cw -1 d

An analysis of the customize expression when the inclusive [!UICONTROL End Date] for the request is 11/30:

*Da:* cw -1 w

il giorno della settimana corrente a domenica, novembre 30 meno sette giorni = giorno della settimana scorsa a partire domenica, novembre 23

*Per:* cw -1 d

il giorno della settimana corrente a domenica, novembre 30 meno un giorno = sabato, novembre 29

After the customized expression is mapped to the spreadsheet, refresh the request using Sunday, November 30, 2008 as the inclusive [!UICONTROL End Date] for the floating request. I dati riflettono il periodo di tempo lungo.

If instead you refresh the expression and specify Saturday, November 29 as the [!UICONTROL End Date] for the floating request, the data will reflect the week 11/16 to 11/22. poiché la data di riferimento per l'aggiornamento della richiesta è un giorno precedente.

Here are the differences when the inclusive [!UICONTROL End Date] for the request is 11/29:

*Da:* cw -1 w

il giorno della settimana corrente a domenica, novembre 23 meno sette giorni = giorno della settimana scorsa a partire domenica, novembre 16

*Per:* cw -1 d

il giorno della settimana corrente a domenica, novembre 23 meno un giorno = sabato, novembre 22

In Europa e in altri Paesi, la settimana inizia lunedì, anziché domenica. In questo caso, potete personalizzare il calendario per modificare la data di inizio. (See [Custom Calendar](../../../../../analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md#concept_4342A844600048759EEDABD164AC3F5A).)
