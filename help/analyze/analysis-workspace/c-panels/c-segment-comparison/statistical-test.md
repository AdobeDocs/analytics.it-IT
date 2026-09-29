---
description: Scopri come i test statistici vengono utilizzati nel confronto dei segmenti.
keywords: Analysis Workspace, segmento IQ
title: Test Statistici Utilizzati Nel Confronto Dei Segmenti
feature: Segmentation
role: User, Admin
exl-id: b1c235ca-2eab-48d2-bf11-e8a8c4067d03
TQID: 'https://experienceleague.adobe.com/49kZ6LC9OMizQvqxE2PCq1LtqhUHtf5iKQUgpgqSmmE'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: e38cbddc-1633-4cd5-bed5-9f289f2a6029
    internal-label: Panels
  - id: c47a19a5-f47b-4e53-afe0-e230da195ebe
    internal-label: Segmentation
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 9%
---
# Test statistici utilizzati nel confronto dei segmenti

Ciascuna delle tabelle di confronto principali mostra un punteggio di differenza. Tale punteggio è calcolato da diversi test statistici in base al confronto effettuato. Tuttavia, indipendentemente dal test utilizzato, il punteggio di differenza viene visualizzato come un valore compreso tra 0 e 1.

Un punteggio pari a 0 significa che non c’è differenza tra i due segmenti e un punteggio pari a 1 significa che c’è stata una differenza molto grande tra i due segmenti. Esistono due tipi di test statistici utilizzati per generare questi punteggi di differenza:

* Per la tabella **[!UICONTROL Top Metrics]** viene utilizzato un test U Mann-Whitney,
* Per la tabella **[!UICONTROL Top Dimension Items]** e **[!UICONTROL Top Segments]** viene utilizzato un confronto delle differenze di rischio.

## Punteggio di differenza delle metriche principali

Nella tabella Metriche principali, lo strumento Confronto segmenti utilizza due esempi di test U Mann-Whitney. Questo test è un test di uguaglianza non parametrico utilizzato per confrontare le distribuzioni di probabilità unidimensionali di ogni metrica per ogni segmento considerato. Il punteggio di differenza nella tabella delle metriche è una combinazione del valore p dalla statistica U calcolata (che rappresenta la differenza stocastica tra i due segmenti distribuiti in una particolare metrica) e la grandezza relativa della differenza osservata. Un punteggio di differenza elevato (vicino a 1) significa che una particolare metrica ha una differenza relativa grande e un’elevata affidabilità statistica che i segmenti sono diversi.

## Punteggi di differenza relativi a elementi di dimensione principali e segmenti principali

Per calcolare il punteggio di differenza nelle tabelle Principali elementi di Dimension e Differenza segmento superiore, viene utilizzato un algoritmo di differenza del rischio relativo (simile al rapporto di rischio, ma utilizzando una differenza anziché un rapporto). Una differenza di rischio viene calcolata sottraendo le incidenze cumulative di un elemento dimensione (o sovrapposizione con un segmento dalla tabella dei segmenti) di un segmento selezionato dall’altro. Un punteggio di differenza elevato (vicino a 1) significa che il particolare elemento dimensionale o segmento terziario era molto prominente in uno dei segmenti selezionati e non nell’altro.

>[!NOTE]
>
>In tutte e tre le tabelle, la statistica della differenza si basa su un campione appropriato di visitatori per consentire al processo di funzionare nel modo più veloce possibile, mantenendo al tempo stesso l’accuratezza statistica. Anche se il punteggio di differenza si basa su un campione, i risultati presentati nella tabella non vengono campionati. Per garantire la significatività statistica, ogni test statistico si basa su un algoritmo di allocazione dinamica in modo che il segmento più piccolo contenga una dimensione del campione che fornisce un margine di errore inferiore al 3%. Se un segmento contiene un numero molto limitato di visitatori (meno di 1.000), per calcolare il punteggio di differenza vengono utilizzati tutti i dati disponibili invece del campione.
