---
description: La segmentazione delle singole metriche consente di eseguire confronti metriche nello stesso rapporto. (solo metriche derivate)
seo-description: La segmentazione delle singole metriche consente di eseguire confronti metriche nello stesso rapporto. (solo metriche derivate)
seo-title: Metriche segmentate
title: Metriche segmentate
uuid: 88 f 9829 b -76 e 4-4598-9494-084 a 91602 bc 1
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Metriche segmentate

La segmentazione delle singole metriche consente di eseguire confronti metriche nello stesso rapporto. (solo metriche derivate)

## Confronto segmenti {#section_29A6E0070F084BFDB6228FA9CE106F48}

Diciamo che vuoi confrontare diversi aspetti di segmenti di «Visitatori Uniti» con quelli del segmento «Visitatori internazionali». Puoi creare metriche che ti daranno informazioni quali:

* In che modo il comportamento di navigazione dei contenuti viene confrontato tra i due gruppi? Un altro esempio è: Come si confronta il tasso di conversione tra i due segmenti?)
* Come percentuale dei visitatori totali, quanti visitatori USA sfoglia determinate pagine e i visitatori internazionali?
* Dove si trovano i diversi segmenti per le differenze tra i vari segmenti?

Diamo un'occhiata alla prima domanda: In che modo il comportamento di navigazione dei contenuti viene confrontato tra i due gruppi?

1. Se non disponi di un segmento paragonabile, crea un segmento interno direttamente nel Generatore metriche calcolate denominato "Visitatori tedeschi", dove "Paesi" è uguale a "Germania". Trascina la dimensione Paesi nel quadro di definizione e seleziona Germania come valore:

   ![](assets/segment-from-dimension.png)

   >[!NOTE]
   >
   >You can also do this in the [Segment Builder](https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_build.html), but we have simplified the workflow by making dimensions available in the Calculated Metric Builder.

   >[!NOTE]
   >
   >"Internal" means that the segment is not visible in the **[!UICONTROL Segments]** list in the left rail. You can however, make it public by hovering over the "i" icon next to it and clicking **[!UICONTROL Make public]**.

1. Se non hai un segmento paragonabile, crea un segmento denominato «Visitatori internazionali» dove «Paesi» non equivale alla Germania.
1. Crea e salva una metrica denominata «Visitatori tedeschi» trascinando il segmento Germania nel quadro della definizione e trascinando al suo interno la metrica Visitatori unici:

   ![](assets/german-visitors.png)

1. Ripetete il passaggio 3 con il segmento Visitatori internazionali e la metrica Visitatori unici per creare una metrica Visitatori internazionali.
1. In Analysis Workspace, drag the **[!UICONTROL Page]** Dimension into a Freeform Table and drag the 2 new calculated metrics next to each other to the top:

   ![](assets/workspace-pages.png)

1. Or, in [!UICONTROL Reports & Analytics], open the [!UICONTROL Pages] report and click **[!UICONTROL Show Metrics]**, then apply the new US Visitors and International Visitors segmented metrics to see how their content browsing behavior compares.

   ![](assets/pages-report.png)

## Compare Percentages of Totals {#section_846CB89725F04388AE0352DB20189EE8}

Puoi introdurre un altro livello di interazione confrontando il comportamento di esplorazione dei visitatori in percentuali normalizzate. A tal fine, crea, due nuove metriche, " % of Total German Visitors" e " % of Total International Visitors":

1. Rilascia il segmento Visitatori tedesco (o Internazionale) nel quadro.
1. Rilascia un altro segmento Visitatori tedesco (o Internazionale) di seguito. Tuttavia, in questa fase, fai clic sulla relativa icona di configurazione (ingranaggio) per selezionare il tipo di metrica "Totale". Il formato deve essere "Percentuale". L'operatore deve essere "diviso per". La definizione della metrica è terminata:

   ![](assets/cm_metric_total.png)

1. Applica questa metrica al progetto:

   ![](assets/cm_percent_total.png)

## Compare Differences in Percentages (using Containers) {#section_13D6353259B74C09B37BA6378A501938}

Se desiderate vedere rapidamente le differenze più importanti tra Stati Uniti e comportamento di navigazione internazionale, potete creare un'altra metrica che sottrae le percentuali tra loro. A questo scopo, potete utilizzare la funzionalità Contenitore che funge da parentesi intorno ai 2 set di metriche.

1. In the [!UICONTROL Definition] canvas, click **[!UICONTROL Add]** &gt; **[!UICONTROL Container]**:

   ![](assets/cm_add_container.png)

1. Trascina la metrica " % of Total US Visitors" precedentemente creata nel primo contenitore, per passare alla definizione completa:

   ![](assets/cm_container_us.png)

1. Crea un altro contenitore di seguito e trascina in essa la metrica " % of Total International Visitors".
1. Cambia l'operatore tra i contenitori 2 a meno (-).

   ![](assets/cm_container_intl.png)

1. Salva la metrica (accertati di averla denominata qualcosa come "Differenza in % tra US e Int'l. ").
1. Quando viene applicata al rapporto, potete facilmente dove sono le differenze più importanti e ordinare il rapporto di conseguenza.

   ![](assets/cm_diff_percent.png)

