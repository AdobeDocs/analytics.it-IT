---
description: Dopo aver eseguito un rapporto, puoi personalizzare il rapporto per visualizzare e analizzare i dati in base alle tue esigenze. Potete filtrare i dati del rapporto, modificare il modo in cui i dati vengono presentati graficamente, modificare la granularità della data e così via.
title: Panoramica della personalizzazione dei rapporti
topic: Reports and analytics
uuid: 37d221b7-50fd-4425-b2ba-f40911b72a2f
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '871'
ht-degree: 6%

---


# Panoramica della personalizzazione dei rapporti

Dopo aver eseguito un rapporto, puoi personalizzare il rapporto per visualizzare e analizzare i dati in base alle tue esigenze. Potete filtrare i dati del rapporto, modificare il modo in cui i dati vengono presentati graficamente, modificare la granularità della data e così via.

## Create a custom report {#task_BA6EACA3039C40AEA5605E1D8C76E646}

Passaggi che descrivono come salvare la configurazione corrente di un rapporto come nuovo rapporto personalizzato da visualizzare a tutti gli utenti.

<!-- 

t_reports_custom.xml

 -->

Solo gli amministratori possono creare un rapporto personalizzato. Quando create un rapporto personalizzato, questo viene aggiunto al menu principale accanto al rapporto su cui si basa.

**Creazione di un rapporto personalizzato**

1. Eseguire un rapporto e configurarlo come necessario.
1. Fai clic su **[!UICONTROL More]** > **[!UICONTROL Create Custom Report]**.
1. Denominate il rapporto, quindi fate clic su **[!UICONTROL Save.]**

   Assicurati di non duplicare un nome di rapporto esistente.

>[!MORELIKETHIS]
>
>* [Personalizzazione del menu](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/customize-menus.html)


## Selezionare un intervallo di date o date {#task_9BEF7D4D839A4748B76E8500D1406C34}

I passaggi che descrivono hot per utilizzare scelgono i periodi di tempo per i dati del report.

<!-- 

t_reports_select_date.xml

 -->

Potete selezionare giorni, settimane, mesi o anni specifici. È inoltre possibile eseguire rapporti di confronto.

Quando apri una dashboard con minirapporti con intervalli di date diversi, puoi scegliere un nuovo intervallo di date nel calendario. Le modifiche vengono applicate a tutti i minirapporti del dashboard.

**Selezione di un intervallo di date**

1. Esegui un report.
1. Fate clic sull&#39;icona del calendario in alto a destra.
1. Selezionare una data.

   È possibile:

   * Visualizza giorni, mesi o periodi di anno (fino a tre).
   * Trascina il cursore sulle date per selezionare un intervallo.
   * Immettete manualmente le date.
   * Fate clic sul nome di un mese per selezionare un mese.
   * Fate clic **[!UICONTROL Select Preset]** per selezionare una data preimpostata.
   * Confronta le date.

1. Fai clic su **[!UICONTROL Run Report]**.

## Confronta date {#task_95155C3700774B709F5FB81AE96B0824}

Passaggi che descrivono come utilizzare il calendario per eseguire confronti di date tra rapporti classifica.

<!-- 

t_reports_comparing_dates.xml

 -->

Non è possibile confrontare le date tra i report con tendenze.

>[!NOTE]
>
>Se desiderate eseguire un confronto delle date sulle metriche chiave in una dashboard, potete inserire i dati nel Generatore [di](https://docs.adobe.com/content/help/it-IT/analytics/analyze/report-builder/home.html) report utilizzando due richieste separate. Quindi si utilizzano formule personalizzate in Excel per analizzare la differenza tra le due.

Per confrontare le date tra i report classifica in Reporting e analisi:

1. Esegui un report.
1. Fare clic sul calendario in alto a destra.
1. Fai clic su **[!UICONTROL Compare Dates]**.
1. Selezionare le date che si desidera utilizzare.
1. Fai clic su **[!UICONTROL Run Report]**.

## Visualizza una percentuale come grafico {#task_BC28CA19A4834AF6BFE68B5B5AEFE75D}

Passaggi che descrivono come specificare se visualizzare la percentuale in una tabella di report come grafico.

<!-- 

t_reports_graph_percent.xml

 -->

Questa visualizzazione è disponibile anche nei minirapporti della dashboard.

1. Eseguire un rapporto che supporti le percentuali, ad esempio un [!UICONTROL Pages Report].
1. Fai clic su **[!UICONTROL Percent Shown As: Graph]**.

## Normalizza i dati del report {#task_8005B55E59BD479DA67BC618FF8BC94A}

Passaggi che descrivono come normalizzare i dati del rapporto.

<!-- 

t_reports_normalize.xml

 -->

Dopo aver eseguito un rapporto con date confrontate, o per confronti A/B, è possibile normalizzare i dati per mostrare la percentuale di modifiche tra i rapporti. Il set di dati secondario viene modificato per compensare le differenze nel numero di giorni selezionati o per diversi volumi di traffico.

**Per normalizzare i dati del report**

1. Eseguire un report che supporti i confronti delle date.
1. Fai clic **[!UICONTROL Compare Dates]**, quindi specifica il confronto tra le date.
1. Fai clic su **[!UICONTROL Run Report]**.
1. Fai clic su **[!UICONTROL Normalize Data: Yes]**.

## Selezionare una pagina per un rapporto {#task_5CAC3B76BD4C4208B8D53DD972D4771F}

Procedura che descrive come selezionare una pagina specifica dalle pagine del sito Web per un rapporto.

<!-- 

t_reports_select_page.xml

 -->

1. Generate un rapporto, ad esempio [!UICONTROL Page Views Report] ( **[!UICONTROL Reports]** > **[!UICONTROL Site Metrics]** > **[!UICONTROL Page Views]**).
1. Fate clic sul **[!UICONTROL Selected Page]** collegamento.
1. In [!UICONTROL Choose Page]selezionare le pagine da visualizzare.
1. Individuate la pagina.
1. Fai clic su **[!UICONTROL OK.]**

## Confronto delle suite di rapporti {#task_6BEBEB2D4F36497C9DA5B18ADAD35546}

Passaggi che descrivono come visualizzare i rapporti da due suite di rapporti nello stesso rapporto.

<!-- 

t_reports_compare_suites.xml

 -->

Oltre alla visualizzazione grafica, la tabella del rapporto fornisce un confronto percentuale. I report seguenti possono essere eseguiti con confronti:

* Contenuto del sito
* Mobile
* Origini del traffico
* Campagne
* Prodotti
* Conservazione dei visitatori
* Profilo visitatore
* Conversione personalizzata
* Traffico personalizzato
* Target
* Sondaggio

**Per confrontare le suite di rapporti**

1. Generare un rapporto che consenta di confrontare i rapporti.
1. Fate clic sul **[!UICONTROL Compare to Site]** collegamento.
1. Individua la suite di rapporti.
1. Fai clic su **[!UICONTROL OK.]**

## Specificare la granularità del rapporto {#task_7ED3EEC9E1704A918B25D06ADA3412E0}

Passaggi che descrivono come visualizzare i totali dei rapporti su base oraria, giornaliera, settimanale, mensile, trimestrale o annuale.

<!-- 

t_reports_granularity.xml

 -->

Il periodo di tempo del rapporto determina quali opzioni di granularità sono disponibili. Ad esempio, potete selezionare solo **[!UICONTROL Hourly]** se avete selezionato uno o due giorni di tempo. Potete selezionare solo **[!UICONTROL Yearly]** la granularità se avete selezionato più di un anno.

**Per specificare la granularità del rapporto**

1. Genera un report con tendenze, ad esempio **[!UICONTROL Site Content]** > **[!UICONTROL Pages.]**
1. Fate clic sul **[!UICONTROL View by]** collegamento, quindi fate clic su una granularità.

## Esecuzione di un rapporto del giorno della settimana {#task_67CC818ACC3749839B69BDB2ED9AE6B8}

Procedura che descrive come eseguire i rapporti in un giorno specifico della settimana, ad esempio ogni lunedì in un dato intervallo di date.

<!-- 

t_reports_day_of_week.xml

 -->

Questa funzione si applica solo ai report con tendenze filtrati con un intervallo di date di Settimana o Giorno.

1. Eseguire un report con tendenze su un intervallo di date specificato.
1. Fai clic sul **[!UICONTROL Day of Week]** collegamento, quindi fai clic su un giorno.

## Pulsante Prova in Workspace {#concept_DA41E22460B94BD9ADF63B1CEE2714A7}

Facendo clic sul **[!UICONTROL Try In Workspace]** pulsante nella parte superiore di un rapporto, verrà caricato lo stesso rapporto in  Analysis Workspace.

<!-- 

try_in_workspace.xml

 -->

La maggior parte dei report in Reporting e  Analytics ora include un pulsante &quot;Try in Workspace&quot; (Prova in area di lavoro) che consente di riprodurre la visualizzazione corrente in  Analysis Workspace per un&#39;ulteriore personalizzazione.

Attualmente, il pulsante è disponibile solo se il nome utente dispone dei diritti completi per  Analysis Workspace.

Per ulteriori informazioni su tutti i modi in cui puoi personalizzare il rapporto, consulta la guida [Analysis Workspace](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html) .
