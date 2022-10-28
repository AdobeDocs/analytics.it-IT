---
title: Paesi
description: Il paese da cui ha avuto origine l'hit.
feature: Dimensions
exl-id: 47704b08-215d-4d2d-bcd4-1789e308c1c6
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 0%

---

# Paesi

La dimensione &quot;Paesi&quot; indica il paese da cui ha avuto origine l&#39;hit. Questa dimensione è utile per determinare da quali paesi provengono i visitatori più popolari quando visitano il sito. Puoi utilizzare questi dati per concentrarti sulle attività di marketing in questi paesi, oppure assicurati che l’esperienza del tuo sito sia ottimale nei paesi con lingue primarie diverse.

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento a regole di ricerca interne all’Adobe. Il valore di ricerca si basa sull’indirizzo IP inviato con l’hit. partner di Adobe con [Elemento digitale](https://www.digitalelement.com/) per mantenere le ricerche tra l’indirizzo IP e il paese. Questa dimensione funziona come standard per tutte le implementazioni.

## Elementi Dimension

Gli articoli per Dimension includono paesi in tutto il mondo. I valori di esempio includono `"United States"`, `"United Kingdom"`oppure `"India"`.

## Differenze tra ubicazione effettiva e segnalata

Poiché questa dimensione è basata sull’indirizzo IP, alcuni scenari possono mostrare una differenza tra la posizione segnalata e la posizione effettiva:

* **Indirizzi IP che rappresentano proxy aziendali**: Questi visitatori possono apparire come traffico proveniente dalla rete aziendale dell&#39;utente, che può essere diversa se l&#39;utente lavora in remoto.
* **Indirizzi IP mobili**: Il targeting IP per dispositivi mobili funziona a diversi livelli a seconda della posizione e della rete. Un certo numero di vettori ritorna il traffico IP attraverso punti di presenza centralizzati o regionali.
* **Utenti ISP satellitari**: Identificare la posizione specifica di questi utenti è difficile, in quanto in genere sembrano originare dalla posizione di uplink.
* **IP militari e governativi**: Rappresenta il personale che viaggia per il mondo e che entra nella propria posizione di casa, piuttosto che la base o l&#39;ufficio in cui si trovano attualmente.
