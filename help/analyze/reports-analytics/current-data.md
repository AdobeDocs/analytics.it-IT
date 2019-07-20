---
description: L'opzione Includi dati correnti in Reporting e analisi consente di visualizzare i dati Analytics più recenti, spesso prima che i dati vengano elaborati e finalizzati completamente. I dati correnti visualizzano la maggior parte delle metriche in minuti, fornendo dati fruibili per una rapida decisione decisionale.
seo-title: Dati correnti
solution: Analytics
subtopic: Dati correnti
title: Dati correnti
topic: Rapporti
uuid: 601 d 3695-be 13-4 b 7 f -9 df 0-de 01 c 8 bd 64 ee
translation-type: tm+mt
source-git-commit: 1fdd14497171dbf5850ec1b1d873a06931d58435

---


# Dati correnti

L'opzione Includi dati correnti in Reporting e analisi consente di visualizzare i dati Analytics più recenti, spesso prima che i dati vengano elaborati e finalizzati completamente. I dati correnti visualizzano la maggior parte delle metriche in minuti, fornendo dati fruibili per una rapida decisione decisionale.

È visibile come opzione nell'ambito delle impostazioni di un rapporto:

![Screenshot dati corrente](assets/current_data.png)

I dati correnti sono attivati per impostazione predefinita su tutti i rapporti che lo supportano. Se preferisci visualizzare tutte le metriche una volta che i dati sono stati elaborati completamente, sono disponibili diverse opzioni:

* Utilizza Analysis Workspace, che utilizza dati completamente elaborati.
* Fate clic su «No» nell'impostazione del rapporto dati corrente per utilizzare solo dati completamente elaborati.
* Rimuovi l'autorizzazione «Dati correnti» da un profilo di prodotto in Admin Console per impedire agli utenti non amministratori di visualizzare questa opzione. See [Analytics Tools permission items](../../admin/admin-console/permissions/analytics-tools.md) in the Admin user guide for more information.

A causa della priorità della disponibilità dei dati, i dati correnti non possono essere utilizzati con segmenti, classificazioni, suddivisioni, percorsi e alcune metriche. Se una di queste funzioni è utilizzata, i dati correnti vengono forzati a "No" nel rapporto e viene visualizzato un avviso giallo che illustra il motivo per cui i dati correnti non sono disponibili.

![Avviso dati corrente](assets/current_data_notice.png)

## Latenza dati corrente

Le metriche vengono visualizzate in uno dei tre fotogrammi seguenti. Fai clic sull'icona dell'orologio accanto all'interruttore Includi dati correnti per visualizzare il valore di latenza effettiva per ogni metrica su un rapporto.

| Intervallo temporale | Metrics (Metriche) |
| --- | --- |
| Meno di 10 minuti | Istanze e visualizzazioni di pagina sulle variabili di traffico |
| Tra 10 e 35 minuti | Eventi di conversione, istanze e visualizzazioni di pagina sulle variabili di conversione |
| Tra 45 e 120 minuti | Tutti gli altri dati, come visite, visitatori unici e partecipazione |

Poiché alcuni dei dati visualizzati nella visualizzazione dati corrente non sono stati elaborati completamente, puoi vedere una differenza tra i valori segnalati nella visualizzazione dati corrente e nella visualizzazione finalizzata. Nei report con tendenze, la differenza di dati è generalmente compresa in 1%.

## Metriche calcolate

Dato che le metriche calcolate possono essere create utilizzando metriche con latenza diversa, alcuni valori recenti potrebbero essere calcolati utilizzando dati incompleti nella visualizzazione dati corrente.

For example, you create the calculated metric 'Page Views per Visit using the formula `Page Views divided by Visits`. Le visualizzazioni di pagina vengono generalmente visualizzate entro 10 minuti e le visite in genere vengono visualizzate entro 2 ore, le metriche calcolate all'interno di questa finestra latenza vengono calcolate utilizzando metriche incomplete. Se pubblichi una nuova pagina con 4000 hit da 4000 visite diverse in un intervallo di 2 ore, la differenza di latenza tra queste metriche può causare calcoli incompleti.

Questa differenza di dati è più visibile durante il reporting su nuovi valori o con brevi fotogrammi. Quando un rapporto utilizza intervalli di date più lunghi, le differenze di latenza che si verificano nelle ultime ore di reporting potrebbero avere un impatto evidente sulle metriche calcolate.

Se hai metriche calcolate che potrebbero essere influenzate da queste differenze, disattivate i dati correnti o utilizzate le metriche con la stessa finestra latenza prevista.

## Rapporti scaricati

Quando scaricate un rapporto con la visualizzazione dati corrente abilitata, il rapporto viene messo in coda, generato e quindi inviato al browser. Se i dati vengono raccolti durante la generazione del report, questi vengono visualizzati nel rapporto. Questa finestra può portare al report scaricato con un leggero numero di dati.
