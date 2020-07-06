---
description: Tutti i rapporti con segnalibro e dashboard sono ora elencati come dimensioni nel passaggio 1 della Richiesta guidata e possono essere importati come richieste del generatore di report.
title: Importare rapporti con segnalibri e minirapporti dashboard
topic: Report builder
uuid: 0fdbdb2e-5db7-4f64-b571-23482ba3606d
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 3%

---


# Importare rapporti con segnalibri e minirapporti dashboard

Tutti i rapporti con segnalibro e dashboard sono ora elencati come dimensioni nel passaggio 1 della Richiesta guidata e possono essere importati come richieste del generatore di report.

Quando si seleziona un rapporto con segnalibro, la Richiesta guidata compila tutte le dimensioni e le metriche che definiscono il rapporto con segnalibro. Anche l&#39;intervallo di date, la granularità e il segmento selezionato vengono aggiornati in base al segnalibro selezionato.

Questo è il modo in cui la Richiesta guidata Passaggio 1 mostra una dashboard e i relativi minirapporti:

![](assets/import_dashboard_reportlet.png)

Quando si fa clic **[!UICONTROL Retrieve your Dashboards]** o **[!UICONTROL Retrieve your Bookmarks]**, i dati del dashboard e/o del segnalibro esistenti vengono recuperati e incollati nel foglio di lavoro.

>[!NOTE]
>
>In Generatore di report, l&#39;elenco delle dashboard e dei segnalibri disponibili è limitato all&#39;utente, ma anche a quelli applicabili alla suite di rapporti selezionata al passaggio 1 della procedura guidata. Per contro, in reporting e analisi di marketing, si dispone dell&#39;accesso a tutti i segnalibri e le dashboard accessibili, indipendentemente dalle suite di rapporti utilizzate da tali dashboard e segnalibri.

>[!NOTE]
>
>Vengono importati solo i dati, quindi se il segnalibro contiene un grafico o se il minirapporti del dashboard è composto solo da un grafico, vengono importati solo i dati utilizzati per compilare il grafico.

Dopo aver creato una richiesta importando un reportlet del dashboard (o un segnalibro), la richiesta viene quindi associata alla dimensione primaria del report (o del segnalibro). Di conseguenza, se modificate la richiesta, la vista ad albero non seleziona più il nodo della visualizzazione ad albero del portlet del dashboard (o il nodo del segnalibro): seleziona invece la dimensione principale.

Il bookmarklet importato imposta correttamente la suite di rapporti, il segmento selezionato, la dimensione e le metriche selezionate sugli stessi parametri esposti nel segnalibro Reports &amp;  Analytics.

>[!IMPORTANT]
>
>L&#39;intervallo di date sarà impostato sullo stesso intervallo di date, ma come intervallo di date statico, anche se questo intervallo di date era un intervallo di date continuo nel segnalibro Reports &amp;  Analytics.

