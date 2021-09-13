---
description: 'La segmentazione sulle singole metriche consente di effettuare confronti tra metriche all’interno dello stesso rapporto. '
title: Metriche segmentate
uuid: 88f9829b-76e4-4598-9494-084a91602bc1
exl-id: 1e7e048b-9d90-49aa-adcc-15876c864e04
source-git-commit: 244f839235f55b7f8873864ced3d5adc2394b631
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 0%

---

# Metriche segmentate

Nel generatore di metriche calcolate puoi applicare segmenti all’interno della definizione della metrica. È utile se desideri derivare nuove metriche da utilizzare nell’analisi. Tieni presente che le definizioni dei segmenti possono essere aggiornate tramite il Generatore di segmenti. Se vengono apportate modifiche, il segmento viene aggiornato automaticamente ovunque viene applicato, anche se fa parte di una definizione di metrica calcolata.

![](assets/german-visitors.png)

## Creare una metrica segmentata {#create}

Supponiamo che desideri confrontare diversi aspetti di un segmento &quot;Visitatori tedeschi&quot; con quelli di un segmento &quot;Visitatori internazionali&quot;. Puoi creare metriche che ti daranno informazioni quali:

* Come si confronta il comportamento di navigazione dei contenuti tra i due gruppi? (Un altro esempio potrebbe essere: Come si confronta il tasso di conversione tra i due segmenti?)
* In percentuale del totale dei visitatori, quanti visitatori tedeschi navigano su determinate pagine rispetto ai visitatori internazionali?
* Dove sono le maggiori differenze in termini di quali contenuti sono accessibili da questi diversi segmenti?

1. Se non disponi di un segmento comparabile, crea un segmento adhoc nel Generatore di metrica calcolata denominato &quot;Visitatori tedeschi&quot;, dove &quot;Paesi&quot; è uguale a &quot;Germania&quot;. Trascina la dimensione Paesi nell&#39;area di lavoro Definizione e seleziona la Germania come valore:

   ![](assets/segment-from-dimension.png)

   >[!NOTE]
   >
   >Puoi eseguire questa operazione anche nel [Generatore di segmenti](/help/components/segmentation/segmentation-workflow/seg-build.md), ma abbiamo semplificato il flusso di lavoro rendendo disponibili le dimensioni nel Generatore di metriche calcolate. &quot;Adhoc&quot; indica che il segmento non è visibile nell’elenco **[!UICONTROL Segments]** nella barra a sinistra. Tuttavia, puoi renderlo pubblico passando con il mouse sull&#39;icona &quot;i&quot; accanto a essa e facendo clic su **[!UICONTROL Make public]**.

1. Se non hai un segmento comparabile, crea un segmento chiamato &quot;Visitatori internazionali&quot; in cui &quot;Paesi&quot; non è uguale a &quot;Germania&quot;.
1. Crea e salva una metrica denominata &quot;Visitatori tedeschi&quot; trascinando il segmento Germania nell’area di lavoro Definizione e trascinando la metrica Visitatori unici al suo interno:

   ![](assets/german-visitors.png)

1. Ripeti il Passaggio 3 con il segmento Visitatori internazionali e la metrica Visitatori unici per creare una metrica Visitatori internazionali.
1. In Analysis Workspace, trascina il Dimension **[!UICONTROL Page]** in una tabella a forma libera e trascina le due nuove metriche calcolate una accanto all’altra nella parte superiore:

   ![](assets/workspace-pages.png)

Ecco una panoramica video:

>[!VIDEO](https://video.tv.adobe.com/v/25407/?quality=12)

## Percentuale di metriche totali {#percent-total}

Puoi approfondire l’esempio precedente confrontando il segmento con una popolazione totale. Per farlo, crea due nuove metriche, &quot;% del totale dei visitatori tedeschi&quot; e &quot;% del totale dei visitatori internazionali&quot;:

1. Rilascia il segmento Visitatori tedeschi (o internazionali) nell’area di lavoro.
1. Rilascia un altro segmento Visitatori tedeschi (o internazionali) qui sotto. Tuttavia, stavolta fai clic sull’icona di configurazione (ingranaggio) per selezionare il tipo di metrica &quot;Totale&quot;. Il formato deve essere &quot;Percent&quot; (Percentuale). L&#39;operatore deve essere &quot;diviso per&quot;. Alla fine trovi questa definizione di metrica:

   ![](assets/cm_metric_total.png)

1. Applica questa metrica al progetto:

   ![](assets/cm_percent_total.png)
