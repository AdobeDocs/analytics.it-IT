---
title: Stati Uniti
description: Stato USA del visitatore.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 0%

---


# Stato USA

La dimensione &quot;Stato USA&quot; indica lo stato del visitatore negli Stati Uniti d’America. È simile alla dimensione [Regioni](regions.md) , con la differenza che questa dimensione è specifica per gli Stati Uniti. L&#39;utilizzo di questa dimensione è utile se si desidera un&#39;analisi più dettagliata di [Paesi](countries.md) , ma non granulare come [Città](cities.md).

## Compilare questa dimensione con i dati

Questa dimensione fa riferimento a regole di ricerca interne ad Adobe. Il valore di ricerca si basa sull&#39;indirizzo IP inviato con l&#39;hit. Adobe collabora con [Digital Element](https://www.digitalelement.com/) per mantenere le ricerche tra l&#39;indirizzo IP e il paese. Questa dimensione funziona automaticamente per tutte le implementazioni.

>[!TIP]
>
>Se l&#39;azienda rispetta le severe normative sulla privacy laddove l&#39; [oscuramento dell&#39;indirizzo](/help/admin/admin/general-acct-settings-admin.md) IP non è sufficiente, puoi richiedere di disabilitare completamente i dati sulla geolocalizzazione. Contatta l&#39;Assistenza clienti con l&#39;ID suite di rapporti e richiedi di disattivare &#39;Geografia&#39; per la suite di rapporti.

## Elementi dimensione

Gli elementi dimensione includono le regioni e il paese in cui risiede la regione. I valori di esempio includono `"California"`, `"Texas"`, o `"Virginia"`. L&#39;elemento dimensione `"Unspecified"` include tutto il traffico internazionale al di fuori degli Stati Uniti.

## Differenze tra la posizione segnalata e quella effettiva

Poiché questa dimensione è basata sull’indirizzo IP, alcuni scenari possono mostrare una differenza tra la posizione segnalata e la posizione effettiva:

* **Indirizzi IP che rappresentano proxy** aziendali: Questi visitatori possono apparire come traffico proveniente dalla rete aziendale dell&#39;utente, che può essere una posizione diversa se l&#39;utente lavora in remoto.
* **Indirizzi** IP mobili: Il targeting IP per dispositivi mobili funziona a vari livelli, a seconda della posizione e della rete. Un certo numero di vettori ritorna il traffico IP attraverso punti di presenza centralizzati o regionali.
* **Utenti** ISP via satellite: Identificare la posizione specifica di questi utenti è difficile, in quanto in genere sembrano provenire dalla posizione di uplink.
* **IP** militari e governativi: Rappresenta il personale che viaggia in tutto il mondo e che accede attraverso la propria sede, anziché la base o l&#39;ufficio in cui si trova attualmente.
