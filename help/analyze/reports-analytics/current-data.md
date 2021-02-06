---
description: L'opzione Includi dati correnti in Reporting e analisi consente di visualizzare gli ultimi dati di Analytics, spesso prima che i dati vengano elaborati e finalizzati completamente. I dati correnti mostrano la maggior parte delle metriche in pochi minuti, fornendo dati fruibili per il processo decisionale rapido.
subtopic: Current Data
title: Dati correnti
topic: Reports
uuid: 601d3695-be13-4b7f-9df0-de01c8bd64ee
translation-type: tm+mt
source-git-commit: 03b1195225b97f3ea151eb5b4f39fbed746b3654
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 1%

---


# Dati correnti

L&#39;opzione Includi dati correnti in Reporting e analisi consente di visualizzare gli ultimi dati di Analytics, spesso prima che i dati vengano elaborati e finalizzati completamente. I dati correnti mostrano la maggior parte delle metriche in pochi minuti, fornendo dati fruibili per il processo decisionale rapido.

È visibile come opzione nelle impostazioni di un rapporto:

![Schermata Dati Corrente](assets/current_data.png)

I dati correnti sono attivati per impostazione predefinita su tutti i rapporti che li supportano. Se preferisci visualizzare tutte le metriche dopo che i dati sono stati elaborati completamente, sono disponibili diverse opzioni:

* Utilizzate  Analysis Workspace, che utilizza dati elaborati completamente.
* Fare clic su &#39;No&#39; nell&#39;impostazione del rapporto dati corrente per utilizzare solo i dati elaborati completamente.
* Rimuovete l&#39;elemento di autorizzazione &quot;Dati correnti&quot; da un profilo di prodotto nel Admin Console  per impedire agli utenti non amministratori di visualizzare questa opzione. Per ulteriori informazioni, consulta [Autorizzazioni del profilo di prodotto per Analytics Tools](/help/admin/admin-console/permissions/analytics-tools.md) nella guida utente di amministrazione.

A causa della disponibilità di dati con priorità, i dati correnti non possono attualmente essere utilizzati con segmenti, classificazioni, suddivisioni, percorsi e alcune metriche. Se si utilizza una di queste funzioni, i dati correnti vengono forzati a &#39;No&#39; nel rapporto e viene visualizzato un avviso giallo che spiega perché i dati correnti non sono disponibili.

![Avviso dati correnti](assets/current_data_notice.png)

## Latenza dati corrente tipica

Le metriche vengono visualizzate in uno dei tre seguenti fotogrammi temporali. Fai clic sull’icona dell’orologio accanto all’opzione Includi dati correnti per visualizzare il valore di latenza effettivo per ogni metrica in un rapporto.

| Intervallo temporale | Metriche |
| --- | --- |
| Meno di 10 minuti | Istanze e visualizzazioni di pagina sulle variabili di traffico |
| Tra 10 e 35 minuti | Eventi di conversione, istanze e visualizzazioni di pagina sulle variabili di conversione |
| Tra 45 e 120 minuti | Tutti gli altri dati, quali visite, visitatori univoci e partecipazione |

Poiché alcuni dei dati visualizzati nella visualizzazione dati corrente non sono stati elaborati completamente, è possibile notare una differenza tra i valori segnalati nella visualizzazione dati corrente e nella visualizzazione finale. Nei report con tendenze, la differenza di dati si trova in genere all&#39;interno dell&#39;1%.

## Metriche calcolate

Poiché le metriche calcolate possono essere create utilizzando metriche con latenza diversa, alcuni valori recenti potrebbero essere calcolati utilizzando dati incompleti nella visualizzazione dati corrente.

Ad esempio, è possibile creare la metrica calcolata &quot;Visualizzazioni di pagina per visita&quot; utilizzando la formula `Page Views divided by Visits`. Le visualizzazioni di pagina vengono visualizzate in genere entro 10 minuti e le visite vengono generalmente visualizzate entro 2 ore. Le metriche calcolate all&#39;interno di questa finestra di latenza vengono calcolate utilizzando metriche incomplete. Se pubblicate una nuova pagina che riceve 4000 hit da 4000 visite diverse su un intervallo di tempo di 2 ore, la differenza di latenza tra queste metriche può causare calcoli incompleti.

Questa differenza di dati è più visibile quando si crea un rapporto sui nuovi valori o si utilizzano frame di tempo brevi. Quando un report utilizza intervalli di date più lunghi, è improbabile che le differenze di latenza che si verificano nelle ultime ore di reporting abbiano un impatto significativo sulle metriche calcolate.

Se hai metriche calcolate che potrebbero essere influenzate da queste differenze, puoi disattivare i dati correnti o utilizzare metriche con la stessa finestra di latenza prevista.

## Report scaricati

Quando scaricate un rapporto con la visualizzazione dati corrente abilitata, il rapporto viene messo in coda, generato e quindi restituito al browser. Se i dati vengono raccolti durante la generazione del rapporto, tali dati vengono visualizzati nel rapporto. Questa finestra di tempo può portare al download del report con un po&#39; più di dati.
