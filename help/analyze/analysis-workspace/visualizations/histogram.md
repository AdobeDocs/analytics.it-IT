---
description: L’istogramma è un nuovo tipo di visualizzazione disponibile in Analysis Workspace.
title: Istogramma
uuid: 8a6bd2c4-da15-4f64-b889-ab9add685046
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Istogramma

Un istogramma è simile a un grafico a barre, ma con i numeri raggruppati in intervalli. Analytics automatizza la creazione di intervalli di numeri, ma puoi comunque cambiare le impostazioni in [Impostazioni avanzate](#section_09D774C584864D4CA6B5672DC2927477).

## Creare un istogramma {#section_74647707CC984A1CB6D3097F43A30B45}

Per creare un istogramma:

1. Fai clic su **[!UICONTROL Visualizations]** (Visualizzazioni) nella barra a sinistra.
1. Trascina **[!UICONTROL Histogram]** (Istogramma) nel pannello.
1. Scegli una metrica da trascinare sulla visualizzazione Istogramma e fai clic su **[!UICONTROL Build]** (Genera).

![](assets/histogram.png)

> [!NOTE] Gli istogrammi supportano solo metriche standard; le metriche calcolate non sono supportate.

In questo esempio abbiamo usato la metrica Visualizzazioni di pagina per Visitatori unici. Il primo intervallo (a sinistra) corrisponde a 1 visualizzazione di pagina per visitatore univoco; il secondo a 2 visualizzazioni di pagina, ecc.

![](assets/histogram2.png)

## Impostazioni avanzate {#section_09D774C584864D4CA6B5672DC2927477}

Per regolare le impostazioni dell’istogramma, fai clic sull’icona Impostazioni (a forma di ingranaggi) in alto a destra. Puoi modificare le seguenti impostazioni:

| Impostazioni istogramma | Funzione |
|---|---|
| Intervallo iniziale | Determina con quale intervallo inizia l’istogramma. L’impostazione predefinita è 1. Puoi impostare il numero iniziale da 0 all’infinito (non sono consentiti numeri negativi). |
| Intervalli di metrica | Puoi aumentare o ridurre il numero di intervalli di dati. Il numero massimo consentito è 50. |
| Dimensione intervalli di metrica | Puoi impostare la dimensione di ogni intervallo. Ad esempio, puoi cambiare la dimensione dell’intervallo da 1 a 2 visualizzazioni di pagina. |
| Metodo di conteggio | Consente di scegliere tra [Visitatore](https://marketing.adobe.com/resources/help/en_US/reference/visitors.html), [Visita](https://marketing.adobe.com/resources/help/it_IT/reference/metrics_visit.html) o [Hit](https://marketing.adobe.com/resources/help/en_US/reference/hit.html). Ad esempio, visualizzazioni di pagina per visita, per visitatore o per hit. Per Hit, “Occorrenze” viene usato come metrica dell’asse y in una tabella a forma libera. |

**Esempi**:

* Con Intervallo iniziale: 1; Intervalli di metrica: 5; Dimensione intervalli di metrica: 2 viene generato l’istogramma: 1-2, 3-4, 5-6, 7-8, 9-10.
* Con Intervallo iniziale: 0; Intervalli di metrica: 3; Dimensione intervalli di metrica: 5 viene generato l’istogramma: 0-4, 5-9, 10-14.

## Visualizzare e modificare i dati dell’istogramma {#section_B2CD7CDF0F6B432F928103AE7AAA3617}

Per visualizzare o modificare l’origine dei dati dell’istogramma, fai clic sul punto accanto all’intestazione Istogramma per passare a **[!UICONTROL Data Source Settings]** &gt; **[!UICONTROL Show Data Source]** (Impostazioni dell’origine dati &gt; Mostra origine dati).

![](assets/manage-data-source.png)

I segmenti pregenerati che compaiono nella tabella sono segmenti interni e non saranno visualizzati nel selettore dei segmenti. Fai clic sul pulsante “i” accanto al nome del segmento, quindi fai clic su **[!UICONTROL Make public]** (Rendi pubblico) per rendere il segmento pubblico.

![](assets/prebuilt_segments.png)

Per scoprire altri modi di gestire le tabelle di dati a forma libera e altre visualizzazioni, ad esempio per suddividere i dati, visita [questa pagina](https://marketing.adobe.com/resources/help/it_IT/analytics/analysis-workspace/freeform-analysis-visualizations.html).
