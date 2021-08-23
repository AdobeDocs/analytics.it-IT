---
title: Frequenza di ritorno
description: Intervallo di tempo intasato tra la visita corrente e quella precedente.
exl-id: 8ec31e17-a57d-416f-b471-c2c37a98d134
source-git-commit: d49a1eac29b949af04e6cefece9f1433fddf19cc
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 1%

---

# Frequenza di ritorno

La dimensione &quot;Frequenza di ritorno&quot; mostra il tempo che trascorre tra le visite dei visitatori di ritorno. Quando un visitatore ritorna al tuo sito, un Adobe controlla da quanto tempo è stata effettuata la visita precedente e inserisce l’hit nell’elemento della dimensione appropriato. Questa dimensione è utile per misurare l’attrattiva e la pertinenza del sito web per i visitatori nel tempo. Inoltre, può aiutare a identificare l&#39;impatto dei contenuti e delle promozioni del tuo sito sui visitatori.

>[!TIP]
>
>Questa dimensione non include i visitatori nuovi.

## Popolare questa dimensione con i dati

Questa dimensione funziona come standard per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

I dati per questa dimensione vengono impostati sul primo hit della visita e persistono per l’intera visita. Il valore non può cambiare a metà visita.

## Elementi Dimension

Gli elementi di Dimension includono periodi fissi basati sul tempo, a seconda del tempo trascorso dalla visita precedente.

* Meno di 1 giorno
* da 1 a 3 giorni
* da 3 a 7 giorni
* da 7 a 14 giorni
* da 14 a 1 mese
* Più lungo di un mese

## Gli elementi di Dimension vengono visualizzati sotto i bucket al di fuori dell’intervallo date del progetto

Quando imposti l’intervallo di date di un progetto, è comune visualizzare l’attributo elementi dimensionali alle visite al di fuori dell’intervallo di date. Ad esempio, un visitatore accede al tuo sito a luglio, quindi torna due volte nello stesso giorno di settembre. La dimensione della frequenza di ritorno per il mese di settembre mostrerebbe una visita sotto &quot;Più lunga di 1 mese&quot; e una visita sotto &quot;Meno di 1 giorno&quot;.
