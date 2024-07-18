---
title: Stati degli Stati Uniti
description: Stato USA del visitatore.
feature: Dimensions
exl-id: d4506e59-c1ff-4348-912d-c1ad73278f56
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 2%

---

# Stato USA

La &#39;dimensione Stati Uniti&#39; [dimension](overview.md) riporta lo stato del visitatore negli Stati Uniti d&#39;America. È simile alla dimensione [Aree](regions.md), con la differenza che questa dimensione è specifica degli Stati Uniti. L&#39;utilizzo di questa dimensione è utile se desideri informazioni più dettagliate di [Paesi](countries.md) ma non granulari come [Città](cities.md).

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento a regole di ricerca interne di Adobe. Il valore di ricerca si basa sull’indirizzo IP inviato con l’hit. Adobe di partner con [elemento digitale](https://www.digitalelement.com/) per mantenere le ricerche tra indirizzo IP e paese.

* Ad AppMeasurement, le implementazioni di questa dimensione sono pronte all’uso.
* Per le implementazioni Web SDK, abilita [!UICONTROL Geo Lookup] quando [si configura uno stream di dati](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=it).

## Elementi dimensionali

Gli elementi Dimension includono le aree geografiche e il paese in cui si trova l’area geografica. I valori di esempio includono `"California"`, `"Texas"` o `"Virginia"`. L&#39;elemento dimensione `"Unspecified"` include tutto il traffico internazionale al di fuori degli Stati Uniti.

Questa dimensione può includere `"AOL"`, un provider di servizi Internet di connessione remota. Agli abbonati a questo servizio viene assegnato un punto di accesso. Gli utenti AOL utilizzano l’indirizzo IP di questo punto di accesso. Poiché questa dimensione si basa sull’indirizzo IP, al posto della posizione effettiva del visitatore viene utilizzata la geolocalizzazione del punto di accesso.

## Differenze tra l&#39;ubicazione effettiva e quella riportata

Poiché questa dimensione si basa sull’indirizzo IP, alcuni scenari possono mostrare una differenza tra la posizione segnalata e la posizione effettiva:

* **Indirizzi IP che rappresentano proxy aziendali**: questi visitatori possono essere visualizzati come traffico proveniente dalla rete aziendale dell&#39;utente, che può essere una posizione diversa se l&#39;utente lavora in remoto.
* **Indirizzi IP per dispositivi mobili**: il targeting IP per dispositivi mobili funziona a vari livelli a seconda della posizione e della rete. Alcuni vettori effettuano il backhaul del traffico IP attraverso punti di presenza centralizzati o regionali.
* **Utenti ISP satellite**: identificare la posizione specifica di questi utenti è difficile, in quanto in genere sembrano provenire dalla posizione uplink.
* **IP militari e governativi**: rappresenta il personale che viaggia in tutto il mondo e che entra attraverso la propria sede principale, anziché la base o l&#39;ufficio in cui si trova attualmente.
* **Proxy che nascondono gli indirizzi IP per motivi di privacy**: servizi come Inoltro privato di Apple nascondono l&#39;indirizzo IP effettivo inviando i dati in modo casuale tramite un intermediario o un proxy. Questo proxy sostituisce quindi un indirizzo IP diverso prima di inoltrarlo all’Adobe.
