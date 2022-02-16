---
description: Tutti i rapporti con segnalibri e i rapporti dashboard sono ora elencati come dimensioni nel passaggio 1 della Creazione guidata richieste e possono essere importati come richieste di Report Builder.
title: Importare rapporti con segnalibri e minirapporti dashboard
feature: Report Builder
role: User, Admin
exl-id: 19813950-2495-4a75-aacb-587b59bf2484
source-git-commit: 1ee50c6a2231795b2ad0015a79e09b7c1c74d850
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 3%

---

# Importare rapporti con segnalibri e minirapporti dashboard

Tutti i rapporti con segnalibri e i rapporti dashboard sono ora elencati come dimensioni nel passaggio 1 della Creazione guidata richieste e possono essere importati come richieste di Report Builder.

Quando si seleziona un rapporto con segnalibro, la Creazione guidata richieste compila tutte le dimensioni e le metriche che definiscono questo rapporto con segnalibro. Anche l’intervallo di date, la granularità e il segmento selezionato vengono aggiornati in base al segnalibro selezionato.

Questo è il modo in cui la Creazione guidata richieste al passaggio 1 mostra un dashboard e i relativi minirapporti:

![](assets/import_dashboard_reportlet.png)

Quando fai clic su **[!UICONTROL Retrieve your Dashboards]** o **[!UICONTROL Retrieve your Bookmarks]**, i dati esistenti del dashboard e/o del segnalibro vengono recuperati e incollati nel foglio di lavoro.

>[!NOTE]
>
>Al Report Builder, l’elenco delle dashboard e dei segnalibri disponibili è limitato all’utente ma anche a quelli applicabili alla suite di rapporti selezionata al passaggio 1 della procedura guidata. Al contrario, in reporting e analisi di marketing, puoi accedere a tutti i segnalibri e le dashboard che ti sono accessibili, indipendentemente dalle suite di rapporti che utilizzano il dashboard e i segnalibri.

>[!NOTE]
>
>Vengono importati solo i dati, quindi se il segnalibro contiene un grafico o se il reportlet del dashboard è costituito solo da un grafico, vengono importati solo i dati utilizzati per compilare il grafico.

Dopo aver creato una richiesta importando un reportlet di dashboard (o un segnalibro), la richiesta verrà quindi associata alla dimensione primaria del reportlet (o del segnalibro). Di conseguenza, se si modifica la richiesta, la vista ad albero non seleziona più il nodo di visualizzazione ad albero del reportlet del dashboard (o il nodo del segnalibro): seleziona invece la dimensione primaria.

Il bookmarklet importato imposterà correttamente la suite di rapporti, il segmento selezionato, la dimensione e le metriche selezionate sugli stessi parametri esposti nel segnalibro Reports &amp; Analytics.

>[!IMPORTANT]
>
>L’intervallo di date verrà impostato sullo stesso intervallo di date, ma come intervallo di date statico, anche se questo intervallo era un intervallo di date continuo nel segnalibro Reports &amp; Analytics.
