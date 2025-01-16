---
description: L’istogramma è un nuovo tipo di visualizzazione disponibile in Analysis Workspace.
title: Istogramma
uuid: 8a6bd2c4-da15-4f64-b889-ab9add685046
feature: Visualizations
role: User, Admin
exl-id: f3dd7507-db2c-495c-b6b9-6c770c7c7ddc
source-git-commit: c0855c6bed6a9762c0440e1a8e004ee11020808e
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 88%

---

# Istogramma {#histogram}

arkdownlint-disable MD034 —>

>[!CONTEXTUALHELP]
>id="workspace_histogram_button"
>title="Istogramma"
>abstract="Crea una visualizzazione a istogramma per rappresentare la distribuzione dei dati numerici in gruppi di intervalli."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

*Questo articolo documenta la visualizzazione Istogramma in **Adobe Analytics**.<br/>Vedere [Istogramma](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/histogram) per la versione **Customer Journey Analytics**di questo articolo.*

>[!ENDSHADEBOX]


Un istogramma è simile a un grafico a barre, ma con i numeri raggruppati in intervalli. Analytics automatizza la creazione di intervalli di numeri, ma puoi comunque cambiare le impostazioni in [Impostazioni avanzate](#section_09D774C584864D4CA6B5672DC2927477).

Ecco un video su come utilizzare gli istogrammi:

>[!VIDEO](https://video.tv.adobe.com/v/23725/?quality=12)

## Creare un istogramma {#section_74647707CC984A1CB6D3097F43A30B45}

Per creare un istogramma:

1. Fai clic su **[!UICONTROL Visualizations]** nella barra a sinistra.
1. Trascina **[!UICONTROL Histogram]** nel pannello.
1. Scegli una metrica da trascinare sulla visualizzazione Istogramma e fai clic su **[!UICONTROL Build]**.

![](assets/histogram.png)

>[!NOTE]
>
>Gli istogrammi supportano solo metriche standard; le metriche calcolate non sono supportate.

In questo esempio abbiamo usato la metrica Visualizzazioni di pagina per Visitatori uninovi. Il primo intervallo (a sinistra) corrisponde a 1 visualizzazione di pagina per visitatore univoco; il secondo a 2 visualizzazioni di pagina, ecc.

![](assets/histogram2.png)

## Impostazioni avanzate {#section_09D774C584864D4CA6B5672DC2927477}

Per regolare le impostazioni dell’istogramma, fai clic sull’icona Impostazioni (a forma di ingranaggi) in alto a destra. Puoi modificare le seguenti impostazioni:

| Impostazioni istogramma | Funzione |
|---|---|
| Intervallo iniziale | Determina con quale intervallo inizia l’istogramma. L’impostazione predefinita è 1. Puoi impostare il numero iniziale da 0 all’infinito (non sono consentiti numeri negativi). |
| Intervalli di metrica | Consente di aumentare/diminuire il numero di intervalli di dati (bucket). Il numero massimo di bucket è 50. |
| Dimensione intervalli di metrica | Puoi impostare la dimensione di ogni intervallo. Ad esempio, puoi cambiare la dimensione dell’intervallo da 1 a 2 visualizzazioni di pagina. |
| Metodo di conteggio | Consente di scegliere tra [Visitatore](/help/components/metrics/unique-visitors.md), [Visita](/help/components/metrics/visits.md) o [Tipo di hit](/help/components/dimensions/hit-type.md). Ad esempio, visualizzazioni di pagina per visita, per visitatore o per hit. Per Hit, “Occorrenze” viene usato come metrica dell’asse y in una tabella a forma libera. |

<!--Russ or Meike - Check Hit Type link above. -->

**Esempi**:

* Con Intervallo iniziale: 1; Intervalli di metrica: 5; Dimensione intervalli di metrica: 2 viene generato l’istogramma: 1-2, 3-4, 5-6, 7-8, 9-10.
* Con Intervallo iniziale: 0; Intervalli di metrica: 3; Dimensione intervalli di metrica: 5 viene generato l’istogramma: 0-4, 5-9, 10-14.

## Visualizzare e modificare i dati dell’istogramma {#section_B2CD7CDF0F6B432F928103AE7AAA3617}

Per visualizzare o modificare l’origine dei dati dell’istogramma, fai clic sul punto accanto all’intestazione Istogramma per passare a **[!UICONTROL Data Source Settings]** > **[!UICONTROL Show Data Source]**.

![](assets/manage-data-source.png)

I segmenti pregenerati che compaiono nella tabella sono segmenti interni e non saranno visualizzati nel selettore dei segmenti. Fai clic sul pulsante “i” accanto al nome del segmento, quindi fai clic su **[!UICONTROL Make public]** per rendere il segmento pubblico.

![](assets/prebuilt_segments.png)

Per scoprire altri modi di gestire le tabelle di dati a forma libera e altre visualizzazioni, ad esempio per suddividere i dati, visita [questa pagina](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=it).
