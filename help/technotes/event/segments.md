---
title: Esclusione di date specifiche nell’analisi
description: Suggerimenti per escludere date o intervalli di date se non desideri includerli nei rapporti.
exl-id: 744666c0-17f3-443b-9760-9c8568bec600
source-git-commit: d03206b127e16cbb98d1318b0acc6c304f91ca48
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 2%

---

# Esclusione di date specifiche nell’analisi

Se disponi di dati [interessato da un evento](overview.md), puoi utilizzare un segmento per escludere qualsiasi intervallo di date che non desideri includere nei rapporti. La segmentazione delle date interessate dall’evento può essere utile per evitare che l’organizzazione prenda decisioni sui dati parziali.

## Isolare i giorni interessati {#isolate}

Crea un segmento che isola l’intervallo di giorni o date interessato. Questo segmento è utile se desideri concentrarti sui giorni problematici per visualizzare ulteriori informazioni sul suo impatto.

1. Apri il generatore di segmenti andando in **[!UICONTROL Components]** > **[!UICONTROL Segments]**, quindi fai clic su **[!UICONTROL Add]**.
2. Trascina la dimensione &quot;Giorno&quot; nell’area di lavoro della definizione e impostala come giorno da isolare.
3. Ripeti il passaggio precedente per ogni giorno che desideri isolare nel rapporto.

![Segmento giorni interessati](assets/affected_days.jpg)

>[!TIP]
>
>Per modificare l&#39;istruzione OR in un&#39;istruzione AND, fare clic sulla freccia rivolta verso il basso accanto a OR e selezionare AND.

Adobe consiglia di utilizzare i componenti dimensione arancione e non i componenti intervallo date viola. Se utilizzi componenti di intervallo date viola, ignorano l’intervallo di calendario del progetto:

![Escludere il tipo di giorno del segmento](assets/exclude_segment_day_type.jpg)

## Escludere i giorni interessati {#exclude}

Crea un segmento che escluda l’intervallo di giorni o date interessato. Questo segmento è utile se desideri escludere i giorni in cui si sono verificati problemi per ridurre al minimo l’impatto sulla generazione di rapporti complessiva.

1. Apri il generatore di segmenti andando in **[!UICONTROL Components]** > **[!UICONTROL Segments]**, quindi fai clic su **[!UICONTROL Add]**.
2. Nell’area di lavoro della definizione del segmento in alto a destra, fai clic su **[!UICONTROL Options]** > **[!UICONTROL Exclude]**.
3. Trascina la dimensione &quot;Giorno&quot; nell’area di lavoro della definizione e impostala come giorno da rimuovere.
4. Ripeti il passaggio precedente per ogni giorno che desideri rimuovere nel rapporto.

![Escludere i giorni interessati](assets/exclude_affected_days.jpg)

## Utilizzare questi segmenti nei rapporti

Una volta creato il segmento di esclusione, puoi utilizzarlo esattamente come faresti con altri segmenti.

### Confrontare i segmenti in un rapporto con tendenze {#compare}

Puoi applicare sia il segmento &quot;Giorni interessati&quot; che il segmento &quot;Escludi giorni interessati&quot; in un rapporto per confrontarli uno accanto all’altro. Trascina entrambi i segmenti sopra o sotto una metrica per confrontarli:

![Entrambi i segmenti](assets/affected_and_exclude.png)

Se non desideri mostrare zeri nella tabella o nelle visualizzazioni (con conseguente calo), abilita **[!UICONTROL Interpret zero as no value]** in impostazioni colonna.

![Interpreta zero](assets/interpret_zero.png)

Se non desideri mostrare zeri nella tabella o nelle visualizzazioni (con conseguente calo), abilita **[!UICONTROL Interpret zero as no value]** in impostazioni colonna.

![Interpreta zero](assets/interpret_zero.png)

### Applicare il segmento di esclusione a un progetto {#apply}

Puoi applicare il segmento &quot;Escludi giorni interessati&quot; a un progetto Workspace. Trascina il segmento di esclusione nella sezione Area di lavoro con etichetta *Rilascia un segmento qui*.

>[!TIP]
>
>Includi una nota sui dati esclusi nella descrizione del pannello per aiutare quelli che visualizzano il rapporto. Fai clic con il pulsante destro del mouse sul titolo di un pannello, quindi fai clic su **[!UICONTROL Edit description]**.

![Segmento applicato a un pannello](assets/exclude_segment_panel.jpg)

### Utilizzare il segmento di esclusione in una suite di rapporti virtuale {#use-vrs}

Puoi utilizzare il segmento in una [suite di rapporti virtuale](/help/components/vrs/vrs-about.md) per escludere i dati in modo più conveniente. Questa opzione è ideale in quanto non ti devi ricordare di applicare il segmento per ogni rapporto che include l’intervallo di date interessato. Se utilizzi già le suite di rapporti virtuali come origine principale di dati, puoi aggiungere il segmento a una VRS esistente.

1. Passa a **[!UICONTROL Components]** > **[!UICONTROL Virtual report suites]**.
2. Fai clic su **[!UICONTROL Add]**.
3. Immetti il nome e la descrizione desiderati per la suite di rapporti virtuali.
4. Trascina il segmento di esclusione nell’area etichettata **[!UICONTROL Add segment]**.
5. Fai clic su **[!UICONTROL Continue]** in alto a destra, quindi fai clic su **[!UICONTROL Save]**.

![Segmento applicato a VRS](assets/exclude_segment_vrs.png)
