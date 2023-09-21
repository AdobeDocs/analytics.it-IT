---
title: DMA Stati Uniti
description: Area di mercato designata dell’hit.
feature: Dimensions
exl-id: 156d5755-2e93-4240-bde3-1d537422b7bf
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 1%

---

# DMA Stati Uniti

La &#39;DMA USA&#39; [dimensione](overview.md) segnala l’area di mercato designata (DMA) del visitatore. Si basa sui mercati dei media compilati da [Nielsen](https://markets.nielsen.com/us/en/contact-us/intl-campaigns/dma-maps/).

## Popola questa dimensione con i dati

Questa dimensione fa riferimento a regole di ricerca interne di Adobe. Il valore di ricerca si basa sull’indirizzo IP inviato con l’hit. Adobe collabora con Nielsen per mantenere le ricerche tra l’indirizzo IP e DMA. Questa dimensione funziona in modo predefinito per tutte le implementazioni.

## Elementi dimensionali

Gli elementi del Dimension includono il codice DMA e DMA del visitatore. Il codice a 3 cifre non è un codice postale, ma il codice DMA di Nielsen. I valori di esempio includono `"Dallas-Ft. Worth (623)"`, `"New York (501)"`, o `"Los Angeles (803)"`. Elemento dimensione `"No Metro (0)"` include tutto il traffico internazionale al di fuori degli Stati Uniti.

## Differenze tra l&#39;ubicazione effettiva e quella riportata

Poiché questa dimensione si basa sull’indirizzo IP, alcuni scenari possono mostrare una differenza tra la posizione segnalata e la posizione effettiva:

* **Indirizzi IP che rappresentano proxy aziendali**: questi visitatori possono apparire come traffico proveniente dalla rete aziendale dell’utente, che può trovarsi in una posizione diversa se l’utente lavora in remoto.
* **Indirizzi IP per dispositivi mobili**: il targeting IP per dispositivi mobili funziona a diversi livelli a seconda della posizione e della rete. Vari vettori effettuano il backhaul del traffico IP attraverso punti di presenza centralizzati o regionali.
* **Utenti ISP satellite**: identificare la posizione specifica di questi utenti è difficile, in quanto generalmente sembrano provenire dalla posizione di uplink.
* **IP militari e governativi**: rappresenta il personale che viaggia per il mondo e che accede dalla propria sede principale, anziché dalla base o dall’ufficio in cui si trova attualmente.
* **Proxy che nascondono gli indirizzi IP per motivi di privacy**: servizi come Inoltro privato di Apple nascondono il vero indirizzo IP inviando in modo casuale i dati tramite un intermediario o un proxy. Questo proxy sostituisce quindi un indirizzo IP diverso prima di inoltrarlo all’Adobe.
