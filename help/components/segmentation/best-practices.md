---
title: Best practice di segmentazione
description: Crea segmenti ottimali che restituiscono i dati in modo efficiente.
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 0%

---


# Best practice di segmentazione

I segmenti complessi sono spesso necessari per ottenere i dati desiderati. Se segmenti complessi sono inefficienti e vengono utilizzati in una suite di rapporti di grandi dimensioni, l&#39;esecuzione dei report richiederà molto più tempo. Quando crei o modifichi un segmento, prendi in considerazione le seguenti risorse per ridurre al minimo la complessità.

## Utilizzate solo l&#39;operatore &#39;Contains&#39; come ultima risorsa

L&#39;operatore &#39;Contiene&#39; è una delle funzioni di elaborazione più complesse nella segmentazione, in quanto deve analizzare l&#39;intero contenuto di ogni valore. Considerare l&#39;utilizzo di altri operatori, ad esempio &quot;Inizia con&quot; o &quot;Termina con&quot;, se i valori desiderati si trovano all&#39;inizio o alla fine di una stringa.

Se l&#39;operatore &#39;Contiene&#39; in un segmento restituisce un gran numero di risultati, il rapporto si verifica in genere un timeout. Ad esempio, se hai creato un segmento in cui `Referrer equals "."`il segmento cerca il contenuto di ogni valore. Valutare la possibilità di utilizzare l&#39;operatore &quot;Exists&quot;.

## Uso delle classificazioni per raggruppare gli elementi dimensionali

Se hai molte condizioni di segmento, possono rapidamente degradare le prestazioni del segmento. Ad esempio, `Page equals X or Page equals Y or Page equals Z` ripetuto con centinaia di valori diversi. Invece di scrivere queste centinaia di condizioni, classifica tutti i valori desiderati in un segmento, quindi usa il valore classificato in un segmento.

1. Create una classificazione per la variabile con cui state lavorando.
2. Scaricate il modello di classificazione e apritelo nel foglio di calcolo o nell’editor di testo desiderato.
3. Attribuite a ogni elemento di dimensione che desiderate includere nel segmento lo stesso valore.
4. Utilizzate Importazione classificazioni per importare nuovamente il foglio di calcolo in  Adobe Analytics
5. Al termine dell&#39;elaborazione della classificazione, crea un segmento utilizzando il valore classificato.

Questo metodo aumenta drasticamente le prestazioni e fornisce un modo semplice per modificare le condizioni del segmento. Invece di modificare il segmento con valori diversi, puoi aggiungere o rimuovere elementi dimensione dalla classificazione.
