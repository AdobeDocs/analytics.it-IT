---
title: Stati degli Stati Uniti
description: Stato USA del visitatore.
feature: Dimensions
exl-id: d4506e59-c1ff-4348-912d-c1ad73278f56
source-git-commit: 146d622f370fd7469a8e5f0f2fe68cb31fa91844
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 1%

---

# Stato USA

La dimensione &quot;Stato USA&quot; riporta lo stato del visitatore negli Stati Uniti d’America. È simile al [Aree geografiche](regions.md) , tranne per il fatto che questa dimensione è specifica per gli Stati Uniti. L’utilizzo di questa dimensione è utile se desideri informazioni più dettagliate di [Paesi](countries.md) ma non granulare come [Città](cities.md).

## Popola questa dimensione con i dati

Questa dimensione fa riferimento a regole di ricerca interne di Adobe. Il valore di ricerca si basa sull’indirizzo IP inviato con l’hit. Adobe di partner con [Elemento digitale](https://www.digitalelement.com/) per mantenere le ricerche tra indirizzo IP e paese. Questa dimensione funziona in modo predefinito per tutte le implementazioni.

## Elementi dimensionali

Gli elementi Dimension includono le aree geografiche e il paese in cui si trova l’area geografica. I valori di esempio includono `"California"`, `"Texas"`, o `"Virginia"`. Elemento dimensione `"Unspecified"` include tutto il traffico internazionale al di fuori degli Stati Uniti.

Questa dimensione può includere `"AOL"`, un provider di servizi Internet per la connessione remota. Agli abbonati a questo servizio viene assegnato un punto di accesso. Gli utenti AOL utilizzano l’indirizzo IP di questo punto di accesso. Poiché questa dimensione si basa sull’indirizzo IP, al posto della posizione effettiva del visitatore viene utilizzata la geolocalizzazione del punto di accesso.

## Differenze tra l&#39;ubicazione effettiva e quella riportata

Poiché questa dimensione si basa sull’indirizzo IP, alcuni scenari possono mostrare una differenza tra la posizione segnalata e la posizione effettiva:

* **Indirizzi IP che rappresentano proxy aziendali**: questi visitatori possono apparire come traffico proveniente dalla rete aziendale dell’utente, che può trovarsi in una posizione diversa se l’utente lavora in remoto.
* **Indirizzi IP per dispositivi mobili**: il targeting IP per dispositivi mobili funziona a diversi livelli a seconda della posizione e della rete. Vari vettori effettuano il backhaul del traffico IP attraverso punti di presenza centralizzati o regionali.
* **Utenti ISP satellite**: identificare la posizione specifica di questi utenti è difficile, in quanto generalmente sembrano provenire dalla posizione di uplink.
* **IP militari e governativi**: rappresenta il personale che viaggia per il mondo e che accede dalla propria sede principale, anziché dalla base o dall’ufficio in cui si trova attualmente.
* **Proxy che nascondono gli indirizzi IP per motivi di privacy**: servizi come Inoltro privato di Apple nascondono il vero indirizzo IP inviando in modo casuale i dati tramite un intermediario o un proxy. Questo proxy sostituisce quindi un indirizzo IP diverso prima di inoltrarlo all’Adobe.
