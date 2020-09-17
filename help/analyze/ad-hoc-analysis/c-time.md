---
description: Il tempo è una dimensione di reporting utile per le tendenze in ore, giorni, settimane e intervalli di date. Ad esempio, in un rapporto sui prodotti viene visualizzato il fatturato prodotto durante l'intervallo di date selezionato. Puoi aggiungere una dimensione Giorno per visualizzare la tendenza in tutti i giorni del periodo di reporting. Il tempo fornisce le impostazioni di granularità Ora, Giorno, Settimana, Mese, Trimestre e Anno. I predefiniti per intervalli di date includono impostazioni quali Oggi, Ieri e Ultimi 7 giorni.
title: Tempo
uuid: a6efbf80-342c-4aeb-80f3-91a3dbdbd33c
translation-type: tm+mt
source-git-commit: d4cb2acb4ecaecce3644a2f3cf29913440e5cd6a
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 3%

---


# Tempo

>[!IMPORTANT]
>
> Adobe sta spostando  Ad Hoc Analysis a fine ciclo di vita il 1 marzo 2021. [Ulteriori informazioni...](https://adobe.ly/discoverworkspace).

Il tempo è una dimensione di reporting utile per le tendenze in ore, giorni, settimane e intervalli di date. Ad esempio, in un rapporto sui prodotti viene visualizzato il fatturato prodotto durante l&#39;intervallo di date selezionato. Puoi aggiungere una dimensione Giorno per visualizzare la tendenza in tutti i giorni del periodo di reporting. Il tempo fornisce le impostazioni di granularità Ora, Giorno, Settimana, Mese, Trimestre e Anno. I predefiniti per intervalli di date includono impostazioni quali Oggi, Ieri e Ultimi 7 giorni.

## Tempo {#concept_CB64A0A2150C471FB0B0B42516905887}

Il tempo è una dimensione di reporting utile per le tendenze in ore, giorni, settimane e intervalli di date. Ad esempio, in un rapporto sui prodotti viene visualizzato il fatturato prodotto durante l&#39;intervallo di date selezionato. Puoi aggiungere una dimensione Giorno per visualizzare la tendenza in tutti i giorni del periodo di reporting. Il tempo fornisce le impostazioni di granularità Ora, Giorno, Settimana, Mese, Trimestre e Anno. I predefiniti per intervalli di date includono impostazioni quali Oggi, Ieri e Ultimi 7 giorni.

Per aggiungere le dimensioni Tempo, trascinare uno o più intervalli di date dal riquadro dello strumento Ora alla tabella del rapporto o al Generatore di tabelle.

Questo esempio mostra una dimensione Giorno con tendenze con entrate.

![](assets/day_dimension.png)

## Tempo - Definizioni {#reference_6E718B78E437438E825DB9262086A987}

Nel riquadro Ora puoi selezionare intervalli di date e predefiniti di tendenze, quindi trascinare le selezioni nella griglia [!UICONTROL Table Builder] o dei rapporti.

<!-- 

r_time_panel.xml

 -->

| Campo | Definizione |
|--- |--- |
| Intervalli di date | Consente di selezionare uno o più periodi di tempo e trascinarli nel Generatore tabelle o nella griglia di report. Visualizzare i periodi di tempo come suddivisioni in righe o come intestazioni di colonna. Puoi selezionare periodi quali giorno, settimana, mese o intervalli di date personalizzati. Se utilizzi un calendario personalizzato in un SiteCatalyst, le suite di rapporti erediteranno tali impostazioni. |
| Tendenza | Consente di generare rapporti sulla tendenza per ora, giorno, settimana, mese e così via. Quando si trascinano gli elementi da Tendenza al rapporto, i dati vengono visualizzati in un&#39;impostazione temporale regolata dall&#39;intervallo di date specificato dal calendario. |
