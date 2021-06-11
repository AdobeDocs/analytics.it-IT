---
title: Aree geografiche
description: Area geografica del visitatore.
exl-id: 95ab4c7e-71e8-490f-88a4-25201331d848
source-git-commit: 4e09df2631626376f9351512afed7a9e4241e7d6
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 0%

---

# Aree geografiche

La dimensione &quot;Regioni&quot; indica l’area geografica del visitatore. È un&#39;area geografica più piccola di un paese ma più grande di una città. In alcuni paesi una regione è uno stato, una provincia o una prefettura. In altre aree si tratta di un paese costituente, un dipartimento o una regione metropolitana. L’utilizzo di questa dimensione è utile se desideri ottenere informazioni più dettagliate rispetto a [Nazioni](countries.md) ma non granulari come [Città](cities.md).

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento a regole di ricerca interne all’Adobe. Il valore di ricerca si basa sull’indirizzo IP inviato con l’hit. Partner di Adobe con [Elemento digitale](https://www.digitalelement.com/) per mantenere le ricerche tra l’indirizzo IP e il paese. Questa dimensione funziona come standard per tutte le implementazioni.

## Elementi Dimension

Gli elementi di Dimension includono le regioni e il paese in cui risiede la regione. I valori di esempio includono `"California (United States)"`, `"Tokyo (Japan)"` o `"Sao Paulo (Brazil)"`.

Alcuni elementi dimensionali possono includere `"AOL"`, un provider di servizi Internet dial-up. Agli abbonati a questo servizio viene assegnato un punto di accesso in base al paese in cui è stabilito il loro numero di account. Gli utenti AOL utilizzano l&#39;indirizzo IP di questo punto di accesso. Poiché questa dimensione si basa sull’indirizzo IP, al posto della posizione effettiva del visitatore viene utilizzata la geolocalizzazione del punto di accesso.

## Differenze tra ubicazione effettiva e segnalata

Poiché questa dimensione è basata sull’indirizzo IP, alcuni scenari possono mostrare una differenza tra la posizione segnalata e la posizione effettiva:

* **Indirizzi IP che rappresentano proxy** aziendali: Questi visitatori possono apparire come traffico proveniente dalla rete aziendale dell&#39;utente, che può essere diversa se l&#39;utente lavora in remoto.
* **Indirizzi** IP mobili: Il targeting IP per dispositivi mobili funziona a diversi livelli a seconda della posizione e della rete. Un certo numero di vettori ritorna il traffico IP attraverso punti di presenza centralizzati o regionali.
* **Utenti** ISP satellitari: Identificare la posizione specifica di questi utenti è difficile, in quanto in genere sembrano originare dalla posizione di uplink.
* **IP** militari e governativi: Rappresenta il personale che viaggia per il mondo e che entra nella propria posizione di casa, piuttosto che la base o l&#39;ufficio in cui si trovano attualmente.
