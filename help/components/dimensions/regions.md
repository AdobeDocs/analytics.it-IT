---
title: Aree geografiche
description: L’area geografica del visitatore.
feature: Dimensions
exl-id: 95ab4c7e-71e8-490f-88a4-25201331d848
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 5%

---

# Aree geografiche

La [dimensione](overview.md) &quot;Aree geografiche&quot; segnala l&#39;area geografica del visitatore. Si tratta di un&#39;area geografica più piccola di un paese ma più grande di una città. In alcuni Paesi, un’area geografica è uno stato, una provincia o una prefettura. In altre aree, è un paese costituente, un dipartimento o una regione metropolitana. L&#39;utilizzo di questa dimensione è utile se desideri che insight sia più granulare di [Paesi](countries.md) ma non granulare come [Città](cities.md).

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento a regole di ricerca interne di Adobe. Il valore di ricerca si basa sull’indirizzo IP inviato con l’hit. Adobe collabora con [elemento digitale](https://www.digitalelement.com/) per mantenere le ricerche tra indirizzo IP e paese. Questa dimensione funziona in modo predefinito per tutte le implementazioni.

## Elementi dimensionali

Gli elementi di Dimension includono le aree geografiche e il paese in cui si trova l’area geografica. I valori di esempio includono `"California (United States)"`, `"Tokyo (Japan)"` o `"Sao Paulo (Brazil)"`.

Alcuni elementi dimensionali possono includere `"AOL"`, un provider di servizi Internet di connessione remota. Agli abbonati a questo servizio viene assegnato un punto di accesso in base al paese in cui è stabilito il loro numero di conto. Gli utenti AOL utilizzano l’indirizzo IP di questo punto di accesso. Poiché questa dimensione si basa sull’indirizzo IP, al posto della posizione effettiva del visitatore viene utilizzata la geolocalizzazione del punto di accesso.

## Differenze tra l&#39;ubicazione effettiva e quella riportata

Poiché questa dimensione si basa sull’indirizzo IP, alcuni scenari possono mostrare una differenza tra la posizione segnalata e la posizione effettiva:

* **Indirizzi IP che rappresentano proxy aziendali**: questi visitatori possono essere visualizzati come traffico proveniente dalla rete aziendale dell&#39;utente, che può essere una posizione diversa se l&#39;utente lavora in remoto.
* **Indirizzi IP per dispositivi mobili**: il targeting IP per dispositivi mobili funziona a vari livelli a seconda della posizione e della rete. Vari vettori effettuano il backhaul del traffico IP attraverso punti di presenza centralizzati o regionali.
* **Utenti ISP satellite**: identificare la posizione specifica di questi utenti è difficile, in quanto in genere sembrano provenire dalla posizione uplink.
* **IP militari e governativi**: rappresenta il personale che viaggia in tutto il mondo e che entra attraverso la propria sede principale, anziché la base o l&#39;ufficio in cui si trova attualmente.
* **Proxy che nascondono gli indirizzi IP per motivi di privacy**: servizi come Inoltro privato di Apple nascondono l&#39;indirizzo IP effettivo inviando i dati in modo casuale tramite un intermediario o un proxy. Questo proxy sostituisce quindi un indirizzo IP diverso prima di inoltrarlo ad Adobe.
