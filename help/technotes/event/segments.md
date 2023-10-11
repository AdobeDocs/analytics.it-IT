---
title: Esclusione di date specifiche nell’analisi
description: Suggerimenti per escludere date o intervalli di date se non si desidera includerli nei rapporti.
exl-id: 744666c0-17f3-443b-9760-9c8568bec600
feature: Event, Segmentation
source-git-commit: 266cf18050d60f08f7e170c56453d1e1d805cb7b
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 2%

---

# Esclusione di date specifiche nell’analisi

Se si dispone di dati [interessato da un evento](overview.md), puoi utilizzare un segmento per escludere eventuali intervalli di date che non desideri includere nei rapporti. La segmentazione delle date interessate dagli eventi può aiutare a evitare che l’organizzazione prenda decisioni su dati parziali.

## Isolare giorni interessati {#isolate}

Crea un segmento che isola il giorno o l’intervallo di date interessato. Questo segmento è utile se desideri concentrarti solo sui giorni problematici per visualizzare ulteriori informazioni sul suo impatto.

1. Apri il generatore di segmenti andando su **[!UICONTROL Components]** > **[!UICONTROL Segments]**, quindi fai clic su **[!UICONTROL Add]**.
2. Trascina la dimensione &quot;Giorno&quot; nell’area di lavoro delle definizioni e impostala in modo che corrisponda al giorno da isolare.
3. Ripeti il passaggio precedente per ogni giorno che desideri isolare nel rapporto.

![Segmento giorni interessati](assets/affected_days.jpg)

>[!TIP]
>
>Per modificare l&#39;istruzione OR in un&#39;istruzione AND, fare clic sulla freccia in giù accanto a OR e selezionare AND.

L’Adobe consiglia di utilizzare i componenti dimensione arancione e non i componenti intervallo date viola. Se utilizzi componenti di intervallo date viola, questi sovrascrivono l’intervallo di calendario del progetto:

![Escludi tipo di giorno segmento](assets/exclude_segment_day_type.jpg)

## Escludi giorni interessati {#exclude}

Crea un segmento che escluda il giorno o l’intervallo di date interessato. Questo segmento è utile se desideri escludere i giorni in cui si sono verificati problemi al fine di ridurre al minimo l’impatto sul reporting complessivo.

1. Apri il generatore di segmenti andando su **[!UICONTROL Components]** > **[!UICONTROL Segments]**, quindi fai clic su **[!UICONTROL Add]**.
2. Nell’area di lavoro di definizione del segmento in alto a destra, fai clic su **[!UICONTROL Options]** > **[!UICONTROL Exclude]**.
3. Trascina la dimensione &quot;Giorno&quot; nell’area di lavoro delle definizioni e impostala in modo che corrisponda al giorno da rimuovere.
4. Ripeti il passaggio precedente per ogni giorno che desideri rimuovere nel rapporto.

![Escludi giorni interessati](assets/exclude_affected_days.jpg)

## Utilizzare questi segmenti nei rapporti

Una volta creato il segmento di esclusione, puoi utilizzarlo esattamente come si farebbe con altri segmenti.

### Confrontare segmenti in un rapporto con tendenze {#compare}

Puoi applicare in un rapporto sia il segmento &quot;Giorni interessati&quot; che il segmento &quot;Escludi giorni interessati&quot; per confrontarli uno accanto all’altro. Trascina entrambi i segmenti sopra o sotto una metrica per confrontarli:

![Entrambi i segmenti](assets/affected_and_exclude.png)

Se non desideri visualizzare gli zeri nella tabella o nelle visualizzazioni (causando calo), abilita **[!UICONTROL Interpret zero as no value]** in impostazioni colonna.

![Interpreta zero](assets/interpret_zero.png)

Se non desideri visualizzare gli zeri nella tabella o nelle visualizzazioni (causando calo), abilita **[!UICONTROL Interpret zero as no value]** in impostazioni colonna.

![Interpreta zero](assets/interpret_zero.png)

### Applicare il segmento di esclusione a un progetto {#apply}

Puoi applicare il segmento &quot;Escludi giorni interessati&quot; a un progetto Workspace. Trascina il segmento da escludere nella sezione dell’area di lavoro etichettata *Rilascia qui un segmento*.

>[!TIP]
>
>Includi una nota sui dati esclusi nella descrizione del pannello per facilitare la visualizzazione del rapporto. Fai clic con il pulsante destro del mouse sul titolo di un pannello, quindi fai clic su **[!UICONTROL Edit description]**.

![Segmento applicato a un pannello](assets/exclude_segment_panel.jpg)

### Utilizzare il segmento di esclusione in una suite di rapporti virtuale {#use-vrs}

Puoi utilizzare il segmento in una [suite di rapporti virtuale](/help/components/vrs/vrs-about.md) per escludere i dati in modo più comodo. Questa opzione è ideale in quanto non è necessario ricordarsi di applicare il segmento per ogni rapporto che include l’intervallo di date interessato. Se utilizzi già suite di rapporti virtuali come origine di dati principale, puoi aggiungere il segmento a una suite di rapporti virtuale esistente.

1. Passa a **[!UICONTROL Components]** > **[!UICONTROL Virtual report suites]**.
2. Fai clic su **[!UICONTROL Add]** (Usa modello di attribuzione non predefinito).
3. Immetti il nome e la descrizione desiderati per la suite di rapporti virtuali.
4. Trascina il segmento di esclusione nell’area etichettata **[!UICONTROL Add segment]**.
5. Clic **[!UICONTROL Continue]** in alto a destra, quindi fai clic su **[!UICONTROL Save]**.

![Segmento applicato alla suite di rapporti virtuale](assets/exclude_segment_vrs.png)
