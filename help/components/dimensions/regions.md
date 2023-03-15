---
title: Aree geografiche
description: L’area geografica del visitatore.
feature: Dimensions
exl-id: 95ab4c7e-71e8-490f-88a4-25201331d848
source-git-commit: 146d622f370fd7469a8e5f0f2fe68cb31fa91844
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 1%

---

# Aree geografiche

La dimensione &quot;Aree&quot; riporta l’area geografica del visitatore. Si tratta di un&#39;area geografica più piccola di un paese ma più grande di una città. In alcuni paesi, una regione è uno stato, una provincia o una prefettura. In altre aree, è un paese costituente, un dipartimento o una regione metropolitana. L’utilizzo di questa dimensione è utile se desideri informazioni più dettagliate di [Paesi](countries.md) ma non granulare come [Città](cities.md).

## Popola questa dimensione con i dati

Questa dimensione fa riferimento a regole di ricerca interne di Adobe. Il valore di ricerca si basa sull’indirizzo IP inviato con l’hit. Adobe di partner con [Elemento digitale](https://www.digitalelement.com/) per mantenere le ricerche tra indirizzo IP e paese. Questa dimensione funziona in modo predefinito per tutte le implementazioni.

## Elementi dimensionali

Gli elementi Dimension includono le aree geografiche e il paese in cui si trova l’area geografica. I valori di esempio includono `"California (United States)"`, `"Tokyo (Japan)"`, o `"Sao Paulo (Brazil)"`.

Alcuni elementi dimensionali possono includere `"AOL"`, un provider di servizi Internet per la connessione remota. Agli abbonati a questo servizio viene assegnato un punto di accesso in base al paese in cui è stabilito il loro numero di conto. Gli utenti AOL utilizzano l’indirizzo IP di questo punto di accesso. Poiché questa dimensione si basa sull’indirizzo IP, al posto della posizione effettiva del visitatore viene utilizzata la geolocalizzazione del punto di accesso.

## Differenze tra l&#39;ubicazione effettiva e quella riportata

Poiché questa dimensione si basa sull’indirizzo IP, alcuni scenari possono mostrare una differenza tra la posizione segnalata e la posizione effettiva:

* **Indirizzi IP che rappresentano proxy aziendali**: questi visitatori possono apparire come traffico proveniente dalla rete aziendale dell’utente, che può trovarsi in una posizione diversa se l’utente lavora in remoto.
* **Indirizzi IP per dispositivi mobili**: il targeting IP per dispositivi mobili funziona a diversi livelli a seconda della posizione e della rete. Vari vettori effettuano il backhaul del traffico IP attraverso punti di presenza centralizzati o regionali.
* **Utenti ISP satellite**: identificare la posizione specifica di questi utenti è difficile, in quanto generalmente sembrano provenire dalla posizione di uplink.
* **IP militari e governativi**: rappresenta il personale che viaggia per il mondo e che accede dalla propria sede principale, anziché dalla base o dall’ufficio in cui si trova attualmente.
* **Proxy che nascondono gli indirizzi IP per motivi di privacy**: servizi come Inoltro privato di Apple nascondono il vero indirizzo IP inviando in modo casuale i dati tramite un intermediario o un proxy. Questo proxy sostituisce quindi un indirizzo IP diverso prima di inoltrarlo all’Adobe.
