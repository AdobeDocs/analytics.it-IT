---
description: Ciascuna tabella di confronto principale mostra un punteggio di differenza calcolato da vari test statistici, in base al confronto eseguito. Tuttavia, indipendentemente dal test utilizzato, il punteggio di differenza è incluso tra 0 e 1.
keywords: Analysis Workspace;Segment IQ
title: Test statistici utilizzati nel confronto dei segmenti
topic: Reports and analytics
uuid: c3f52470-5bfc-4e6b-8638-1c142b08d013
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Test statistici utilizzati nel confronto dei segmenti

Ciascuna tabella di confronto principale mostra un punteggio di differenza calcolato da vari test statistici, in base al confronto eseguito. Tuttavia, indipendentemente dal test utilizzato, il punteggio di differenza è incluso tra 0 e 1.

Un punteggio pari a 0 indica che non c&#39;è differenza tra i due segmenti e un punteggio pari a 1 indica che c&#39;era una differenza molto grande tra i due segmenti. Esistono due tipi di test statistici impiegati per generare questo punteggio di differenza: per la tabella Metriche principali viene utilizzato il test U di Mann-Whitney, mentre per la tabella Elementi dimensione principali e Segmenti principali viene utilizzato un confronto delle differenze in termini di rischio.

## Punteggio di differenza delle metriche principali {#section_5E8047464EB945C78543B25F8F30F17A}

Nella tabella Metriche principali, lo Strumento di confronto segmenti utilizza un test U di Mann-Whitney di due campioni, che è un test di uguaglianza non parametrica utilizzato per confrontare le distribuzioni di probabilità unidimensionale di ciascuna metrica per ciascun segmento considerato. Il punteggio di differenza nella tabella delle metriche è una combinazione del valore p ottenuto dalla statistica U calcolata (che rappresenta il modo in cui i due segmenti sono distribuiti stocasticamente in una particolare metrica) e la grandezza relativa della differenza osservata. Un punteggio di differenza elevato (vicino a 1) indica che la metrica in questione presenta una differenza relativa elevata, oltre a un&#39;elevata confidenza statistica che attesta la diversità dei segmenti.

## Punteggi di differenza relativi a elementi di dimensione principali e segmenti principali {#section_8073ADA6053B44C9A23FDC5ED4AF2AC4}

Per calcolare il punteggio di differenza nelle tabelle Elementi dimensione principali e Differenza segmento principale, viene utilizzato un algoritmo di differenziazione del rischio relativo (simile al rapporto di rischio, anche se si utilizza una differenza anziché un rapporto). Una differenza di rischio viene calcolata sottraendo le incidenze cumulative di un elemento dimensione (o sovrapponendolo con un segmento dalla tabella del segmento) di un segmento selezionato dall&#39;altro. Un punteggio di differenza elevato (vicino a 1) indica che l’elemento dimensione o il terzo segmento era molto visibile in uno dei segmenti selezionati e non nell’altro.

>[!NOTE] In tutte e tre le tabelle, la statistica della differenza si basa su un campione appropriato di visitatori per consentire al processo di funzionare nel modo più veloce possibile, mantenendo al tempo stesso l’accuratezza statistica. Mentre il punteggio di differenza è basato su un campione, i risultati presentati nella tabella non vengono sottoposti a campionamento. Per garantire la significatività statistica, ogni test statistico si basa su un algoritmo di allocazione dinamica in modo che il segmento più piccolo contenga una dimensione del campione che fornisce meno del 3% di margine di errore. Se un segmento contiene pochissimi visitatori (meno di 1.000), utilizziamo tutti i dati disponibili e non eseguiamo il campionamento per calcolare il punteggio di differenza.
