---
description: Tutti i rapporti con segnalibri e i rapporti del dashboard sono ora elencati come dimensioni nel passaggio 1 della Creazione guidata richieste e possono essere importati come richieste del generatore di rapporti.
title: Importare rapporti con segnalibri e minirapporti dashboard
feature: Report Builder
role: User, Admin
exl-id: 19813950-2495-4a75-aacb-587b59bf2484
source-git-commit: fb39f906d6c08713e4dc8211c917b2942502868e
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 3%

---

# Importare rapporti con segnalibri e minirapporti dashboard

Tutti i rapporti con segnalibri e i rapporti del dashboard sono ora elencati come dimensioni nel passaggio 1 della Creazione guidata richieste e possono essere importati come richieste del generatore di rapporti.

Quando si seleziona un rapporto con segnalibro, la Creazione guidata richieste popola tutte le dimensioni e le metriche che definiscono tale rapporto. Anche l’intervallo di date, la granularità e il segmento selezionato vengono aggiornati in base al segnalibro selezionato.

Il passaggio 1 della Creazione guidata richieste mostra un dashboard e i relativi reportlet in questo modo:

![Schermata che mostra il Passaggio 1 di 2 della Creazione guidata richieste evidenziando Recupera dashboard e Recupera segnalibri.](assets/import_dashboard_reportlet.png)

Quando fai clic su **[!UICONTROL Retrieve your Dashboards]** o **[!UICONTROL Retrieve your Bookmarks]**, i dati del dashboard e/o segnalibro esistenti vengono recuperati e incollati nel foglio di lavoro.

>[!NOTE]
>
>In Report Builder, l’elenco delle dashboard e dei segnalibri disponibili è limitato all’utente ma anche a quelli applicabili alla suite di rapporti selezionata al passaggio 1 della procedura guidata. Al contrario, in Reports &amp; Analytics di marketing, puoi accedere a tutti i segnalibri e le dashboard accessibili, indipendentemente dalle suite di rapporti utilizzate da dashboard e segnalibri.

>[!NOTE]
>
>Vengono importati solo i dati, quindi se il segnalibro contiene un grafico o se il reportlet del dashboard è costituito solo da un grafico, vengono importati solo i dati utilizzati per compilare il grafico.

Dopo aver creato una richiesta importando un reportlet del dashboard (o un segnalibro), la richiesta verrà associata alla dimensione principale del reportlet (o del segnalibro). Di conseguenza, se si modifica la richiesta, la vista albero non seleziona più il nodo di visualizzazione della struttura del reportlet del dashboard (o nodo segnalibro), ma la dimensione principale.

Il bookmarklet importato imposterà correttamente la suite di rapporti, il segmento selezionato, la dimensione e le metriche selezionate sugli stessi parametri esposti nel segnalibro Reports &amp; Analytics.

>[!IMPORTANT]
>
>L’intervallo di date sarà impostato sullo stesso intervallo, ma come intervallo di date statico, anche se si tratta di un intervallo di date continuo nel segnalibro di Reports &amp; Analytics.
