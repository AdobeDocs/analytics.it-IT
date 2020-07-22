---
title: Elementi dimensione dinamici e statici
description: Come interagire con gli elementi dimensionali dinamici e statici nelle tabelle.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 2%

---


# Elementi dimensione dinamici e statici nelle tabelle a forma libera

Nelle tabelle a forma libera, le righe e le colonne possono contenere diversi valori dei componenti. Questi valori possono essere dinamici (cambiare con il tempo) o statici (non cambiare con il tempo), a seconda dell&#39;analisi che si desidera generare.

## Elementi dimensione dinamici

Gli elementi dimensione dinamici cambiano con il tempo e dipendono dalla metrica ordinata dalla tabella a forma libera. Gli elementi dimensionali dinamici sono preferiti quando si desidera analizzare gli elementi principali per un determinato periodo di tempo.

Quando rilasci una dimensione in una tabella a forma libera, vengono restituite righe dinamiche. Rappresentano gli elementi principali che corrispondono alla dimensione per una metrica e un periodo di tempo specifici. È inoltre possibile rilasciare una dimensione nelle colonne di tabella a forma libera e la dimensione si espande automaticamente nei primi 5 elementi dimensionali.

Ad esempio, quando si trascina la dimensione Tipo browser nella tabella, gli elementi principali della dimensione Tipo browser (ad esempio, Microsoft, Apple, Google, ecc.) tornare alle righe della tabella in modo dinamico. Se viene rilasciata in una colonna, i primi cinque elementi dimensionali del tipo di browser torneranno in modo dinamico.

Gli elementi dimensione dinamica dispongono dell&#39;opzione filtro riga e **non** sono presenti icone blocco e X.

## Elementi dimensione statici

Gli elementi dimensionali statici non cambiano con il tempo; sono componenti fissi che vengono sempre restituiti in una tabella a forma libera. Gli elementi dimensione statica sono preferiti quando si desidera analizzare sempre lo stesso elemento, siano essi campagne specifiche o giorni specifici della settimana.

Ogni volta che si selezionano e si rilasciano manualmente valori di componenti specifici (dimensione, metrica, segmento, intervallo di date) in una tabella, il risultato è un elenco statico di righe o colonne. È inoltre possibile creare elementi dimensionali statici se si sceglie di:

* Da righe, fate clic con il pulsante destro del mouse > [!UICONTROL Display only selected rows]
* Da colonne, fare clic con il pulsante destro del mouse > [!UICONTROL Make item static]

Ad esempio, quando si trascina su specifici elementi del tipo di browser come Microsoft e Apple, questi due elementi specifici vengono sempre inseriti nella tabella.

Gli elementi dimensione statici **non** dispongono dell&#39;opzione filtro righe. Al contrario, su ogni elemento sono presenti le icone Blocca e X. Fare clic sull&#39;icona X per rimuovere l&#39;elemento dimensione dalla tabella.

## Elementi dimensionali misti

È possibile aggiungere alla stessa tabella elementi dimensionali di dimensioni diverse. In questi casi, l’intestazione della riga indica &quot;Dimensioni miste&quot;. Questi elementi dimensione sono statici. Ad esempio, aggiungere elementi dimensionali specifici dalla dimensione Tipo browser e altri elementi dimensionali dalla dimensione Browser.

## Righe totali a forma libera

Le righe dinamiche e statiche si comportano in modo diverso nella riga totale a forma libera. Per impostazione predefinita:

* Le righe dinamiche vengono sommate con metriche lato server e deduplicate, come visite o visitatori
* Le righe statiche sono sommate sul lato client e **non** duplicano le metriche.

[Ulteriori informazioni sulle opzioni totali](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/build-workspace-project/workspace-totals.html) di Workspace per le righe dinamiche e statiche.
