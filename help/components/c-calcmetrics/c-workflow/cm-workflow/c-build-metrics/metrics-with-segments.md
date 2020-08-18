---
description: La segmentazione di singole metriche consente di effettuare confronti tra metriche all'interno dello stesso rapporto. (Solo metriche derivate)
title: Metriche segmentate
uuid: 88f9829b-76e4-4598-9494-084a91602bc1
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 1%

---


# Metriche segmentate

La segmentazione di singole metriche consente di effettuare confronti tra metriche all&#39;interno dello stesso rapporto. (Solo metriche derivate)

## Confronto segmenti {#section_29A6E0070F084BFDB6228FA9CE106F48}

Supponiamo che tu voglia confrontare diversi aspetti di un segmento &quot;Visitatori statunitensi&quot; con quelli di un segmento &quot;Visitatori internazionali&quot;. Puoi creare metriche che ti forniranno informazioni approfondite, come:

* Qual è il comportamento di esplorazione dei contenuti rispetto ai due gruppi? (Un altro esempio potrebbe essere: Come si confronta il tasso di conversione tra i due segmenti?)
* In percentuale del totale dei visitatori, quanti visitatori USA sfogliano determinate pagine rispetto ai visitatori internazionali?
* Quali sono le maggiori differenze in termini di accesso al contenuto da parte di questi diversi segmenti?

Esploriamo la prima domanda: Qual è il comportamento di esplorazione dei contenuti rispetto ai due gruppi?

1. Se non hai un segmento comparabile, crea un segmento interno direttamente nel Generatore di metrica calcolata denominato &quot;Visitatori tedeschi&quot;, dove &quot;Paesi&quot; è uguale a &quot;Germania&quot;. Trascina la dimensione Paesi nel quadro Definizione e seleziona la Germania come valore:

   ![](assets/segment-from-dimension.png)

   >[!NOTE]
   >
   >Potete eseguire questa operazione anche nel Generatore [di](/help/components/segmentation/segmentation-workflow/seg-build.md)segmenti, ma abbiamo semplificato il flusso di lavoro rendendo disponibili le dimensioni nel Generatore di metrica calcolata.

   >[!NOTE]
   >
   >&quot;Internal&quot; indica che il segmento non è visibile nell&#39; **[!UICONTROL Segments]** elenco nella barra a sinistra. Tuttavia, potete renderlo pubblico passando il puntatore del mouse sull&#39;icona &quot;i&quot; accanto ad essa e facendo clic **[!UICONTROL Make public]**.

1. Se non hai un segmento paragonabile, crea un segmento denominato &quot;Visitatori internazionali&quot; in cui &quot;Paesi&quot; non equivale a &quot;Germania&quot;.
1. Crea e salva una metrica denominata &quot;Visitatori tedeschi&quot; trascinando il segmento Germania nell’area di lavoro Definizione e trascinando la metrica Visitatori unici al suo interno:

   ![](assets/german-visitors.png)

1. Ripetete il Passaggio 3 con il segmento Visitatori internazionali e la metrica Visitatori unici per creare una metrica Visitatori internazionali.
1. In  Analysis Workspace, trascina l’ **[!UICONTROL Page]** Dimension in una tabella a forma libera e trascina le due nuove metriche calcolate l’una accanto all’altra verso l’alto:

   ![](assets/workspace-pages.png)

1. In [!UICONTROL Reports & Analytics]alternativa, apri il [!UICONTROL Pages] rapporto e fai clic su **[!UICONTROL Show Metrics]**, quindi applica le nuove metriche segmentate Visitatori USA e Visitatori internazionali per vedere il confronto tra il loro comportamento di navigazione dei contenuti.

   ![](assets/pages-report.png)

## Confronta percentuali di totali {#section_846CB89725F04388AE0352DB20189EE8}

Potete introdurre un altro livello di richiesta confrontando il comportamento di navigazione dei visitatori in percentuali normalizzate. Per farlo, crea due nuove metriche, &quot;% del totale dei visitatori tedeschi&quot; e &quot;% del totale dei visitatori internazionali&quot;:

1. Trascina il segmento Visitatori tedeschi (o internazionali) nel quadro.
1. Rilascia di seguito un altro segmento Visitatori tedeschi (o internazionali). Tuttavia, stavolta fai clic sull’icona di configurazione (ingranaggio) per selezionare il tipo di metrica &quot;Totale&quot;. Il formato deve essere &quot;Percent&quot;. L&#39;operatore deve essere &quot;diviso per&quot;. Si conclude con questa definizione di metrica:

   ![](assets/cm_metric_total.png)

1. Applica questa metrica al progetto:

   ![](assets/cm_percent_total.png)

## Confronta differenze in percentuali (utilizzando i contenitori) {#section_13D6353259B74C09B37BA6378A501938}

Se si desidera visualizzare rapidamente le maggiori differenze tra il comportamento di esplorazione statunitense e internazionale, è possibile creare un&#39;altra metrica che sottrae le percentuali l&#39;una dall&#39;altra. A tal fine, puoi utilizzare la funzionalità Contenitore che agisce efficacemente come parentesi intorno ai due set di metriche.

1. In the [!UICONTROL Definition] canvas, click **[!UICONTROL Add]** > **[!UICONTROL Container]**:

   ![](assets/cm_add_container.png)

1. Rilascia la metrica &quot;% del totale dei visitatori negli Stati Uniti&quot; creata in precedenza nel primo contenitore, che si espande fino alla definizione completa:

   ![](assets/cm_container_us.png)

1. Crea un altro contenitore qui sotto e trascina la metrica &quot;% del totale dei visitatori internazionali&quot;.
1. Cambia l&#39;operatore tra i 2 contenitori in un segno meno (-).

   ![](assets/cm_container_intl.png)

1. Salvate la metrica (accertatevi di averla denominata &quot;Difference in % tra USA e Int&#39;l.&quot;).
1. Se applicato al rapporto, è possibile individuare facilmente le maggiori differenze in percentuale e ordinare il rapporto di conseguenza.

   ![](assets/cm_diff_percent.png)

