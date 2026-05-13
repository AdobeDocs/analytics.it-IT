---
title: Elementi Dimension Dinamici E Statici
description: Scopri come utilizzare gli elementi dimensionali dinamici e statici nelle tabelle a forma libera in Analysis Workspace.
feature: Freeform Tables
role: User, Admin
exl-id: 4cdc93b5-67ed-46a4-ba9f-a96e640da9d9
TQID: https://experienceleague.adobe.com/hP5X4gRBiRB1wmGziYT25iGS-Enpuu0C--3qeGxrvb4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
  - id: e318d41c-1d01-4c1e-9b18-1f61d435ceee
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 570
ht-degree: 38%

---

# Elementi dimensionali dinamici e statici

Nelle tabelle a forma libera, le righe e le colonne possono contenere vari valori dei componenti. Questi valori possono essere dinamici (cambiare nel tempo) o statici (non cambiare nel tempo), a seconda dell’analisi che desideri generare.

## Elementi dimensionali dinamici

Gli elementi dimensionali dinamici cambiano nel tempo e dipendono dalla metrica in base alla quale viene ordinato nella tabella a forma libera. Gli elementi dimensionali dinamici sono consigliati quando si desidera analizzare gli elementi principali per un determinato periodo di tempo.

Quando rilasci una dimensione in una tabella a forma libera, vengono restituite righe dinamiche. Le righe dinamiche rappresentano gli elementi principali che corrispondono alla dimensione per una metrica e un periodo di tempo specifici. È inoltre possibile rilasciare una dimensione nelle colonne di una tabella a forma libera. Così facendo la dimensione si espande automaticamente nei primi 5 elementi dimensionali.

Ad esempio, quando trascini la dimensione Tipo di browser nella tabella, gli elementi dimensionali principali (ad esempio Microsoft, Apple, Google, ecc.) tornare dinamicamente alle righe della tabella. Se viene rilasciata in una colonna, sono restituiti in modo dinamico i primi cinque elementi della dimensione Tipo di browser.

Gli elementi dimensionali dinamici dispongono dell&#39;opzione filtro righe ![Filtro](/help/assets/icons/Filter.svg) e di una ![Chiusura](/help/assets/icons/Close.svg) e **non** dispongono di un blocco ![BloccoChiuso](/help/assets/icons/LockClosed.svg). <!--do they have the lock icon? --> Quando fai clic su ![Chiudi](/help/assets/icons/Close.svg) accanto a un elemento di dimensione dinamica, viene applicato automaticamente un filtro. Per ulteriori informazioni sull&#39;applicazione di filtri alle tabelle, vedere [Filtrare e ordinare le tabelle](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).


![Tabella a forma libera che evidenzia l&#39;icona del filtro.](assets/dynamic-items.png)

## Elementi dimensionali statici

Gli elementi dimensionali statici non cambiano con il tempo, sono componenti fissi che vengono sempre restituiti in una tabella a forma libera. Gli elementi dimensionali statici sono consigliati quando si desidera analizzare sempre gli stessi elementi, siano essi campagne o giorni della settimana specifici.

Ogni volta che selezioni e rilasci manualmente valori di componenti specifici (dimensione, metrica, filtro, intervallo di date) in una tabella, il risultato è un elenco statico di righe o colonne.

Ad esempio, quando trascini su specifici elementi della dimensione Tipo di browser, come Microsoft e Apple, questi due elementi specifici vengono sempre inseriti nella tabella.

È inoltre possibile creare elementi dimensionali statici se si sceglie di selezionare **[!UICONTROL Display only selected rows]** dal menu di scelta rapida per le righe selezionate.

Gli elementi dimensionali statici **non** dispongono dell’opzione filtro righe. Su ogni elemento sono invece presenti ![LockClosed](/help/assets/icons/LockClosed.svg) e ![Close](/help/assets/icons/Close.svg). Seleziona ![Chiudi](/help/assets/icons/Close.svg) per rimuovere l&#39;elemento dimensione dalla tabella.

![Tabella a forma libera che mostra il tipo di browser e la riga Microsoft con un&#39;icona di blocco. Nota: questo elemento dimensione è statico e non cambierà con il tempo.](assets/static-items.png)

## Elementi dimensionali misti

È possibile aggiungere alla stessa tabella elementi dimensionali di dimensioni diverse. In questi casi, l&#39;intestazione di riga indica **[!UICONTROL Mixed Dimensions]**. Questi elementi dimensionali sono statici. Ad esempio, è possibile aggiungere elementi dimensionali specifici dalla dimensione Gruppo di browser e altri elementi dimensionali dalla dimensione Nome browser.

![Tabella a forma libera che evidenzia la colonna Dimensioni miste.](assets/mixed-dimensions.png)

## Righe del totale a forma libera

Le righe dinamiche e statiche si comportano in modo diverso nella riga del totale a forma libera. Per impostazione predefinita:

* Le righe dinamiche vengono sommate lato server e deduplicano metriche quali sessioni o persone.
* Le righe statiche vengono sommate lato client e **non** duplicano le metriche. Per calcolare la riga del totale lato server, modifica l’impostazione della riga in **Mostra totale**. [Ulteriori informazioni](/help/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.md)


>[!BEGINSHADEBOX]

Vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Riordinare le righe statiche](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/reordering-static-rows-in-analysis-workspace){target="_blank"} per un video demo.

>[!ENDSHADEBOX]


