---
title: Best practice
description: Scopri alcune best practice per la segmentazione.
feature: Segmentation
exl-id: 4115a804-5063-430a-b9d3-2b64b26ca4d8
source-git-commit: 35f2812c1a1a4eed090e04d67014fcebf88a80ec
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 63%

---

# Best practice di segmentazione

I segmenti complessi sono spesso necessari per ottenere i dati desiderati. Se i segmenti complessi sono inefficienti e vengono utilizzati in una suite di rapporti di grandi dimensioni, l’esecuzione dei rapporti richiederà molto più tempo. Quando crei o modifichi un segmento, prendi in considerazione le seguenti risorse per minimizzare la complessità.

## Utilizza l&#39;operatore `Contains` solo come ultima risorsa

L&#39;operatore [**[!UICONTROL Contains]**](/help/components/segmentation/seg-reference/seg-operators.md) è una delle funzionalità di elaborazione più complesse della segmentazione, in quanto l&#39;operatore deve analizzare l&#39;intero contenuto di ogni valore. Prendere in considerazione l&#39;utilizzo di altri operatori come **[!UICONTROL Starts with]**&#x200B;o **[!UICONTROL Ends with]**&#x200B;se i valori desiderati si trovano all&#39;inizio o alla fine di una stringa.

Se un operatore **[!UICONTROL Contains]** in un segmento restituisce un numero elevato di risultati, in genere si verifica un timeout del rapporto. Ad esempio, se hai creato un segmento in cui **[!UICONTROL Referrer]** **[!UICONTROL equals]** `"."`, il segmento esegue ricerche nel contenuto di ogni valore. Valuta l&#39;utilizzo dell&#39;operatore **[!UICONTROL Exists]**.

## Utilizzare le classificazioni per raggruppare gli elementi dimensionali

Se un segmento ha molte condizioni, queste possono rapidamente degradare le prestazioni del segmento. Ad esempio, **[!UICONTROL Page]** **[!UICONTROL equals]** `X` **[!UICONTROL OR]** **[!UICONTROL Page]** **[!UICONTROL equals]** `Y` **[!UICONTROL OR]** **[!UICONTROL Page]** **[!UICONTROL equals]** `Z` ripetuto con centinaia di valori diversi. Invece di scrivere queste centinaia di condizioni, classifica tutti i valori desiderati in un segmento, quindi usa il valore classificato in un segmento.

1. Crea una classificazione per la variabile con cui stai lavorando.
2. Scarica il modello di classificazione e aprilo nel foglio di calcolo o nell’editor di testo desiderato.
3. Attribuisci lo stesso valore a ogni elemento dimensionale che desideri includere nel segmento.
4. Utilizza l’importazione di classificazioni per importare nuovamente il foglio di calcolo in Adobe Analytics.
5. Al termine dell’elaborazione della classificazione, crea un segmento utilizzando il valore classificato.

Questo metodo migliora drasticamente le prestazioni e fornisce un modo semplice per modificare le condizioni dei segmenti. Invece di modificare il segmento con valori diversi, puoi aggiungere o rimuovere elementi dimensionali dalla classificazione.
