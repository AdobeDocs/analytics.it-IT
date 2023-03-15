---
description: L’opzione Includi dati correnti in Reports & Analytics consente di visualizzare i dati Analytics più recenti, spesso prima che i dati vengano completamente elaborati e finalizzati. I dati correnti visualizzano la maggior parte delle metriche in pochi minuti, fornendo dati fruibili per un processo decisionale rapido.
subtopic: Current Data
title: Dati correnti
uuid: 601d3695-be13-4b7f-9df0-de01c8bd64ee
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 4e90f5ad-ba12-4282-a0d9-55765d88104b
source-git-commit: 4ddc2640aa8b3a22411c86ff8bfe0ecf345a3d63
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 1%

---

# Dati correnti

{{ra-eol}}

L’opzione Includi dati correnti in Reports &amp; Analytics consente di visualizzare i dati Analytics più recenti, spesso prima che i dati vengano completamente elaborati e finalizzati. I dati correnti visualizzano la maggior parte delle metriche in pochi minuti, fornendo dati fruibili per un processo decisionale rapido.

È visibile come opzione nelle impostazioni di un rapporto:

![Screenshot dati corrente](assets/current_data.png)

L&#39;opzione Dati correnti è attivata per impostazione predefinita in tutti i report che la supportano. Se preferisci visualizzare tutte le metriche dopo che i dati sono stati completamente elaborati, ci sono diverse opzioni:

* Utilizza Analysis Workspace, che utilizza dati completamente elaborati.
* Fai clic su No nell’impostazione corrente del rapporto dati per utilizzare solo dati completamente elaborati.
* Rimuovi l’elemento di autorizzazione &quot;Dati correnti&quot; da un profilo di prodotto nell’Admin Console per impedire agli utenti non amministratori di visualizzare questa opzione. Consulta [Autorizzazioni del profilo di prodotto per gli strumenti Analytics](/help/admin/admin-console/permissions/analytics-tools.md) per ulteriori informazioni, consulta la guida utente dell’amministratore.

A causa della priorità assegnata alla disponibilità dei dati, i dati correnti al momento non possono essere utilizzati con segmenti, classificazioni, raggruppamenti, percorsi e alcune metriche. Se utilizzi una di queste funzioni, i dati correnti vengono forzati a &quot;No&quot; nel rapporto e viene visualizzata una nota gialla che spiega perché i dati correnti non sono disponibili.

![Avviso sui dati correnti](assets/current_data_notice.png)

## Latenza tipica dei dati correnti

Le metriche vengono visualizzate in uno dei tre intervalli di tempo seguenti. Fai clic sull’icona dell’orologio accanto all’interruttore Includi dati correnti per visualizzare il valore della latenza effettiva per ogni metrica in un rapporto.

| Intervallo temporale | Metriche |
| --- | --- |
| Meno di 10 minuti | Istanze e visualizzazioni di pagina sulle variabili di traffico |
| Tra 10 e 35 minuti | Eventi di conversione, istanze e visualizzazioni di pagina sulle variabili di conversione |
| Tra 45 e 120 minuti | Tutti gli altri dati, come visite, visitatori univoci e partecipazione |

Poiché alcuni dei dati visualizzati nella visualizzazione dati corrente non sono stati completamente elaborati, è possibile notare una differenza tra i valori riportati nella visualizzazione dati corrente e quelli nella visualizzazione finalizzata. Nei rapporti con tendenze, la differenza di dati è in genere entro l’1%.

## Metriche calcolate 

Poiché le metriche calcolate possono essere create utilizzando metriche con latenza diversa, alcuni valori recenti potrebbero essere calcolati utilizzando dati incompleti nella visualizzazione dati corrente.

Ad esempio, puoi creare la metrica calcolata &quot;Visualizzazioni pagina per visita&quot; utilizzando la formula `Page Views divided by Visits`. Le visualizzazioni di pagina vengono in genere visualizzate entro 10 minuti e le visite entro 2 ore; le metriche calcolate all’interno di questa finestra di latenza vengono calcolate utilizzando metriche incomplete. Se pubblichi una nuova pagina che ottiene 4000 hit da 4000 visite diverse in un intervallo di tempo di 2 ore, la differenza di latenza tra queste metriche può causare calcoli incompleti.

Questa differenza di dati è più visibile quando si generano rapporti su nuovi valori o si utilizzano intervalli di tempo brevi. Quando un rapporto utilizza intervalli di date più lunghi, è improbabile che le differenze di latenza che si verificano nelle ultime ore di reporting abbiano un impatto significativo sulle metriche calcolate.

Se disponi di metriche calcolate che potrebbero essere influenzate da queste differenze, disattiva i dati correnti o utilizza metriche con la stessa finestra di latenza prevista.

## Report scaricati

Quando scarichi un rapporto con la visualizzazione dati corrente abilitata, il rapporto viene messo in coda, generato e quindi restituito al browser. Se i dati vengono raccolti durante la generazione del rapporto, vengono visualizzati nel rapporto. Questa finestra temporale può comportare una leggera quantità di dati per il rapporto scaricato.
