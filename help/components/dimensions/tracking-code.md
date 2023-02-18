---
title: Codice di tracciamento
description: Nome del codice di tracciamento o della campagna.
feature: Dimensions
exl-id: e4f70552-6946-4974-a9e2-928faf563ecd
source-git-commit: e46b15eedda78303e6e29faceea6db8483eee277
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 2%

---

# Codice di tracciamento

La dimensione &quot;Tracking Code&quot; (Codice di tracciamento) elenca i nomi dei codici di tracciamento sul sito. È possibile inserire collegamenti con diversi valori dei parametri della stringa di query in diverse posizioni su Internet. Questa dimensione ti aiuta a capire quali collegamenti sono stati i più efficaci nel indirizzare il traffico verso il tuo sito.

Le stringhe di query sul codice di tracciamento sono comuni nelle e-mail, negli annunci pubblicitari, nei post sui social media e in altre attività di marketing utilizzate dalla tua organizzazione.

## Popolare questa dimensione con i dati

Questa dimensione recupera i dati dal [`v0` stringa di interrogazione](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la variabile [`campaign`](/help/implement/vars/page-vars/campaign.md) variabile.

## Elementi dimensionali

Gli elementi di Dimension includono i nomi dei codici di tracciamento sul sito. L’organizzazione determina gli elementi dimensionali specifici da utilizzare. Vedi [Tracciamento delle campagne](/help/implement/use-cases/campaign-tracking.md) per ulteriori informazioni.

## Confrontare la dimensione del codice di tracciamento con i canali di marketing che raccolgono i codici di tracciamento

Alcuni utenti che impostano le regole di elaborazione dei canali di marketing configurano una regola che prende tutti i valori utilizzati nella dimensione del codice di tracciamento. Anche se è una pratica eccellente, sono diversi a causa delle intrinseche differenze di elaborazione e di architettura. L’elenco seguente spiega perché queste due dimensioni, anche se a colpo d’occhio simili, non possono essere confrontate tra loro.

* **Canali precedenti nelle regole di elaborazione**: Le regole di elaborazione dei canali di marketing più in alto nell’elenco possono impedire l’attribuzione degli hit al canale di marketing dei codici di tracciamento. Ad esempio:

   1. Hai impostato &#39;Social Networks&#39; come prima regola e &#39;Tracking codes&#39; come secondo.
   2. Un utente pubblica un collegamento al tuo sito contenente un codice di tracciamento su un sito di social media e diversi dei loro amici fanno clic su tale collegamento al tuo sito.

   Poiché &quot;Social Networks&quot; è la prima regola di elaborazione del canale di marketing, questi utenti attribuiscono al canale di marketing &quot;Social Networks&quot; e non al canale di marketing dei codici di tracciamento.
* **Altri canali di marketing possono rubare l’attribuzione**: Quando si gestisce una dimensione standard dei codici di tracciamento, non è necessario preoccuparsi che altre parti del sito rubino l’attribuzione. Tuttavia, con i canali di marketing, un utente può corrispondere a una regola diversa, attribuendo attribuzioni diverse. Ad esempio:
   1. Hai &quot;Codici di tracciamento&quot; come primo canale e &quot;Diretto&quot; come secondo canale.
   2. Un utente arriva inizialmente al tuo sito tramite un codice di tracciamento, ma poi se ne va.
   3. Il giorno successivo, digitano il tuo URL nella loro barra degli indirizzi, quindi effettuano un acquisto.

   Il canale di marketing dei codici di tracciamento non riceverebbe il credito dell’ultimo contatto per quell’acquisto. Al contrario, andrebbe al canale di marketing &quot;diretto&quot;.
* **Differenze di scadenza**: I canali di marketing hanno una scadenza continua di 30 giorni di coinvolgimento dei visitatori, che siano stati toccati o meno un canale. I codici di tracciamento hanno una scadenza basata su quando è stata impostata la variabile. Ad esempio:
   1. Hai una scadenza di coinvolgimento del visitatore di 30 giorni e hai anche configurato la dimensione del codice di tracciamento per scadere dopo 30 giorni.
   2. Un utente arriva al tuo sito tramite un codice di tracciamento. Sfogliano il sito, poi se ne vanno.
   3. Tre settimane dopo, tornano senza un codice di tracciamento o un canale di marketing, poi se ne vanno di nuovo.
   4. Altre due settimane più tardi (cinque settimane dopo la visita iniziale), tornano senza un codice di tracciamento o un canale di marketing, quindi effettuano un acquisto.
   L’utente ha infine effettuato un acquisto oltre i 30 giorni, ma non è mai stato inattivo per più di 30 giorni. Vedrai i ricavi attribuiti al canale di marketing dei codici di tracciamento, ma non per la dimensione autonoma.
