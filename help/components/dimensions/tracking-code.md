---
title: Codice di tracciamento
description: Nome del codice di tracciamento o della campagna.
feature: Dimensions
exl-id: e4f70552-6946-4974-a9e2-928faf563ecd
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 3%

---

# Codice di tracciamento

Nel &#39;Codice di tracciamento&#39; [dimension](overview.md) sono elencati i nomi dei codici di tracciamento sul sito. Puoi inserire collegamenti con valori di parametri di stringhe di query diversi in posizioni diverse su Internet. Questa dimensione ti aiuta a capire quali collegamenti sono stati più efficaci nel traffico verso il tuo sito.

L’aggiunta di stringhe di query del codice di tracciamento è comune nelle e-mail, negli annunci pubblicitari, nei post sui social media e in altre attività di marketing utilizzate dalla tua organizzazione.

## Popolare questa dimensione con i dati

Questa dimensione recupera i dati dalla stringa di query [`v0`](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la variabile [`campaign`](/help/implement/vars/page-vars/campaign.md).

## Elementi dimensionali

Gli elementi di Dimension includono i nomi dei codici di tracciamento sul sito. L’organizzazione determina gli elementi dimensionali specifici che desideri utilizzare. Per ulteriori informazioni, consulta [Tracciamento campagna](/help/implement/use-cases/campaign-tracking.md).

## Confrontare la dimensione Codice di tracciamento con i canali di marketing che raccolgono i codici di tracciamento

Alcuni utenti che impostano regole di elaborazione per il canale di marketing configurano una regola che accetta tutti i valori utilizzati nella dimensione Codice di tracciamento. Sebbene siano una pratica eccellente, sono diversi a causa delle differenze intrinseche di elaborazione e architettura. L’elenco seguente spiega perché questi due metodi, anche se simili a colpo d’occhio, possono modificare il comportamento di attribuzione.

### Canali precedenti nelle regole di elaborazione

Le regole di elaborazione dei canali di marketing riportate più in alto nell’elenco possono impedire che gli hit vengano attribuiti al canale di marketing dei Codici di tracciamento. Ad esempio:

1. Hai &quot;Social Network&quot; impostato come prima regola e &quot;Codici di tracciamento&quot; come seconda.
2. Un utente pubblica un collegamento al sito contenente un codice di tracciamento su un sito di social media e diversi amici fanno clic su tale collegamento al sito.

Poiché Social Networks è la prima regola di elaborazione del canale di marketing, questi utenti attribuiscono al canale di marketing Social Networks e non al canale di marketing dei codici di tracciamento.

### Altri canali di marketing possono utilizzare l’attribuzione fino all’ultimo contatto

Quando hai a che fare con una dimensione Codici di tracciamento standard, non devi preoccuparti di altre parti del sito che rubano l’attribuzione. Tuttavia, con i canali di marketing, un utente può corrispondere a una regola diversa, dando un’attribuzione diversa. Ad esempio:

1. Hai &quot;Codici di tracciamento&quot; come primo canale e &quot;Diretto&quot; come secondo.
2. Un utente arriva inizialmente al sito tramite un codice di tracciamento, ma poi se ne va.
3. Il giorno successivo, digitano l’URL nella barra degli indirizzi, quindi effettuano un acquisto.

In questo esempio, il canale di marketing dei codici di tracciamento non riceverebbe il credito dell’ultimo contatto per tale acquisto. ma al canale di marketing diretto.


### Differenze di scadenza

I canali di marketing hanno una scadenza continua del coinvolgimento dei visitatori di 30 giorni, indipendentemente dal fatto che un canale sia stato toccato o meno. I codici di tracciamento hanno una scadenza in base a quando è stata impostata la variabile. Ad esempio:

1. Hai una scadenza del coinvolgimento dei visitatori di 30 giorni e hai anche configurato la dimensione Codice di tracciamento affinché scada dopo 30 giorni.
2. Un utente arriva al sito tramite un codice di tracciamento. Navigano nel sito, poi se ne vanno.
3. Tre settimane dopo, tornano senza un codice di tracciamento o un canale di marketing, e poi se ne vanno di nuovo.
4. Altre due settimane dopo (cinque settimane dalla visita iniziale), tornano senza un codice di tracciamento o un canale di marketing, quindi fanno un acquisto.

L’utente ha alla fine effettuato un acquisto oltre i 30 giorni, ma non è mai stato inattivo per più di 30 giorni. In questo caso, vedrai i ricavi attribuiti al canale di marketing dei codici di tracciamento, ma non per la dimensione del codice di tracciamento stessa.



