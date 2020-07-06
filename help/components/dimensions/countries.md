---
title: Paesi
description: Il paese da cui ha avuto origine l’hit.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 0%

---


# Paesi

La dimensione &quot;Paesi&quot; indica il paese da cui ha avuto origine l&#39;hit. Questa dimensione è utile per determinare da quali paesi provengono i visitatori più popolari durante la visita del sito. Puoi utilizzare questi dati per concentrarti sulle attività di marketing in questi paesi, o per essere certo che la tua esperienza sul sito sia ottimale in paesi con lingue primarie diverse.

## Compilare questa dimensione con i dati

Questa dimensione fa riferimento a regole di ricerca interne ad Adobe. Il valore di ricerca si basa sull&#39;indirizzo IP inviato con l&#39;hit. Adobe collabora con [Digital Element](https://www.digitalelement.com/) per mantenere le ricerche tra l&#39;indirizzo IP e il paese. Questa dimensione funziona automaticamente per tutte le implementazioni.

>[!TIP]
>
>Se l&#39;azienda rispetta le severe normative sulla privacy laddove l&#39; [oscuramento dell&#39;indirizzo](/help/admin/admin/general-acct-settings-admin.md) IP non è sufficiente, puoi richiedere di disabilitare completamente i dati sulla geolocalizzazione. Contatta l&#39;Assistenza clienti con l&#39;ID suite di rapporti e richiedi di disattivare &#39;Geografia&#39; per la suite di rapporti.

## Valori dimensione

I valori delle dimensioni comprendono i paesi di tutto il mondo. I valori di esempio includono `"United States"`, `"United Kingdom"`, o `"India"`.

## Differenze tra la posizione segnalata e quella effettiva

Poiché questa dimensione è basata sull’indirizzo IP, alcuni scenari possono mostrare una differenza tra la posizione segnalata e la posizione effettiva:

* **Indirizzi IP che rappresentano proxy** aziendali: Questi visitatori possono apparire come traffico proveniente dalla rete aziendale dell&#39;utente, che può essere una posizione diversa se l&#39;utente lavora in remoto.
* **Indirizzi** IP mobili: Il targeting IP per dispositivi mobili funziona a vari livelli, a seconda della posizione e della rete. Un certo numero di vettori ritorna il traffico IP attraverso punti di presenza centralizzati o regionali.
* **Utenti** ISP via satellite: Identificare la posizione specifica di questi utenti è difficile, in quanto in genere sembrano provenire dalla posizione di uplink.
* **IP** militari e governativi: Rappresenta il personale che viaggia in tutto il mondo e che accede attraverso la propria sede, anziché la base o l&#39;ufficio in cui si trova attualmente.
