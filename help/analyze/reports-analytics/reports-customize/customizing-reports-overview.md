---
description: Dopo aver eseguito un rapporto, puoi personalizzare il rapporto per visualizzare e analizzare i dati in base alle tue esigenze. Puoi filtrare i dati dei rapporti, modificare il modo in cui i dati vengono presentati graficamente, modificare la granularità della data e così via.
title: Panoramica della personalizzazione dei rapporti
uuid: 37d221b7-50fd-4425-b2ba-f40911b72a2f
feature: Nozioni di base su Reports & Analytics
role: Business Practitioner, Administrator
exl-id: 5a042fac-926e-4560-83bf-11f66ddb8273
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '868'
ht-degree: 4%

---

# Panoramica della personalizzazione dei rapporti

Dopo aver eseguito un rapporto, puoi personalizzare il rapporto per visualizzare e analizzare i dati in base alle tue esigenze. Puoi filtrare i dati dei rapporti, modificare il modo in cui i dati vengono presentati graficamente, modificare la granularità della data e così via.

## Creare un rapporto personalizzato {#task_BA6EACA3039C40AEA5605E1D8C76E646}

Passaggi che descrivono come salvare la configurazione corrente di un rapporto come nuovo rapporto personalizzato da visualizzare per tutti gli utenti.

<!-- 

t_reports_custom.xml

 -->

Solo gli amministratori possono creare un rapporto personalizzato. Quando crei un rapporto personalizzato, questo viene aggiunto al menu principale accanto al rapporto su cui si basa.

**Creazione di un rapporto personalizzato**

1. Esegui un rapporto e configuralo come necessario.
1. Fai clic su **[!UICONTROL More]** > **[!UICONTROL Create Custom Report]**.
1. Assegna un nome al rapporto, quindi fai clic su **[!UICONTROL Save.]**

   Assicurati di non duplicare un nome di report esistente.

>[!MORELIKETHIS]
>
>* [Personalizzazione del menu](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/customize-menus.html)


## Selezionare un intervallo di date o date {#task_9BEF7D4D839A4748B76E8500D1406C34}

I passaggi che descrivono &quot;caldo&quot; da utilizzare consentono di scegliere i periodi di tempo per i dati del rapporto.

<!-- 

t_reports_select_date.xml

 -->

Puoi selezionare giorni, settimane, mesi o anni specifici. È inoltre possibile eseguire rapporti di confronto.

Quando apri una dashboard con minirapporti che hanno intervalli di date diversi, puoi scegliere un nuovo intervallo di date nel calendario. Le modifiche vengono applicate a tutti i minirapporti nel dashboard.

**Per selezionare un intervallo di date**

1. Esegui un report.
1. Fai clic sull&#39;icona del calendario in alto a destra.
1. Seleziona una data.

   È possibile:

   * Visualizza giorni, mesi o periodi di anno (fino a tre).
   * Trascina il cursore tra le date per selezionare un intervallo.
   * Immetti le date manualmente.
   * Fai clic sul nome di un mese per selezionare un mese.
   * Fai clic su **[!UICONTROL Select Preset]** per selezionare una data preimpostata.
   * Confronta le date.

1. Fai clic su **[!UICONTROL Run Report]**.

## Confronto delle date {#task_95155C3700774B709F5FB81AE96B0824}

Passaggi che descrivono come utilizzare il calendario per eseguire confronti di date tra rapporti con classifica.

<!-- 

t_reports_comparing_dates.xml

 -->

Non è possibile confrontare date tra rapporti con tendenze.

>[!NOTE]
>
>Se desideri eseguire un confronto delle date sulle metriche chiave in un dashboard, puoi estrarre i dati in [Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html) utilizzando due richieste separate. In seguito, è possibile utilizzare formule personalizzate in Excel per analizzare la differenza tra le due.

Per confrontare date tra rapporti classificati in Reporting e analisi:

1. Esegui un report.
1. Fai clic sul calendario in alto a destra.
1. Fai clic su **[!UICONTROL Compare Dates]**.
1. Seleziona le date da utilizzare.
1. Fai clic su **[!UICONTROL Run Report]**.

## Visualizza una percentuale come grafico {#task_BC28CA19A4834AF6BFE68B5B5AEFE75D}

Passaggi che descrivono come specificare se visualizzare la percentuale in una tabella di rapporto come grafico.

<!-- 

t_reports_graph_percent.xml

 -->

Questa visualizzazione è disponibile anche nei reportlet del dashboard.

1. Esegui un rapporto che supporta le percentuali, ad esempio un [!UICONTROL Pages Report].
1. Fai clic su **[!UICONTROL Percent Shown As: Graph]**.

## Normalizzare i dati del report {#task_8005B55E59BD479DA67BC618FF8BC94A}

Passaggi che descrivono come normalizzare i dati dei rapporti.

<!-- 

t_reports_normalize.xml

 -->

Dopo aver eseguito un rapporto con date confrontate o per confronti A/B, puoi normalizzare i dati per mostrare la percentuale di modifica tra i rapporti. L&#39;insieme di dati secondari viene modificato per compensare le differenze nel numero di giorni selezionati o per diversi volumi di traffico.

**normalizzazione dei dati del rapporto**

1. Esegui un rapporto che supporta i confronti tra date.
1. Fai clic su **[!UICONTROL Compare Dates]**, quindi specifica il confronto delle date.
1. Fai clic su **[!UICONTROL Run Report]**.
1. Fai clic su **[!UICONTROL Normalize Data: Yes]**.

## Selezionare una pagina per un rapporto {#task_5CAC3B76BD4C4208B8D53DD972D4771F}

Passaggi che descrivono come selezionare una pagina specifica dalle pagine del sito web per un rapporto.

<!-- 

t_reports_select_page.xml

 -->

1. Genera un rapporto, ad esempio un [!UICONTROL Page Views Report] ( **[!UICONTROL Reports]** > **[!UICONTROL Site Metrics]** > **[!UICONTROL Page Views]**).
1. Fai clic sul collegamento **[!UICONTROL Selected Page]** .
1. In [!UICONTROL Choose Page], selezionare le pagine da visualizzare.
1. Individua la pagina.
1. Fai clic su **[!UICONTROL OK.]**

## Confrontare suite di rapporti {#task_6BEBEB2D4F36497C9DA5B18ADAD35546}

Passaggi che descrivono come visualizzare i rapporti da due suite di rapporti nello stesso rapporto.

<!-- 

t_reports_compare_suites.xml

 -->

Oltre alla visualizzazione grafica, la tabella del rapporto fornisce un confronto percentuale. È possibile eseguire i seguenti rapporti con confronti:

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

**Confronto delle suite di rapporti**

1. Genera un rapporto che ti consente di confrontare i rapporti.
1. Fai clic sul collegamento **[!UICONTROL Compare to Site]** .
1. Individua la suite di rapporti.
1. Fai clic su **[!UICONTROL OK.]**

## Specificare la granularità del rapporto {#task_7ED3EEC9E1704A918B25D06ADA3412E0}

Passaggi che descrivono come visualizzare i totali dei rapporti su base oraria, giornaliera, settimanale, mensile, trimestrale o annuale.

<!-- 

t_reports_granularity.xml

 -->

Il periodo di tempo del rapporto determina quali opzioni di granularità sono disponibili. Ad esempio, è possibile selezionare solo **[!UICONTROL Hourly]** se è stato selezionato uno o due intervalli di tempo. È possibile selezionare solo la granularità **[!UICONTROL Yearly]** se sono stati selezionati più di un anno.

**Per specificare la granularità del rapporto**

1. Genera un rapporto con tendenze, ad esempio **[!UICONTROL Site Content]** > **[!UICONTROL Pages.]**
1. Fai clic sul collegamento **[!UICONTROL View by]** , quindi fai clic su una granularità.

## Eseguire un rapporto giornaliero della settimana {#task_67CC818ACC3749839B69BDB2ED9AE6B8}

Passaggi che descrivono come eseguire rapporti in un giorno specifico della settimana, ad esempio su ogni lunedì in un determinato intervallo di date.

<!-- 

t_reports_day_of_week.xml

 -->

Questa funzione si applica solo ai report con tendenze filtrati con un intervallo di date di Settimana o Giorno.

1. Esegui un rapporto con tendenze su un intervallo di date specificato.
1. Fai clic sul collegamento **[!UICONTROL Day of Week]**, quindi fai clic su un giorno.

## Pulsante &quot;Prova in Workspace&quot; {#concept_DA41E22460B94BD9ADF63B1CEE2714A7}

Facendo clic sul pulsante **[!UICONTROL Try In Workspace]** nella parte superiore di un rapporto, lo stesso verrà caricato in Analysis Workspace.

<!-- 

try_in_workspace.xml

 -->

La maggior parte dei rapporti in Reports &amp; Analytics ora include un pulsante &quot;Try in Workspace&quot; (Prova in area di lavoro) per consentirti di riprodurre la visualizzazione corrente in Analysis Workspace per un’ulteriore personalizzazione.

Attualmente, il pulsante è disponibile solo se il tuo nome utente dispone dei diritti completi su Analysis Workspace.

Per ulteriori informazioni su come personalizzare il rapporto, consulta la guida [Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html) .
