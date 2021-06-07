---
title: Stati degli Stati Uniti
description: Stato USA del visitatore.
exl-id: d4506e59-c1ff-4348-912d-c1ad73278f56
source-git-commit: 9770f8e04089ff339d912d1787679257c87c7caa
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 0%

---

# Stato americano

La dimensione &quot;Stato USA&quot; indica lo stato del visitatore negli Stati Uniti d’America. È simile alla dimensione [Regioni](regions.md), con la differenza che questa dimensione è specifica degli Stati Uniti. L’utilizzo di questa dimensione è utile se desideri ottenere informazioni più dettagliate rispetto a [Nazioni](countries.md) ma non granulari come [Città](cities.md).

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento a regole di ricerca interne all’Adobe. Il valore di ricerca si basa sull’indirizzo IP inviato con l’hit. Partner di Adobe con [Elemento digitale](https://www.digitalelement.com/) per mantenere le ricerche tra l’indirizzo IP e il paese. Questa dimensione funziona come standard per tutte le implementazioni.

## Elementi Dimension

Gli elementi di Dimension includono le regioni e il paese in cui risiede la regione. I valori di esempio includono `"California"`, `"Texas"` o `"Virginia"`. L’elemento dimensione `"Unspecified"` include tutto il traffico internazionale al di fuori degli Stati Uniti.

Questa dimensione può includere `"AOL"`, un provider di servizi Internet dial-up. Agli abbonati a questo servizio viene assegnato un punto di accesso. Gli utenti AOL utilizzano l&#39;indirizzo IP di questo punto di accesso. Poiché questa dimensione si basa sull’indirizzo IP, al posto della posizione effettiva del visitatore viene utilizzata la geolocalizzazione del punto di accesso.

## Differenze tra ubicazione effettiva e segnalata

Poiché questa dimensione è basata sull’indirizzo IP, alcuni scenari possono mostrare una differenza tra la posizione segnalata e la posizione effettiva:

* **Indirizzi IP che rappresentano proxy** aziendali: Questi visitatori possono apparire come traffico proveniente dalla rete aziendale dell&#39;utente, che può essere diversa se l&#39;utente lavora in remoto.
* **Indirizzi** IP mobili: Il targeting IP per dispositivi mobili funziona a diversi livelli a seconda della posizione e della rete. Un certo numero di vettori ritorna il traffico IP attraverso punti di presenza centralizzati o regionali.
* **Utenti** ISP satellitari: Identificare la posizione specifica di questi utenti è difficile, in quanto in genere sembrano originare dalla posizione di uplink.
* **IP** militari e governativi: Rappresenta il personale che viaggia per il mondo e che entra nella propria posizione di casa, piuttosto che la base o l&#39;ufficio in cui si trovano attualmente.
