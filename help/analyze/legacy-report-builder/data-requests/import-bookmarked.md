---
description: Tutti i rapporti con segnalibri e i rapporti del dashboard sono ora elencati come dimensioni nel passaggio 1 della Creazione guidata richieste e possono essere importati come richieste di Report Builder.
title: Importare rapporti con segnalibri e minirapporti dashboard
feature: Report Builder
role: User, Admin
exl-id: 19813950-2495-4a75-aacb-587b59bf2484
source-git-commit: ae6ffed05f5a33f032d0c7471ccdb1029154ddbd
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 5%

---

# Importare rapporti con segnalibri e minirapporti dashboard

{{legacy-arb}}

Tutti i rapporti con segnalibri e i rapporti del dashboard sono ora elencati come dimensioni nel passaggio 1 della Creazione guidata richieste e possono essere importati come richieste di Report Builder.

Quando si seleziona un rapporto con segnalibro, la Creazione guidata richieste popola tutte le dimensioni e le metriche che definiscono tale rapporto. Anche l’intervallo di date, la granularità e il segmento selezionato vengono aggiornati in base al segnalibro selezionato.

Il passaggio 1 della Creazione guidata richieste mostra un dashboard e i relativi reportlet in questo modo:

![Schermata che mostra il passaggio 1 di 2 della Creazione guidata richieste evidenziando Recupera dashboard e recupera segnalibri.](assets/import_dashboard_reportlet.png)

Quando si fa clic su **[!UICONTROL Retrieve your Dashboards]** o **[!UICONTROL Retrieve your Bookmarks]**, i dati del dashboard e/o segnalibro esistenti vengono recuperati e incollati nel foglio di lavoro.

>[!NOTE]
>
>Vengono importati solo i dati, quindi se il segnalibro contiene un grafico o se il reportlet del dashboard è costituito solo da un grafico, vengono importati solo i dati utilizzati per compilare il grafico.

Dopo aver creato una richiesta importando un reportlet del dashboard (o un segnalibro), la richiesta verrà associata alla dimensione principale del reportlet (o del segnalibro). Di conseguenza, se si modifica la richiesta, la vista albero non seleziona più il nodo di visualizzazione della struttura del reportlet del dashboard (o nodo segnalibro), ma la dimensione principale.

