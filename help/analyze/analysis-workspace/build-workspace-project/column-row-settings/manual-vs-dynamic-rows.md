---
description: Modalità di interazione con righe statiche nelle tabelle.
seo-description: Modalità di interazione con righe statiche nelle tabelle.
seo-title: Righe statiche e dinamiche
title: Righe statiche e dinamiche
uuid: caf 033 ef-d 252-4 f 8 a -802 e -7 edbbac 5 c 8 c 0
translation-type: tm+mt
source-git-commit: fc29562a342c9d1721e250f5e3abc4d3fced926f

---


# Righe statiche e dinamiche

Le tabelle di Analysis Workspace generano righe “dinamiche” quando una dimensione viene trascinata nella tabella. Di conseguenza, tutti gli elementi che corrispondono alla dimensione, per una metrica specifica, vengono inseriti nella tabella.

Ad esempio, quando la dimensione Browser viene trascinata nella tabella, tutti i suoi elementi dimensioni (ad esempio, browser Android, Mobile Safari, Firefox, ecc.) vengono inseriti nella tabella stessa.

Invece, ogni volta che selezioni e trascini manualmente una metrica specifica, un segmento, un intervallo di dati o un singolo elemento dimensionale in una tabella, ottieni una riga o un elenco “statici” oppure impostati come hardcoded. Ora puoi interagire con una riga statica nei seguenti modi:

* Fai clic sull’icona Anteprima nelle righe statiche per visualizzare un’anteprima dei segmenti, delle metriche, e degli intervalli di date.
* Fai clic sull’icona “x” per eliminare la riga dalla tabella.
* Limita il numero di righe che vengono visualizzate e attivano il paging.
* Aggiungi “vari elementi dimensionali”. Ad esempio, puoi aggiungere un elemento dalla dimensione di browser e un altro elemento dalla dimensione di un prodotto.

   Di seguito, riportiamo un’immagine esemplificativa:

   ![](assets/static_rows.png)

Inoltre, (solo) quando ti trovi in modalità statica, ora puoi modificare il calcolo dei totali della colonna. Basta fare clic sull’icona a ingranaggio e scegliere tra queste 2 opzioni:

![](assets/column-totals.png)

| Opzione | Descrizione |
|---|---|
| Calcola i totali, sommando i valori presenti in ciascuna colonna. | Questa opzione consente di calcolare solo le righe presenti nella tabella (calcolo lato client). |
| Calcola i totali, basandosi su tutte le righe per ciascuna metrica. | Questa opzione include tutti gli elementi di questa dimensione anche quelli non elencati nella tabella (calcolo lato server). |

