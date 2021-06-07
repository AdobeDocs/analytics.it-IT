---
title: DMA Stati Uniti
description: Area di mercato designata dell'hit.
exl-id: 156d5755-2e93-4240-bde3-1d537422b7bf
source-git-commit: 9770f8e04089ff339d912d1787679257c87c7caa
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 1%

---

# DMA Stati Uniti

La dimensione &quot;US DMA&quot; indica l’area di mercato designata (DMA) del visitatore. Si basa sui mercati dei media compilati da [Nielsen](https://www.nielsen.com/us/en/intl-campaigns/dma-maps/).

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento a regole di ricerca interne all’Adobe. Il valore di ricerca si basa sull’indirizzo IP inviato con l’hit. Partner di Adobe con Nielsen per mantenere le ricerche tra l’indirizzo IP e DMA. Questa dimensione funziona come standard per tutte le implementazioni.

## Elementi Dimension

Gli elementi di Dimension includono il codice DMA e DMA del visitatore. Il codice a 3 cifre non è un codice postale, ma piuttosto il codice DMA di Nielsen. I valori di esempio includono `"Dallas-Ft. Worth (623)"`, `"New York (501)"` o `"Los Angeles (803)"`. L’elemento dimensione `"No Metro (0)"` include tutto il traffico internazionale al di fuori degli Stati Uniti.

## Differenze tra ubicazione effettiva e segnalata

Poiché questa dimensione è basata sull’indirizzo IP, alcuni scenari possono mostrare una differenza tra la posizione segnalata e la posizione effettiva:

* **Indirizzi IP che rappresentano proxy** aziendali: Questi visitatori possono apparire come traffico proveniente dalla rete aziendale dell&#39;utente, che può essere diversa se l&#39;utente lavora in remoto.
* **Indirizzi** IP mobili: Il targeting IP per dispositivi mobili funziona a diversi livelli a seconda della posizione e della rete. Un certo numero di vettori ritorna il traffico IP attraverso punti di presenza centralizzati o regionali.
* **Utenti** ISP satellitari: Identificare la posizione specifica di questi utenti è difficile, in quanto in genere sembrano originare dalla posizione di uplink.
* **IP** militari e governativi: Rappresenta il personale che viaggia per il mondo e che entra nella propria posizione di casa, piuttosto che la base o l&#39;ufficio in cui si trovano attualmente.
