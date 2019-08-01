---
description: La figura seguente mostra il funzionamento della raccolta dati.
keywords: DFA
seo-description: La figura seguente mostra il funzionamento della raccolta dati.
seo-title: Raccolta dati in tempo reale Integrazione Adobe
solution: Analytics
title: Raccolta dati in tempo reale Integrazione Adobe
topic: Connettori dati
uuid: 5 dce 319 c -7 d 4 b -4475-8 e 6 d-dc 5 c 972 a 82 e 9
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Adobe Integration: Real-Time Data Collection{#adobe-integration-real-time-data-collection}

La figura seguente mostra il funzionamento della raccolta dati.

![](assets/DFA_data_collection.png)

La parte raccolta dati dell'integrazione Adobe inizia quando il visitatore arriva alla pagina di destinazione (1). Il codice di raccolta dati Adobe in esecuzione sulla pagina di destinazione non dispone della conoscenza della cronologia con gli annunci serviti. Il team Google DFA ha coordinato un servizio in esecuzione sul server DFA Floodlight per consentire al codice Adobe di interrogare le informazioni pubblicitarie sul visitatore attualmente sul sito (2). Per ottenere questi dati, ritarda temporaneamente il beacon immagine Adobe e richiede i dati da Floodlight Server.

Una volta che i dati arrivano o richiedono troppo tempo, l'hit viene attivato ai server di tracciamento Adobe (3).

The Integrate module is a special core Adobe JavaScript module which causes the Adobe image beacon to delay, waiting on a 3rd party request for a specific amount of time ( *`s.maxDelay`*). *`s.maxDelay`* definisce per quanto tempo il modulo Integra attenderà i dati da DFA Floodlight Server prima di passare il tag immagine al browser del visitatore. Questo comportamento è importante per fare ancora in modo che i dati dei visitatori di base vengano raccolti, anche quando i server DFA Floodlight sono stati ridotti o caricati troppo. If the Floodlight data arrives before *`s.maxDelay`* has expired, the Adobe tracking data will be fired immediately, and will contain the additional DFA data.

Quando si verifica un timeout, il codice della pagina può specificare un evento Adobe Reports &amp; Analytics da utilizzare come Evento Timeout. This event is useful when diagnosing problems with the integration, or when adjusting *`s.maxDelay`*. In cases where there are excessive timeouts, increase *`s.maxDelay`*. *`s.maxDelay`* può essere impostata anche su un valore troppo elevato, in tal caso i visitatori potrebbero avere il rischio di lasciare il sito prima della scadenza *`s.maxDelay`* del timer. For more discussion on this topic, see [Tuning s.maxDelay](../dfa-data-connector-analytics/dfa-integration/dfa-tuning-s-maxlelay.md#concept-6deb28eee18e414db220d6009d449f0d).

A volte il server Floodlight risponde con errori relativi al visitatore. Ciò si verifica in genere quando il server Floodlight non sa nulla sul visitatore, perché il visitatore non ha ancora visto annunci pubblicitari o non ha un cookie visitatore DFA. Il codice della pagina può specificare una variabile Conversione personalizzata (evar) che raccolga questi errori e può essere utile per risolvere problemi di implementazione o segnalare problemi di implementazione con la transazione Google. Gli errori più comuni non sono History (Cronologia), No Cookie (Nessun cookie), Query Error (Errore query) e Opted Out (Disattivato), come descritto nella tabella seguente:

| Errore | Nome | Descrizione |
|---|---|---|
| nh | Nessuna cronologia | Il visitatore non ha visualizzato o fatto clic su annunci. |
| nc | Nessun cookie | Il visitatore non dispone di un cookie visitatore DFA. |
| qe | Errore query | Si sono verificati dei dati di query per il server floodlight. |
| oo | Rifiuto | Il visitatore ha acconsentito al tracciamento di impression/clic su Google. |

