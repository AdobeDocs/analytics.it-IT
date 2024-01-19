---
description: Dopo aver eseguito un rapporto, puoi personalizzarlo per visualizzare e analizzare i dati in base alle tue esigenze. Puoi filtrare i dati dei rapporti, modificare il modo in cui i dati vengono presentati graficamente, cambiare la granularità delle date e così via.
title: Panoramica della personalizzazione dei rapporti
uuid: 37d221b7-50fd-4425-b2ba-f40911b72a2f
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 5a042fac-926e-4560-83bf-11f66ddb8273
source-git-commit: a2e69b5f39de3c964381bb5dd5ecd4d9714e9249
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 78%

---

# Personalizzare i rapporti

Dopo aver eseguito un rapporto, puoi personalizzarlo per visualizzare e analizzare i dati in base alle tue esigenze. Puoi filtrare i dati dei rapporti, modificare il modo in cui i dati vengono presentati graficamente, cambiare la granularità delle date e così via.

## Seleziona una data o un intervallo di date {#task_9BEF7D4D839A4748B76E8500D1406C34}

È possibile scegliere i periodi di tempo per i dati del rapporto.

<!-- 

t_reports_select_date.xml

 -->

Puoi selezionare giorni, settimane, mesi o anni specifici. È inoltre possibile eseguire rapporti di confronto.

Quando apri una dashboard contenente reportlet che hanno intervalli di date diversi, puoi scegliere un nuovo intervallo di date nel calendario. Le modifiche vengono applicate a tutti i reportlet nella dashboard.

Per selezionare un intervallo di date:

1. Esegui un rapporto.
1. Fai clic sull’icona del calendario in alto a destra.
1. Seleziona una data.

   È possibile:

   * Visualizzare giorni, mesi o periodi di anno (fino a tre)
   * Trascinare il cursore su più date per selezionare un intervallo
   * Immettere le date manualmente
   * Fare clic sul nome di un mese per selezionarlo
   * Fare clic su **[!UICONTROL Select Preset]** per selezionare una data predefinita
   * Confrontare più date

1. Fai clic su **[!UICONTROL Run Report]**.

## Confrontare più date {#task_95155C3700774B709F5FB81AE96B0824}

È possibile utilizzare il calendario per eseguire confronti di date tra rapporti classificati.

<!-- 

t_reports_comparing_dates.xml

 -->

Non è possibile confrontare date tra rapporti con tendenze.

>[!NOTE]
>
>Se desideri confrontare le metriche chiave di una dashboard per date diverse, puoi richiamare i dati in [Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html?lang=it) utilizzando due richieste separate. In seguito, puoi utilizzare formule personalizzate in Excel per analizzare la differenza tra i due set di dati.

<!-- delete this procedure, but what about this entire "Compare dates" section?

To compare dates between ranked reports in Reports & analytics: 

1. Run a report.
1. Click the calendar at the top right.
1. Click **[!UICONTROL Compare Dates]**.
1. Select the dates you want to use.
1. Click **[!UICONTROL Run Report]**.

-->

## Visualizzare i valori percentuali sotto forma di grafico {#task_BC28CA19A4834AF6BFE68B5B5AEFE75D}

È possibile specificare se visualizzare come grafico la percentuale in una tabella di rapporto.

<!-- 

t_reports_graph_percent.xml

 -->

Questa visualizzazione è disponibile anche nei reportlet delle dashboard.

Per visualizzare la percentuale sotto forma di grafico in una tabella di rapporto:

1. Esegui un rapporto che supporta i valori percentuali, ad esempio [!UICONTROL Pages Report].
1. Fai clic su **[!UICONTROL Percent Shown As: Graph]**.

## Normalizzare i dati del rapporto {#task_8005B55E59BD479DA67BC618FF8BC94A}

<!-- 

t_reports_normalize.xml

 -->

Dopo aver eseguito un rapporto con date confrontate o per confronti A/B, puoi normalizzare i dati per mostrare la percentuale di variazione tra i rapporti. Il set di dati secondari viene regolato per compensare le differenze nel numero di giorni selezionati o per diversi volumi di traffico.

Per normalizzare i dati del rapporto:

1. Esegui un rapporto che supporta i confronti tra date.
1. Fai clic su **[!UICONTROL Compare Dates]**, quindi specifica il confronto tra date.
1. Fai clic su **[!UICONTROL Run Report]**.
1. Fai clic su **[!UICONTROL Normalize Data: Yes]** (Crea set di dati da schema).

## Seleziona una pagina per un rapporto {#task_5CAC3B76BD4C4208B8D53DD972D4771F}

Per selezionare una pagina specifica dalle pagine del sito Web per un rapporto:

<!-- 

t_reports_select_page.xml

 -->

1. Genera un rapporto, ad esempio un [!UICONTROL Page Views Report] ( **[!UICONTROL Reports]** > **[!UICONTROL Site Metrics]** > **[!UICONTROL Page Views]**).
1. Fai clic sul collegamento **[!UICONTROL Selected Page]**
1. In [!UICONTROL Choose Page], seleziona le pagine che desideri visualizzare.
1. Individua la pagina.
1. Fai clic su **[!UICONTROL OK.]**

## Confronta le suite di rapporti {#task_6BEBEB2D4F36497C9DA5B18ADAD35546}

Puoi visualizzare i rapporti di due suite di rapporti nello stesso rapporto.

<!-- 

t_reports_compare_suites.xml

 -->

Oltre alla visualizzazione grafica, la tabella del rapporto fornisce un confronto in percentuale. I seguenti rapporti possono essere eseguiti con confronti:

* Contenuto del sito
* Mobile
* Origini di traffico
* Campagne
* Prodotti
* Conservazione dei visitatori
* Profilo visitatore
* Conversione personalizzata
* Traffico personalizzato
* Target
* Sondaggio

Per confrontare le suite di rapporti:

1. Genera un rapporto che ti consente di confrontare i rapporti.
1. Fai clic sul collegamento **[!UICONTROL Compare to Site]**
1. Individua la suite di rapporti.
1. Fai clic su **[!UICONTROL OK.]**

## Specifica la granularità del rapporto {#task_7ED3EEC9E1704A918B25D06ADA3412E0}

Puoi visualizzare i totali dei rapporti su base oraria, giornaliera, settimanale, mensile, trimestrale o annuale.

<!-- 

t_reports_granularity.xml

 -->

Il periodo di tempo del rapporto determina quali opzioni di granularità sono disponibili. Ad esempio, puoi selezionare **[!UICONTROL Hourly]** solo se è stato selezionato un arco temporale di uno o due giorni. Puoi selezionare solo granularità **[!UICONTROL Yearly]** se è stato selezionato più di un anno.

Per specificare la granularità del rapporto:

1. Genera un rapporto con tendenze, ad esempio **[!UICONTROL Site Content]** > **[!UICONTROL Pages.]**
1. Fai clic sul collegamento **[!UICONTROL View by]**, quindi fai clic su una granularità.

## Esegui un rapporto in base al giorno della settimana {#task_67CC818ACC3749839B69BDB2ED9AE6B8}

È possibile eseguire rapporti in un giorno specifico della settimana, ad esempio ogni lunedì in un determinato intervallo di date.

<!-- 

t_reports_day_of_week.xml

 -->

Questa funzione si applica solo ai rapporti con tendenze filtrati con un intervallo di date di Settimana o Giorno.

Per eseguire un rapporto in base al giorno della settimana:

1. Esegui un rapporto con tendenze su un intervallo di date specificato.
1. Fai clic sul collegamento **[!UICONTROL Day of Week]**, quindi fai clic su un giorno.
