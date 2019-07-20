---
description: Tutti i rapporti segnalibri e i rapporti dashboard sono ora elencati come dimensioni nella procedura guidata Richiesta 1 e possono essere importati come richieste di generatore di report.
seo-description: Tutti i rapporti segnalibri e i rapporti dashboard sono ora elencati come dimensioni nella procedura guidata Richiesta 1 e possono essere importati come richieste di generatore di report.
seo-title: Importare rapporti con segnalibri e minirapporti dashboard
solution: Analytics
title: Importare rapporti con segnalibri e minirapporti dashboard
topic: Generatore di report
uuid: 0 fdbdb 2 e -5 db 7-4 f 64-b 571-23482 ba 3606 d
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Importare rapporti con segnalibri e minirapporti dashboard

Tutti i rapporti segnalibri e i rapporti dashboard sono ora elencati come dimensioni nella procedura guidata Richiesta 1 e possono essere importati come richieste di generatore di report.

Quando selezionate un rapporto con segnalibro, la richiesta guidata compila tutte le dimensioni e le metriche che definiscono questo rapporto contrassegnato. Anche l'intervallo di date, la granularità e il segmento selezionato vengono aggiornati in base al segnalibro selezionato.

Ecco come la richiesta guidata 1 mostra una dashboard e i relativi reportlet:

![](assets/import_dashboard_reportlet.png)

When you click **[!UICONTROL Retrieve your Dashboards]** or **[!UICONTROL Retrieve your Bookmarks]**, your existing dashboard and/or bookmark data is retrieved and pasted in the worksheet.

>[!NOTE]
>
>In Generatore di report, l'elenco di dashboard e segnalibri disponibili è limitato all'utente, ma anche a quelli che si applicano alla suite di rapporti selezionata al Passaggio 1 della procedura guidata. Per contro, in reporting e analisi di marketing, ti viene fornito l'accesso a tutti i segnalibri e i dashboard che ti sono accessibili, indipendentemente dalle suite di rapporti utilizzate da tali dashboard e segnalibri.

>[!NOTE]
>
>Vengono importati solo i dati, quindi se il segnalibro contiene un grafico o se il minirapporto dashboard è costituito da un solo grafico, vengono importati solo i dati utilizzati per comporre il grafico.

Dopo aver creato una richiesta importando un minirapporto dashboard (o un segnalibro), la richiesta verrà associata alla dimensione principale del minirapporto (o segnalibro). Di conseguenza, se modificate la richiesta, la vista struttura non seleziona più il nodo di visualizzazione ad albero del minirapporto dashboard (o nodi segnalibro): ma ne seleziona la dimensione principale.

Il bookmarklet importato imposta correttamente la suite di rapporti, il segmento selezionato, la dimensione e le metriche selezionate sugli stessi parametri esposti nel segnalibro Reporting e analisi.

>[!IMPORTANT]
>
>L'intervallo di date verrà impostato sullo stesso intervallo di date, ma come intervallo di date statico, anche se questo intervallo di date era un intervallo di date continuo nel segnalibro Reporting e analisi.

