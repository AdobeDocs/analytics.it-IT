---
description: In Analysis Workspace, le metriche possono essere utilizzate in due modi.
title: Metriche in Analysis Workspace
feature: Metrics
role: User, Admin
exl-id: 0a5dc709-c4e8-412a-a6cf-37b85d811f65
source-git-commit: e0a10540bdfbd9fa3694ff3c7a8585eeb87eaad8
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 21%

---

# Metriche

Le metriche consentono di quantificare i punti dati in Analysis Workspace. Sono più comunemente utilizzate come colonne in una visualizzazione e legate alle dimensioni.

Adobe offre diversi tipi di metriche da utilizzare in Analysis Workspace:

* **Metriche standard**: la maggior parte delle metriche utilizzate nei progetti sono metriche standard. Alcuni esempi includono [Visualizzazioni pagina](/help/components/metrics/page-views.md), [Ricavi](/help/components/metrics/revenue.md), o [Eventi personalizzati](/help/components/metrics/custom-events.md). Consulta [Panoramica delle metriche](/help/components/metrics/overview.md) nella guida utente Componenti per ulteriori informazioni.

   ![Metrica standard](assets/standard-metric.png)

* **Metriche calcolate**: metriche definite dall’utente basate su metriche standard, numeri statici o funzioni algoritmiche. Le metriche calcolate definite dall’utente mostrano l’icona di una calcolatrice nell’elenco dei componenti disponibili. Consulta [Panoramica sulle metriche calcolate](/help/components/c-calcmetrics/cm-overview.md) nella guida utente Componenti per ulteriori informazioni.

   ![Metrica calcolata](assets/calculated-metric.png)

* **Modelli di metriche calcolate**: metriche definite dall’Adobe che si comportano in modo simile alle metriche calcolate. Puoi utilizzarli così come sono nei progetti Workspace o salvarne una copia per personalizzarne la logica. I modelli di metriche calcolate mostrano un’icona di Adobe nell’elenco dei componenti disponibili.

   ![Modello di metrica calcolata](assets/calculated-metric-template.png)

Le metriche sono flessibili per quanto riguarda il loro utilizzo in Analysis Workspace. Trascina una metrica in una tabella a forma libera vuota per visualizzare la tendenza della metrica nel periodo della data del progetto. Puoi anche trascinare una metrica quando è presente una dimensione per visualizzarla rispetto a ciascun elemento dimensione. Trascinare una metrica sopra un’intestazione di metrica esistente la sostituisce e trascinare una metrica accanto a un’intestazione consente di vedere entrambe le metriche una accanto all’altra.

>[!VIDEO](https://video.tv.adobe.com/v/40817/?quality=12)

## Metriche calcolate

Le metriche calcolate consentono di vedere facilmente in che modo le metriche si relazionano tra loro utilizzando semplici operatori o funzioni statistiche. Esistono diversi modi per creare metriche calcolate:

* Fai clic sul pulsante più accanto all’intestazione Metriche sotto l’elenco dei componenti a sinistra.
* Passa a **[!UICONTROL Components]** > **[!UICONTROL Calculated Metrics]** > **[!UICONTROL Add]**.
* Fai clic con il pulsante destro del mouse su un’intestazione di colonna > **[!UICONTROL Create metric from selection]** quando sono selezionate una o più celle della colonna di intestazione. Questa opzione crea automaticamente una metrica calcolata senza dover utilizzare il Generatore di regole della metrica calcolata.

[Metriche calcolate: metriche senza implementazione](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-implementationless-metrics.html?lang=it) (3:42)

## Confrontare metriche con diversi modelli di attribuzione

Per confrontare in modo rapido e semplice un modello di attribuzione con un altro, fai clic con il pulsante destro del mouse su una metrica e seleziona **[!UICONTROL Compare Attribution Models]**:

![Confrontare attribuzione](assets/compare-attribution.png)

Questa scorciatoia ti consente di confrontare in maniera facile e veloce un modello di attribuzione con un altro senza trascinare una metrica e configurarla due volte.

## Utilizza il [!UICONTROL cumulative average] funzione per applicare uniformità metrica

Video sull’argomento:

>[!VIDEO](https://video.tv.adobe.com/v/27068/?quality=12)
