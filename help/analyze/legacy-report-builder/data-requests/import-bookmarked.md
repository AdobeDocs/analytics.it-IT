---
description: Tutti i rapporti con segnalibri e i rapporti del dashboard sono ora elencati come dimensioni nel passaggio 1 della Creazione guidata richieste e possono essere importati come richieste Report Builder.
title: Importare rapporti con segnalibri e minirapporti dashboard
feature: Report Builder
role: User, Admin
exl-id: 19813950-2495-4a75-aacb-587b59bf2484
TQID: https://experienceleague.adobe.com/dnOYs7eOvv15K73EPrfRegz1vH9-B5p8xI8d86vPYe4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 235
ht-degree: 5%

---

# Importare rapporti con segnalibri e minirapporti dashboard

{{legacy-arb}}

Tutti i rapporti con segnalibri e i rapporti del dashboard sono ora elencati come dimensioni nel passaggio 1 della Creazione guidata richieste e possono essere importati come richieste Report Builder.

Quando si seleziona un rapporto con segnalibro, la Creazione guidata richieste popola tutte le dimensioni e le metriche che definiscono tale rapporto. Anche l’intervallo di date, la granularità e il segmento selezionato vengono aggiornati in base al segnalibro selezionato.

Il passaggio 1 della Creazione guidata richieste mostra un dashboard e i relativi reportlet in questo modo:

![Schermata che mostra il passaggio 1 di 2 della Creazione guidata richieste evidenziando Recupera dashboard e recupera segnalibri.](assets/import_dashboard_reportlet.png)

Quando si fa clic su **[!UICONTROL Retrieve your Dashboards]** o **[!UICONTROL Retrieve your Bookmarks]**, i dati del dashboard e/o segnalibro esistenti vengono recuperati e incollati nel foglio di lavoro.

>[!NOTE]
>
>Vengono importati solo i dati, quindi se il segnalibro contiene un grafico o se il reportlet del dashboard è costituito solo da un grafico, vengono importati solo i dati utilizzati per compilare il grafico.

Dopo aver creato una richiesta importando un reportlet del dashboard (o un segnalibro), la richiesta verrà associata alla dimensione principale del reportlet (o del segnalibro). Di conseguenza, se si modifica la richiesta, la vista albero non seleziona più il nodo di visualizzazione della struttura del reportlet del dashboard (o nodo segnalibro), ma la dimensione principale.

