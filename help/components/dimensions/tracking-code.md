---
title: Codice di tracciamento
description: Nome del codice di tracciamento o della campagna.
translation-type: tm+mt
source-git-commit: 178e372e63c436268a1f7028d986504983430b2f
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 1%

---


# Codice di tracciamento

La dimensione &quot;Codice tracciamento&quot; elenca i nomi dei codici di tracciamento sul sito. Questa dimensione viene in genere raccolta utilizzando i parametri delle stringhe di query. È possibile inserire collegamenti con valori di parametro di stringa di query diversi in diverse aree di Internet. Questa dimensione indica quali collegamenti sono stati i più efficaci nel veicolare il traffico verso il sito.

## Compilare questa dimensione con i dati

Questa dimensione recupera i dati dalla stringa [`v0` di](/help/implement/validate/query-parameters.md) query nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la [`campaign`](/help/implement/vars/page-vars/campaign.md) variabile.

## Elementi Dimension

Gli elementi di Dimension includono i nomi dei codici di monitoraggio sul sito. L&#39;organizzazione determina quali elementi dimensionali specifici si desidera utilizzare.

## Confronta la dimensione del codice di tracciamento con i canali di marketing che raccolgono i codici di tracciamento

Alcuni utenti che configurano le regole di elaborazione dei canali di marketing configurano una regola che prende tutti i valori utilizzati nella dimensione del codice di tracciamento. Anche se si tratta di una pratica eccellente, sono diversi a causa delle differenze inerenti all&#39;elaborazione e all&#39;architettura. Nell&#39;elenco seguente viene illustrato il motivo per cui queste due dimensioni, anche se a colpo d&#39;occhio simili, non possono essere confrontate l&#39;una con l&#39;altra.

* **Canali precedenti nelle regole** di elaborazione: Le regole di elaborazione dei canali di marketing più in alto nell’elenco possono impedire l’attribuzione degli hit al canale di marketing dei codici di tracciamento. Ad esempio:

   1. Hai impostato &#39;Social Network&#39; come prima regola, e &#39;Tracking codes&#39; come seconda.
   2. Un utente pubblica un collegamento al tuo sito contenente un codice di tracciamento su un sito di social media, e molti dei loro amici fanno clic sul collegamento al tuo sito.

   Poiché &#39;Social Network&#39; è la prima regola di elaborazione del canale di marketing, questi utenti attribuiscono al canale di marketing &#39;Social Network&#39;, e non al canale di marketing dei codici di tracciamento.
* **Altri canali di marketing possono rubare l&#39;attribuzione**: Quando hai a che fare con una dimensione standard Codici di tracciamento, non devi preoccuparti che altre parti del tuo sito rubino l&#39;attribuzione. Tuttavia, con i canali Marketing, un utente può corrispondere a una regola diversa, attribuendo un&#39;attribuzione diversa. Ad esempio:
   1. Il primo canale contiene &#39;Tracking codes&#39; e &#39;Direct&#39; come secondo canale.
   2. Inizialmente, un utente arriva sul sito tramite un codice di tracciamento, ma poi se ne va.
   3. Il giorno successivo, digitano l’URL nella barra degli indirizzi, quindi fanno un acquisto.

   Il canale di marketing dei codici di tracciamento non riceverebbe l&#39;ultimo credito per l&#39;acquisto. Invece, passava al canale di marketing &quot;diretto&quot;.
* **Differenze** di scadenza: I canali di marketing hanno una scadenza continua di 30 giorni per il coinvolgimento dei visitatori, a prescindere dal fatto che un canale sia stato toccato o meno. I codici di tracciamento hanno una scadenza in base a quando è stata impostata la variabile. Ad esempio:
   1. Hai una scadenza del coinvolgimento del visitatore di 30 giorni e hai anche configurato la dimensione Codice di tracciamento per scadere dopo 30 giorni.
   2. Un utente accede al sito tramite un codice di tracciamento. Sfogliano il sito e poi se ne vanno.
   3. Tre settimane dopo, tornano senza un codice di tracciamento o un canale di marketing, e poi se ne vanno di nuovo.
   4. Altre due settimane dopo (cinque settimane dopo la visita iniziale), tornano senza un codice di tracciamento o un canale di marketing, quindi effettuano un acquisto.
   L&#39;utente ha effettuato un acquisto oltre i 30 giorni, ma non è mai rimasto inattivo per più di 30 giorni. Vedreste i ricavi attribuiti al canale di marketing dei codici di tracciamento, ma non per la dimensione standalone.
