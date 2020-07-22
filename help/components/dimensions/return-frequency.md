---
title: Frequenza di ritorno
description: Il tempo trascorso tra la visita corrente e quella precedente è aumentato notevolmente.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 0%

---


# Frequenza di ritorno

La dimensione &quot;Frequenza di ritorno&quot; mostra il tempo che trascorre tra le visite dei visitatori di ritorno. Quando un visitatore ritorna al sito, Adobe verifica da quanto tempo è stata effettuata la visita precedente e inserisce l’hit nell’elemento dimensione appropriato. Questa dimensione è utile per misurare l&#39;attrattiva e la rilevanza del sito Web per i visitatori nel tempo. Può anche aiutare a identificare l&#39;impatto dei contenuti e delle promozioni del sito sui visitatori.

>[!TIP]
>
>Questa dimensione non include i visitatori per la prima volta.

## Compilare questa dimensione con i dati

Questa dimensione funziona automaticamente per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

I dati per questa dimensione vengono impostati sul primo hit della visita e persistono per l’intera visita. Il valore non può essere modificato durante la visita intermedia.

## Elementi dimensione

Gli elementi dimensione includono intervalli di tempo, a seconda del tempo trascorso dalla visita precedente.

* Meno di 1 giorno
* Da 1 a 3 giorni
* Da 3 a 7 giorni
* da 7 a 14 giorni
* Da 14 a 1 mese
* Più lungo di 1 mese

## Gli elementi dimensione vengono visualizzati sotto i bucket al di fuori dell&#39;intervallo di date del progetto

Quando imposti l&#39;intervallo di date di un progetto, è comune visualizzare l&#39;attributo degli elementi dimensione alle visite al di fuori dell&#39;intervallo di date. Ad esempio, un visitatore accede al sito a luglio, quindi ritorna due volte nello stesso giorno in settembre. La dimensione della frequenza di ritorno per il mese di settembre mostrerebbe una visita in &#39;Più di 1 mese&#39;, e una visita in &#39;Meno di 1 giorno&#39;.