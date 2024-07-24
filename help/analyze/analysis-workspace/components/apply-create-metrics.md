---
description: In Analysis Workspace, le metriche possono essere utilizzate in due modi.
title: Metriche in Analysis Workspace
feature: Metrics
role: User, Admin
exl-id: 0a5dc709-c4e8-412a-a6cf-37b85d811f65
source-git-commit: f8541ac8f82e63f1664b06ed788d307c5d224ca9
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 16%

---

# Metriche

Le metriche consentono di quantificare i punti dati in Analysis Workspace. Sono più comunemente utilizzate come colonne in una visualizzazione e legate alle dimensioni.

## Tipi di metriche

Adobe offre diversi tipi di metriche da utilizzare in Analysis Workspace:

* **Metriche standard**: la maggior parte delle metriche utilizzate nei progetti sono metriche standard. Gli esempi includono [visualizzazioni pagina](/help/components/metrics/page-views.md), [ricavi](/help/components/metrics/revenue.md) o [eventi personalizzati](/help/components/metrics/custom-events.md). Per ulteriori informazioni, consulta [Panoramica delle metriche](/help/components/metrics/overview.md) nella guida utente dei Componenti.

  ![Metrica standard](assets/standard-metric.png)

* **Metriche calcolate**: metriche definite dall&#39;utente basate su metriche standard, numeri statici o funzioni algoritmiche. Le metriche calcolate definite dall’utente mostrano l’icona di una calcolatrice nell’elenco dei componenti disponibili. Per ulteriori informazioni, consulta [Panoramica sulle metriche calcolate](/help/components/c-calcmetrics/cm-overview.md) nella guida utente dei componenti.

  ![Metrica calcolata](assets/calculated-metric.png)

* **Modelli di metriche calcolate**: metriche definite dall&#39;Adobe che si comportano in modo simile alle metriche calcolate. Puoi utilizzarli così come sono nei progetti Workspace o salvarne una copia per personalizzarne la logica. I modelli di metriche calcolate mostrano un’icona di Adobe nell’elenco dei componenti disponibili.

  ![Modello di metrica calcolata](assets/calculated-metric-template.png)

## Utilizzare le metriche in Analysis Workspace

Le metriche possono essere utilizzate in vari modi all’interno di Analysis Workspace. Per informazioni su come aggiungere metriche e altri tipi di componenti ad Analysis Workspace, vedi [Utilizzare componenti in Analysis Workspace](/help/analyze/analysis-workspace/components/use-components-in-workspace.md).

>[!VIDEO](https://video.tv.adobe.com/v/40817/?quality=12)

## Creare metriche calcolate

Le metriche calcolate consentono di vedere facilmente in che modo le metriche si relazionano tra loro utilizzando semplici operatori o funzioni statistiche.

Esistono diversi modi per creare metriche calcolate. Il metodo scelto determina se la metrica calcolata è disponibile nell’elenco dei componenti in tutti i progetti o solo nel progetto in cui è stata creata.

### Creare metriche calcolate per tutti i progetti

Puoi utilizzare il generatore di metriche calcolate per creare metriche calcolate. Quando vengono create in questo modo, le metriche calcolate sono disponibili nell’elenco dei componenti e possono quindi essere utilizzate nei progetti di tutta l’organizzazione.

Per informazioni su come accedere al generatore di metriche calcolate, vedere [Genera metriche](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).

### Creare metriche calcolate per un singolo progetto

Puoi creare metriche calcolate rapide disponibili solo per il progetto in cui sono state create.

Per creare una metrica calcolata per un singolo progetto:

1. In Analysis Workspace, apri il progetto in cui desideri creare la metrica calcolata.

1. In una tabella a forma libera, fare clic con il pulsante destro del mouse su una o più celle di colonna di intestazione, quindi selezionare **[!UICONTROL Create metric from selection]**

   ![Evidenziazione del pannello Workspace Crea da selezione](assets/create-metric-from-selection.png)

1. Per creare una metrica calcolata solo per questo progetto, scegli una delle seguenti opzioni:

   * [!UICONTROL **Dividi**]

   * [!UICONTROL **Sottrai**]

   * [!UICONTROL **Aggiungi**]

   * [!UICONTROL **Moltiplica**]

   In alternativa, per aprire il generatore di metriche calcolate e creare la metrica calcolata per tutti i progetti, selezionare [!UICONTROL **Apri nel generatore di metriche calcolate**], quindi continuare con [Genera metriche](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md).

[Metriche calcolate: metriche senza implementazione](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html?lang=it) (3:42)

## Confrontare metriche con diversi modelli di attribuzione

Per confrontare in modo rapido e semplice un modello di attribuzione con un altro, fai clic con il pulsante destro del mouse su una metrica e seleziona **[!UICONTROL Compare Attribution Models]**:

![Confrontare attribuzione](assets/compare-attribution.png)

Questa scorciatoia ti consente di confrontare in maniera facile e veloce un modello di attribuzione con un altro senza trascinare una metrica e configurarla due volte.

## Utilizza la funzione [!UICONTROL cumulative average] per applicare l&#39;arrotondamento delle metriche

Video sull’argomento:

>[!VIDEO](https://video.tv.adobe.com/v/27068/?quality=12)
