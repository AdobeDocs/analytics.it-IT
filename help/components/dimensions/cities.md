---
title: Città
description: La città da cui ha avuto origine l’hit.
feature: Dimensions
exl-id: c04525bb-50d6-4d28-b5dc-335d089e184b
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 1%

---

# Città

Le &quot;Città&quot; [dimensione](overview.md) segnala la città da cui ha avuto origine l’hit. Questa dimensione è utile per determinare da cosa provengono i visitatori delle città più popolari quando visitano il tuo sito. Potreste usare questi dati per concentrarvi sulla pubblicità locale in queste città, come cartelloni o pubblicità.

## Popola questa dimensione con i dati

Questa dimensione fa riferimento a regole di ricerca interne di Adobe. Il valore di ricerca si basa sull’indirizzo IP inviato con l’hit. Adobe di partner con [Elemento digitale](https://www.digitalelement.com/) per mantenere le ricerche tra indirizzo IP e città.

* Ad AppMeasurement, le implementazioni di questa dimensione sono pronte all’uso.
* Per le implementazioni dell’SDK web, abilita [!UICONTROL Geo Lookup] quando [configurazione di uno stream di dati](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html).

## Elementi dimensionali

Gli elementi Dimension includono città in tutto il mondo. I valori di esempio includono `"New York (New York, United States)"`, `"Bangalore (Karnataka, India)"`, o `"London (London, United Kingdom)"`.

Alcuni elementi dimensionali possono includere `"AOL"`, un provider di servizi Internet per la connessione remota. Agli abbonati a questo servizio viene assegnato un punto di accesso in base al paese in cui è stabilito il loro numero di conto. Gli utenti AOL utilizzano l’indirizzo IP di questo punto di accesso. Poiché questa dimensione si basa sull’indirizzo IP, al posto della posizione effettiva del visitatore viene utilizzata la geolocalizzazione del punto di accesso.

## Differenze tra l&#39;ubicazione effettiva e quella riportata

Poiché questa dimensione si basa sull’indirizzo IP, alcuni scenari possono mostrare una differenza tra la posizione segnalata e la posizione effettiva:

* **Indirizzi IP che rappresentano proxy aziendali**: questi visitatori possono apparire come traffico proveniente dalla rete aziendale dell’utente, che può trovarsi in una posizione diversa se l’utente lavora in remoto.
* **Indirizzi IP per dispositivi mobili**: il targeting IP per dispositivi mobili funziona a diversi livelli a seconda della posizione e della rete. Alcuni vettori effettuano il backhaul del traffico IP attraverso punti di presenza centralizzati o regionali.
* **Utenti ISP satellite**: identificare la posizione specifica di questi utenti è difficile, in quanto generalmente sembrano provenire dalla posizione di uplink.
* **IP militari e governativi**: rappresenta il personale che viaggia per il mondo e che accede dalla propria sede principale, anziché dalla base o dall’ufficio in cui si trova attualmente.
* **Proxy che nascondono gli indirizzi IP per motivi di privacy**: servizi come Inoltro privato di Apple nascondono il vero indirizzo IP inviando in modo casuale i dati tramite un intermediario o un proxy. Questo proxy sostituisce quindi un indirizzo IP diverso prima di inoltrarlo all’Adobe.
