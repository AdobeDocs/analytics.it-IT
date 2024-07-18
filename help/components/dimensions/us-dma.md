---
title: DMA Stati Uniti
description: Area di mercato designata dell’hit.
feature: Dimensions
exl-id: 156d5755-2e93-4240-bde3-1d537422b7bf
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 3%

---

# DMA Stati Uniti

La [dimensione](overview.md) di &#39;DMA USA&#39; segnala l&#39;area di mercato designata (DMA) del visitatore. Si basa sui mercati dei contenuti multimediali compilati da [Nielsen](https://www.nielsen.com/dma-regions/).

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento a regole di ricerca interne di Adobe. Il valore di ricerca si basa sull’indirizzo IP inviato con l’hit. Adobe collabora con Nielsen per mantenere le ricerche tra l’indirizzo IP e DMA.

* Ad AppMeasurement, le implementazioni di questa dimensione sono pronte all’uso.
* Per le implementazioni Web SDK, abilita [!UICONTROL Geo Lookup] quando [si configura uno stream di dati](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=it).

## Elementi dimensionali

Gli elementi Dimension includono i codici DMA e DMA del visitatore. Il codice a 3 cifre non è un codice postale, ma il codice DMA di Nielsen. I valori di esempio includono `"Dallas-Ft. Worth (623)"`, `"New York (501)"` o `"Los Angeles (803)"`. L&#39;elemento dimensione `"No Metro (0)"` include tutto il traffico internazionale al di fuori degli Stati Uniti.

## Differenze tra l&#39;ubicazione effettiva e quella riportata

Poiché questa dimensione si basa sull’indirizzo IP, alcuni scenari possono mostrare una differenza tra la posizione segnalata e la posizione effettiva:

* **Indirizzi IP che rappresentano proxy aziendali**: questi visitatori possono essere visualizzati come traffico proveniente dalla rete aziendale dell&#39;utente, che può essere una posizione diversa se l&#39;utente lavora in remoto.
* **Indirizzi IP per dispositivi mobili**: il targeting IP per dispositivi mobili funziona a vari livelli a seconda della posizione e della rete. Alcuni vettori effettuano il backhaul del traffico IP attraverso punti di presenza centralizzati o regionali.
* **Utenti ISP satellite**: identificare la posizione specifica di questi utenti è difficile, in quanto in genere sembrano provenire dalla posizione uplink.
* **IP militari e governativi**: rappresenta il personale che viaggia in tutto il mondo e che entra attraverso la propria sede principale, anziché la base o l&#39;ufficio in cui si trova attualmente.
* **Proxy che nascondono gli indirizzi IP per motivi di privacy**: servizi come Inoltro privato di Apple nascondono l&#39;indirizzo IP effettivo inviando i dati in modo casuale tramite un intermediario o un proxy. Questo proxy sostituisce quindi un indirizzo IP diverso prima di inoltrarlo all’Adobe.
