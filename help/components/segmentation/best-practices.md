---
title: Best practice di segmentazione
description: Crea segmenti ottimali in grado di restituire i dati in modo efficiente.
translation-type: ht
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: ht
source-wordcount: '296'
ht-degree: 100%

---


# Best practice di segmentazione

I segmenti complessi sono spesso necessari per ottenere i dati desiderati. Se i segmenti complessi sono inefficienti e vengono utilizzati in una suite di rapporti di grandi dimensioni, l’esecuzione dei rapporti richiederà molto più tempo. Quando crei o modifichi un segmento, prendi in considerazione le seguenti risorse per minimizzare la complessità.

## Utilizzare l’operatore “Contains” solo come ultima risorsa

L’operatore “Contains” (contiene) è una delle funzioni di elaborazione più complesse nella segmentazione, in quanto deve analizzare l’intero contenuto di ogni valore. Considera l’utilizzo di altri operatori, ad esempio “Starts with” o “Ends with”, se i valori desiderati si trovano all’inizio o alla fine di una stringa.

Se l’operatore “Contains” in un segmento restituisce un gran numero di risultati, in genere si verifica un timeout del rapporto. Ad esempio, se hai creato un segmento in cui `Referrer equals "."`, il segmento esegue ricerche nel contenuto di ogni valore. Valuta la possibilità di utilizzare l’operatore “Exists” al posto di “Contains”.

## Utilizzare le classificazioni per raggruppare gli elementi dimensionali

Se un segmento ha molte condizioni, queste possono rapidamente degradare le prestazioni del segmento. Ad esempio, `Page equals X or Page equals Y or Page equals Z` ripetuto con centinaia di valori diversi. Invece di scrivere queste centinaia di condizioni, classifica tutti i valori desiderati in un segmento, quindi usa il valore classificato in un segmento.

1. Crea una classificazione per la variabile con cui stai lavorando.
2. Scarica il modello di classificazione e aprilo nel foglio di calcolo o nell’editor di testo desiderato.
3. Attribuisci lo stesso valore a ogni elemento dimensionale che desideri includere nel segmento.
4. Utilizza l’importazione di classificazioni per importare nuovamente il foglio di calcolo in Adobe Analytics.
5. Al termine dell’elaborazione della classificazione, crea un segmento utilizzando il valore classificato.

Questo metodo migliora drasticamente le prestazioni e fornisce un modo semplice per modificare le condizioni dei segmenti. Invece di modificare il segmento con valori diversi, puoi aggiungere o rimuovere elementi dimensionali dalla classificazione.
