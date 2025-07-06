---
description: Scopri come i test statistici vengono utilizzati nel confronto dei segmenti.
keywords: Analysis Workspace, segmento IQ
title: Test Statistici Utilizzati Nel Confronto Dei Segmenti
feature: Segmentation
role: User, Admin
exl-id: b1c235ca-2eab-48d2-bf11-e8a8c4067d03
source-git-commit: b4c1636bdc9d5be522b16f945a46beabf4f7a733
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 44%

---

# Test statistici utilizzati nel confronto dei segmenti

Ciascuna delle tabelle di confronto principali mostra un punteggio di differenza. Tale punteggio è calcolato da diversi test statistici in base al confronto effettuato. Tuttavia, indipendentemente dal test utilizzato, il punteggio di differenza viene visualizzato come un valore compreso tra 0 e 1.

Un punteggio pari a 0 significa che non c’è differenza tra i due segmenti e un punteggio pari a 1 significa che c’è stata una differenza molto grande tra i due segmenti. Esistono due tipi di test statistici utilizzati per generare questi punteggi di differenza:

* Per la tabella **[!UICONTROL Top Metrics]** viene utilizzato un test U Mann-Whitney,
* Per la tabella **[!UICONTROL Top Dimension Items]** e **[!UICONTROL Top Segments]** viene utilizzato un confronto delle differenze di rischio.

## Punteggio di differenza delle metriche principali

Nella tabella Metriche principali, lo strumento Confronto segmenti utilizza due esempi di test U Mann-Whitney. Questo test è un test di uguaglianza non parametrico utilizzato per confrontare le distribuzioni di probabilità unidimensionali di ogni metrica per ogni segmento considerato. Il punteggio di differenza nella tabella metriche è rappresentato da una combinazione del valore p ottenuto dalla statistica U calcolata (che rappresenta il modo in cui i due segmenti si distribuiscono in modo stocasticamente diverso in una data metrica) e la grandezza relativa della differenza osservata. Un punteggio di differenza elevato (vicino a 1) significa che una particolare metrica ha una differenza relativa grande e un’elevata affidabilità statistica che i segmenti sono diversi.

## Punteggi di differenza relativi a elementi di dimensione principali e segmenti principali

Per calcolare il punteggio di differenza sulle tabelle Elementi dimensione principali e Differenza segmento principale, viene impiegato un algoritmo di differenziazione del rischio relativo (simile al rapporto di rischio, anche se si utilizza una differenza e non un rapporto). Una differenza di rischio viene calcolata sottraendo le incidenze cumulative di un elemento della dimensione (o sovrapponendolo con un segmento dalla relativa tabella) di un segmento selezionato dall’altro. Un punteggio di differenza elevato (vicino a 1) significa che il particolare elemento dimensionale o segmento terziario era molto prominente in uno dei segmenti selezionati e non nell’altro.

>[!NOTE]
>
>In tutte e tre le tabelle, la statistica della differenza si basa su un campione appropriato di visitatori per consentire al processo di funzionare nel modo più veloce possibile, mantenendo al tempo stesso l’accuratezza statistica. Mentre il punteggio di differenza si basa su un campione, i risultati mostrati nella tabella non sono sottoposti a campionamento. Per garantire significatività statistica, ciascun test statistico si basa su un algoritmo di assegnazione dinamica, in modo che il segmento più piccolo contenga una dimensione del campione che offre meno del 3% di margine di errore. Se un segmento contiene un numero molto limitato di visitatori (meno di 1.000), per calcolare il punteggio di differenza vengono utilizzati tutti i dati disponibili invece del campione.
