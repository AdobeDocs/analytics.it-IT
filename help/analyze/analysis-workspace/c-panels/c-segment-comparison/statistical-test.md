---
description: Ciascuna tabella di confronto principale mostra un punteggio di differenza calcolato da vari test statistici, in base al confronto eseguito. Tuttavia, indipendentemente dal test utilizzato, il punteggio di differenza è incluso tra 0 e 1.
keywords: Analysis Workspace;Segment IQ
title: Test statistici utilizzati nel confronto dei segmenti
topic: Reports and analytics
uuid: c3f52470-5bfc-4e6b-8638-1c142b08d013
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '463'
ht-degree: 100%

---


# Test statistici utilizzati nel confronto dei segmenti

Ciascuna tabella di confronto principale mostra un punteggio di differenza calcolato da vari test statistici, in base al confronto eseguito. Tuttavia, indipendentemente dal test utilizzato, il punteggio di differenza è incluso tra 0 e 1.

Un punteggio pari a 0 indica che non vi sono differenze tra i due segmenti, mentre 1 indica che la differenza tra i due segmenti è notevole. Esistono due tipi di test statistici impiegati per generare questo punteggio di differenza: per la tabella Metriche principali viene utilizzato il test U di Mann-Whitney, mentre per la tabella Elementi dimensione principali e Segmenti principali viene utilizzato un confronto delle differenze in termini di rischio.

## Punteggio di differenza delle metriche principali {#section_5E8047464EB945C78543B25F8F30F17A}

Nella tabella Metriche principali, lo Strumento di confronto segmenti utilizza un test U di Mann-Whitney di due campioni, che è un test di uguaglianza non parametrica impiegato per mettere a confronto le distribuzioni di probabilità unidimensionale di ciascuna metrica per ogni segmento considerato. Il punteggio di differenza nella tabella metriche è rappresentato da una combinazione del valore p ottenuto dalla statistica U calcolata (che rappresenta il modo in cui i due segmenti si distribuiscono in modo stocasticamente diverso in una data metrica) e la grandezza relativa della differenza osservata. Un punteggio di differenza elevato (vicino a 1) indica che la metrica in questione presenta una differenza relativa importante e una elevata attendibilità statistica, che attesta la diversità dei segmenti.

## Punteggi di differenza relativi a elementi di dimensione principali e segmenti principali {#section_8073ADA6053B44C9A23FDC5ED4AF2AC4}

Per calcolare il punteggio di differenza sulle tabelle Elementi dimensione principali e Differenza segmento principale, viene impiegato un algoritmo di differenziazione del rischio relativo (simile al rapporto di rischio, anche se si utilizza una differenza e non un rapporto). Una differenza di rischio viene calcolata sottraendo le incidenze cumulative di un elemento della dimensione (o sovrapponendolo con un segmento dalla relativa tabella) di un segmento selezionato dall’altro. Un punteggio di differenza elevato (vicino a 1) indica che l’elemento della dimensione in questione o il terzo segmento erano molto evidenti in uno dei segmenti selezionati e non nell’altro.

>[!NOTE]
>
>In tutte e tre le tabelle, la statistica della differenza si basa su un campione appropriato di visitatori per consentire al processo di funzionare nel modo più veloce possibile, mantenendo al tempo stesso l’accuratezza statistica. Mentre il punteggio di differenza si basa su un campione, i risultati mostrati nella tabella non sono sottoposti a campionamento. Per garantire significatività statistica, ciascun test statistico si basa su un algoritmo di assegnazione dinamica, in modo che il segmento più piccolo contenga una dimensione del campione che offre meno del 3% di margine di errore. Se un segmento contiene pochissimi visitatori (meno di 1.000), utilizziamo tutti i dati disponibili e non eseguiamo il campionamento durante il calcolo del punteggio di differenza.
