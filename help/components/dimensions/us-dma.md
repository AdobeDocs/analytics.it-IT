---
title: DMA USA
description: Area di mercato designata dell'hit.
translation-type: tm+mt
source-git-commit: 52e00470df0f0c6bff84b26c1548e64ff5114fb8
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 0%

---


# DMA USA

La dimensione &#39;US DMA&#39; segnala l&#39;area di mercato designata (DMA) del visitatore. Si basa sui mercati dei media compilati da [Nielsen](https://www.nielsen.com/us/en/intl-campaigns/dma-maps/).

## Compilare questa dimensione con i dati

Questa dimensione fa riferimento a regole di ricerca interne ad Adobe. Il valore di ricerca si basa sull&#39;indirizzo IP inviato con l&#39;hit. Adobe collabora con Nielsen per mantenere le ricerche tra l&#39;indirizzo IP e DMA. Questa dimensione funziona automaticamente per tutte le implementazioni.

> [!TIP] Se l&#39;azienda rispetta le severe normative sulla privacy laddove l&#39; [oscuramento dell&#39;indirizzo](/help/admin/admin/general-acct-settings-admin.md) IP non è sufficiente, puoi richiedere di disabilitare completamente i dati sulla geolocalizzazione. Contatta l&#39;Assistenza clienti con l&#39;ID suite di rapporti e richiedi di disattivare &#39;Geografia&#39; per la suite di rapporti.

## Valori dimensione

I valori delle dimensioni includono il codice DMA e DMA del visitatore. Il codice a 3 cifre non è un codice ZIP, ma il codice DMA di Nielsen. I valori di esempio includono `"Dallas-Ft. Worth (623)"`, `"New York (501)"`, o `"Los Angeles (803)"`. Il valore della dimensione `"No Metro (0)"` include tutto il traffico internazionale al di fuori degli Stati Uniti.

## Differenze tra la posizione segnalata e quella effettiva

Poiché questa dimensione è basata sull’indirizzo IP, alcuni scenari possono mostrare una differenza tra la posizione segnalata e la posizione effettiva:

* **Indirizzi IP che rappresentano proxy** aziendali: Questi visitatori possono apparire come traffico proveniente dalla rete aziendale dell&#39;utente, che può essere una posizione diversa se l&#39;utente lavora in remoto.
* **Indirizzi** IP mobili: Il targeting IP per dispositivi mobili funziona a vari livelli, a seconda della posizione e della rete. Un certo numero di vettori ritorna il traffico IP attraverso punti di presenza centralizzati o regionali.
* **Utenti** ISP via satellite: Identificare la posizione specifica di questi utenti è difficile, in quanto in genere sembrano provenire dalla posizione di uplink.
* **IP** militari e governativi: Rappresenta il personale che viaggia in tutto il mondo e che accede attraverso la propria sede, anziché la base o l&#39;ufficio in cui si trova attualmente.
