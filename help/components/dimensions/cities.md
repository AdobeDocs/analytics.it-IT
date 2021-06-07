---
title: Città
description: La città da cui ha avuto origine l'hit.
exl-id: c04525bb-50d6-4d28-b5dc-335d089e184b
source-git-commit: 9770f8e04089ff339d912d1787679257c87c7caa
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 0%

---

# Città

La dimensione &quot;Città&quot; indica la città da cui ha avuto origine l’hit. Questa dimensione è utile per determinare le origini delle città più popolari visitatori durante la visita del sito. Puoi usare questi dati per concentrarti sulla pubblicità locale in queste città, come cartelloni pubblicitari.

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento a regole di ricerca interne all’Adobe. Il valore di ricerca si basa sull’indirizzo IP inviato con l’hit. Partner di Adobe con [Elemento digitale](https://www.digitalelement.com/) per mantenere le ricerche tra l’indirizzo IP e la città. Questa dimensione funziona come standard per tutte le implementazioni.

## Elementi Dimension

Gli articoli per Dimension includono le città di tutto il mondo. I valori di esempio includono `"New York (New York, United States)"`, `"Bangalore (Karnataka, India)"` o `"London (London, United Kingdom)"`.

Alcuni elementi dimensionali possono includere `"AOL"`, un provider di servizi Internet dial-up. Agli abbonati a questo servizio viene assegnato un punto di accesso in base al paese in cui è stabilito il loro numero di account. Gli utenti AOL utilizzano l&#39;indirizzo IP di questo punto di accesso. Poiché questa dimensione si basa sull’indirizzo IP, al posto della posizione effettiva del visitatore viene utilizzata la geolocalizzazione del punto di accesso.

## Differenze tra ubicazione effettiva e segnalata

Poiché questa dimensione è basata sull’indirizzo IP, alcuni scenari possono mostrare una differenza tra la posizione segnalata e la posizione effettiva:

* **Indirizzi IP che rappresentano proxy** aziendali: Questi visitatori possono apparire come traffico proveniente dalla rete aziendale dell&#39;utente, che può essere diversa se l&#39;utente lavora in remoto.
* **Indirizzi** IP mobili: Il targeting IP per dispositivi mobili funziona a diversi livelli a seconda della posizione e della rete. Un certo numero di vettori ritorna il traffico IP attraverso punti di presenza centralizzati o regionali.
* **Utenti** ISP satellitari: Identificare la posizione specifica di questi utenti è difficile, in quanto in genere sembrano originare dalla posizione di uplink.
* **IP** militari e governativi: Rappresenta il personale che viaggia per il mondo e che entra nella propria posizione di casa, piuttosto che la base o l&#39;ufficio in cui si trovano attualmente.
