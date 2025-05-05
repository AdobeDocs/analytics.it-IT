---
description: La segmentazione di singole metriche consente di effettuare confronti di metriche all’interno dello stesso rapporto.
title: Metriche segmentate
feature: Calculated Metrics
exl-id: 1e7e048b-9d90-49aa-adcc-15876c864e04
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 0%

---

# Metriche segmentate

Nel generatore di metriche calcolate, puoi applicare segmenti all’interno della definizione della metrica. Questa funzione è utile se desideri derivare nuove metriche da utilizzare nell’analisi. Tieni presente che le definizioni dei segmenti possono essere aggiornate tramite il Generatore di segmenti. Se vengono apportate modifiche, il segmento viene aggiornato automaticamente ovunque venga applicato, incluso se fa parte di una definizione di metrica calcolata.

![](assets/german-visitors.png)

## Creare una metrica segmentata {#create}

Supponiamo che tu voglia confrontare diversi aspetti di un segmento &quot;Visitatori tedeschi&quot; con quelli di un segmento &quot;Visitatori internazionali&quot;. Puoi creare metriche che ti forniranno informazioni approfondite, ad esempio:

* Come si confrontano i comportamenti di navigazione del contenuto tra i due gruppi? Un altro esempio potrebbe essere: come si confronta il tasso di conversione tra i due segmenti?
* Come percentuale del totale dei visitatori, quanti visitatori tedeschi navigano in determinate pagine rispetto ai visitatori internazionali?
* Quali sono le principali differenze in termini di contenuto a cui accedono questi diversi segmenti?

Crea e salva una metrica denominata &quot;Visitatori tedeschi&quot; e una metrica denominata &quot;Visitatori internazionali&quot;:

1. Crea un segmento ad hoc nel generatore di metriche calcolate denominato &quot;Visitatori tedeschi&quot;, dove &quot;Paesi&quot; è uguale a &quot;Germania&quot;.

   Trascina la dimensione Paesi nell&#39;area di lavoro Definizione e seleziona [!UICONTROL **Germania**] come valore:

   ![](assets/segment-from-dimension.png)

   >[!NOTE]
   >
   >Puoi eseguire questa operazione anche nel [Generatore di segmenti](/help/components/segmentation/segmentation-workflow/seg-build.md), ma il flusso di lavoro è stato semplificato rendendo disponibili le dimensioni nel generatore di metriche calcolate. &quot;Adhoc&quot; significa che il segmento non è visibile nell&#39;elenco **[!UICONTROL Segments]** nella barra a sinistra. È tuttavia possibile renderlo pubblico passando il puntatore sull&#39;icona &quot;i&quot; accanto a esso e facendo clic su **[!UICONTROL Make public]**.

1. Trascina il segmento Germania nell’area di lavoro Definizione e al suo interno trascina la metrica Visitatori univoci:

   ![](assets/german-visitors.png)

1. Seleziona [!UICONTROL **Salva**] per salvare la metrica calcolata.

1. Crea un segmento ad hoc nel generatore di metriche calcolate denominato &quot;Visitatori internazionali&quot;, dove &quot;Paesi&quot; non è uguale a &quot;Germania&quot;.

   Trascina la dimensione Paesi nell&#39;area di lavoro Definizione, seleziona [!UICONTROL **Germania**] come valore, quindi seleziona [!UICONTROL **è diverso**] come operatore.

1. Trascina la metrica Visitatori univoci al suo interno.

1. Seleziona [!UICONTROL **Salva**] per salvare la metrica calcolata.

1. In Analysis Workspace, trascina il Dimension **[!UICONTROL Page]** in una tabella a forma libera e trascina le due nuove metriche calcolate una accanto all&#39;altra nella parte superiore:

   ![](assets/workspace-pages.png)


>[!BEGINSHADEBOX]

Per un video demo, vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Metriche segmentate](https://video.tv.adobe.com/v/41661?quality=12&learn=on&captions=ita){target="_blank"}.

>[!ENDSHADEBOX]


## Percentuale delle metriche totali {#percent-total}

Per sviluppare ulteriormente l’esempio precedente, confronta il segmento con una popolazione totale. Per farlo, crea due nuove metriche, &quot;% del totale dei visitatori tedeschi&quot; e &quot;% del totale dei visitatori internazionali&quot;:

1. Rilascia il segmento Visitatori tedeschi (o internazionali) nell’area di lavoro.
1. Rilascia qui sotto un altro segmento di visitatori tedeschi (o internazionali). Tuttavia, questa volta, fai clic sulla relativa icona di configurazione (ingranaggio) per selezionare il tipo di metrica &quot;Totale&quot;. Il formato deve essere &quot;Percentuale&quot;. L’operatore deve essere &quot;diviso per&quot;. Alla fine trovi questa definizione di metrica:

   ![](assets/cm_metric_total.png)

1. Applica questa metrica al progetto:

   ![](assets/cm_percent_total.png)
