---
title: Frequenza di ritorno
description: Periodo di tempo compreso tra la visita corrente e la visita precedente.
feature: Dimensions
exl-id: 8ec31e17-a57d-416f-b471-c2c37a98d134
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 2%

---

# Frequenza di ritorno

La dimensione &quot;Frequenza di ritorno&quot; mostra il periodo di tempo che intercorre tra le visite dei visitatori di ritorno. Quando un visitatore ritorna sul tuo sito, Adobe osserva da quanto tempo è avvenuta la visita precedente e memorizza l’hit nell’elemento dimensionale appropriato. Questa dimensione è utile per valutare l’attrattiva del sito web e la sua rilevanza per i visitatori nel tempo. Può anche aiutare a identificare l&#39;impatto dei contenuti e delle promozioni del sito sui visitatori.

>[!TIP]
>
>Questa dimensione non include i visitatori nuovi.

## Popola questa dimensione con i dati

Questa dimensione funziona in modo predefinito per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

I dati per questa dimensione sono impostati sul primo hit della visita e persistono per l’intera visita. Il valore non può cambiare a metà visita.

## Elementi dimensionali

Gli elementi del Dimension includono contenitori basati sul tempo, a seconda del tempo trascorso dalla visita precedente.

* Meno di 1 giorno
* Da 1 a 3 giorni
* Da 3 a 7 giorni
* Da 7 a 14 giorni
* Da 14 giorni a 1 mese
* Più di 1 mese

## Gli elementi del Dimension vengono visualizzati in periodi fissi al di fuori dell’intervallo di date del progetto

Quando imposti l’intervallo di date di un progetto, in genere viene visualizzato l’attributo degli elementi dimensionali per le visite al di fuori dell’intervallo di date. Ad esempio, un visitatore accede al tuo sito a luglio e poi ritorna due volte nello stesso giorno di settembre. La dimensione Frequenza di ritorno per il mese di settembre mostrerebbe una visita in &quot;Più di 1 mese&quot; e una visita in &quot;Meno di 1 giorno&quot;.
