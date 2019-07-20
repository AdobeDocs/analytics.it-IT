---
description: Dopo aver eseguito un rapporto, puoi personalizzare il rapporto per visualizzare e analizzare i dati in base alle tue esigenze. Potete filtrare i dati del rapporto, cambiare il modo in cui i dati vengono presentati graficamente, modificare la granularità data e così via.
seo-description: Dopo aver eseguito un rapporto, puoi personalizzare il rapporto per visualizzare e analizzare i dati in base alle tue esigenze. Potete filtrare i dati del rapporto, cambiare il modo in cui i dati vengono presentati graficamente, modificare la granularità data e così via.
seo-title: Personalizzazione dei rapporti
solution: Analytics
title: Personalizzazione dei rapporti
topic: Reports & Analytics
uuid: 37 d 221 b 7-50 fd -4425-b 2 ba-f 40911 b 72 a 2 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Personalizzazione dei rapporti

Dopo aver eseguito un rapporto, puoi personalizzare il rapporto per visualizzare e analizzare i dati in base alle tue esigenze. Potete filtrare i dati del rapporto, cambiare il modo in cui i dati vengono presentati graficamente, modificare la granularità data e così via.

## Create a custom report {#task_BA6EACA3039C40AEA5605E1D8C76E646}

Procedura che descrive come salvare la configurazione corrente di un report come nuovo rapporto personalizzato per tutti gli utenti.

<!-- 

t_reports_custom.xml

 -->

Solo gli amministratori possono creare un rapporto personalizzato. Quando create un rapporto personalizzato, viene aggiunto al menu principale di reporting accanto al report su cui si basa.

**Creazione di un rapporto personalizzato**

1. Eseguite un rapporto e configuratelo come necessario.
1. Click **[!UICONTROL More]** &gt; **[!UICONTROL Create Custom Report]**.
1. Name the report, then click **[!UICONTROL Save.]**

   Verificate di non duplicare un nome di rapporto esistente.

>[!MORE_ LIKE_ THIS]
>
>* [Personalizzazione del menu](https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=customize_menus)


## Select a date or date range {#task_9BEF7D4D839A4748B76E8500D1406C34}

I passaggi che descrivono l'attivazione possono scegliere i periodi di tempo per i dati del rapporto.

<!-- 

t_reports_select_date.xml

 -->

Puoi selezionare giorni, settimane, mesi o anni specifici. Puoi anche eseguire rapporti di confronto.

Quando apri un dashboard con i minirapporti con intervalli di date diversi, puoi scegliere un nuovo intervallo di date nel calendario. Le modifiche vengono applicate a tutti i minirapporti nel dashboard.

**Per selezionare un intervallo di date**

1. Esegui un report.
1. Fai clic sull'icona Calendario in alto a destra.
1. Selezionate una data.

   Puoi:

   * Visualizza giorni, mesi o periodi di anno (fino a tre).
   * Trascina il cursore tra le date per selezionare un intervallo.
   * Immettete le date manualmente.
   * Fate clic sul nome di un mese per selezionare un mese.
   * Click **[!UICONTROL Select Preset]** to select a preset date.
   * Confronta date.

1. Fai clic su **[!UICONTROL Run Report]**.

## Compare dates {#task_95155C3700774B709F5FB81AE96B0824}

Procedura che descrive come utilizzare il calendario per eseguire confronti di date tra i report classifica.

<!-- 

t_reports_comparing_dates.xml

 -->

Non è possibile confrontare date tra i report con tendenze.

>[!NOTE]
>
>If you want to perform a date comparison on key metrics in a dashboard, you can pull the data into [Report Builder](https://marketing.adobe.com/resources/help/en_US/arb/) using two separate requests. In Excel potrete quindi usare formule personalizzate per analizzare la differenza tra i due.

Per confrontare le date tra rapporti classifica in Reporting e analisi:

1. Esegui un report.
1. Fai clic sul calendario in alto a destra.
1. Fai clic su **[!UICONTROL Compare Dates]**.
1. Selezionate le date da utilizzare.
1. Fai clic su **[!UICONTROL Run Report]**.

## Display a percent as a graph {#task_BC28CA19A4834AF6BFE68B5B5AEFE75D}

Procedura che descrive come visualizzare la percentuale in una tabella di rapporti come grafico.

<!-- 

t_reports_graph_percent.xml

 -->

Questa visualizzazione è disponibile anche nei minirapporti dashboard.

1. Run a report that supports percentages, such as a [!UICONTROL Pages Report].
1. Fai clic su **[!UICONTROL Percent Shown As: Graph]**.

## Normalize report data {#task_8005B55E59BD479DA67BC618FF8BC94A}

Procedura che descrive come normalizzare i dati del rapporto.

<!-- 

t_reports_normalize.xml

 -->

Dopo aver eseguito un rapporto con date confrontate, o per confronti A/B, puoi normalizzare i dati per mostrare la percentuale di modifica tra i rapporti. Il set di dati secondari viene regolato per compensare le differenze nel numero di giorni selezionati o per diversi volumi di traffico.

**Normalizzazione dei dati del rapporto**

1. Eseguire un report che supporta confronti di date.
1. Click **[!UICONTROL Compare Dates]**, then specify your date comparison.
1. Fai clic su **[!UICONTROL Run Report]**.
1. Fai clic su **[!UICONTROL Normalize Data: Yes]**.

## Select a page for a report {#task_5CAC3B76BD4C4208B8D53DD972D4771F}

Procedura che descrive come selezionare una pagina specifica dalle pagine del sito Web per un rapporto.

<!-- 

t_reports_select_page.xml

 -->

1. Generate a report, such as a [!UICONTROL Page Views Report] ( **[!UICONTROL Reports]** &gt; **[!UICONTROL Site Metrics]** &gt; **[!UICONTROL Page Views]**).
1. Click the **[!UICONTROL Selected Page]** link.
1. On [!UICONTROL Choose Page], select the pages you want to display.
1. Individuare la pagina.
1. Fai clic su **[!UICONTROL OK.]**

## Compare report suites {#task_6BEBEB2D4F36497C9DA5B18ADAD35546}

Procedura che descrive come visualizzare i rapporti da due suite di rapporti nello stesso rapporto.

<!-- 

t_reports_compare_suites.xml

 -->

Oltre alla visualizzazione grafica, la tabella del rapporto fornisce un confronto percentuale. I report seguenti possono essere eseguiti con confronti:

* Contenuto del sito
* Dispositivi mobili
* Origini del traffico
* Campagne
* Variabile  
* Conservazione dei visitatori
* Profilo visitatore
* Conversione personalizzata
* Traffico personalizzato
* Target
* Sondaggio

**Per confrontare le suite di rapporti**

1. Generare un report che consente di confrontare i rapporti.
1. Click the **[!UICONTROL Compare to Site]** link.
1. Individuate la suite di rapporti.
1. Fai clic su **[!UICONTROL OK.]**

## Specify report granularity {#task_7ED3EEC9E1704A918B25D06ADA3412E0}

Procedura che descrive come visualizzare i totali del report su base giornaliera, giornaliera, settimanale, trimestrale, trimestrale o annuale.

<!-- 

t_reports_granularity.xml

 -->

Il periodo di tempo del report determina quali opzioni di granularità sono disponibili. For example, you can select only **[!UICONTROL Hourly]** if you have a one or two day time frame selected. You can select only **[!UICONTROL Yearly]** granularity if you have more than one year selected.

**Per specificare la granularità dei report**

1. Generate a trended report, such as **[!UICONTROL Site Content]** &gt; **[!UICONTROL Pages.]**
1. Click the **[!UICONTROL View by]** link, then click a granularity.

## Run a day-of-week report {#task_67CC818ACC3749839B69BDB2ED9AE6B8}

Procedura che descrive come eseguire i rapporti su un giorno specifico della settimana, ad esempio su ogni lunedì in un dato intervallo di date.

<!-- 

t_reports_day_of_week.xml

 -->

Questa funzione si applica solo ai report con tendenze filtrati con un intervallo di date Settimana o Giorno.

1. Esegui un rapporto con tendenze su un intervallo date specificato.
1. Click the **[!UICONTROL Day of Week]** link, then click a day.

## 'Try in Workspace' button {#concept_DA41E22460B94BD9ADF63B1CEE2714A7}

Clicking the **[!UICONTROL Try In Workspace]** button at the top of a report will load the same report in Analysis Workspace.

<!-- 

try_in_workspace.xml

 -->

La maggior parte dei rapporti in Reporting e analisi ora include un pulsante «Prova in Workspace» per riprodurre la visualizzazione corrente in Analysis Workspace per personalizzare ulteriormente.

Al momento, il pulsante è disponibile solo se il nome utente ha tutti i diritti per Analysis Workspace.

For more information on all the ways you can customize your report, see the [Analysis Workspace](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/) guide.
