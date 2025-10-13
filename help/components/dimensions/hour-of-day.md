---
title: Ora del giorno
description: L’ora numerica del giorno, indipendentemente dal giorno.
feature: Dimensions
exl-id: b9361534-7e58-41ed-9a38-c02aeed7a2d8
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 9%

---

# Ora del giorno

La dimensione &#39;Ora del giorno&#39; [dimensione](overview.md) riporta l&#39;ora numerica di un dato giorno come elemento dimensione. Ad esempio, se un rapporto si estende dal 1° gennaio al 7 gennaio, la prima ora di ogni giorno si raggruppa nello stesso elemento dimensionale. Questo rapporto è utile se desideri un rapporto suddiviso per ora del giorno relativa, ma non vuoi ore statiche come elementi dimensionali. È particolarmente utile come dimensione nei rapporti pianificati, in quanto questa dimensione viene aggregata all’intervallo di date selezionato.

Questa dimensione si basa sul fuso orario della suite di rapporti e non su quello locale del visitatore. Ad esempio, se la suite di rapporti è in Fuso orario e un visitatore in California visita il tuo sito alle 00:00 (ora del Pacifico), gli hit vengono raggruppati sotto l’elemento di dimensione :00. `11:00 AM` Se desideri una dimensione che registri l&#39;ora del visitatore locale, Adobe consiglia di utilizzare il plug-in [getTimeParting](/help/implement/vars/plugins/gettimeparting.md).

## Popolare questa dimensione con i dati

Questa dimensione funziona in modo predefinito per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi dimensionali

Gli elementi di Dimension includono `12:00 AM` - `11:00 PM`, che rappresenta l&#39;ora del giorno in cui si è verificato l&#39;hit (arrotondato per difetto). Ad esempio, se un hit è stato generato alle 15:00, viene raggruppato sotto l&#39;elemento dimensionale :58.`3:00 PM`

## Ora legale

L&#39;ora legale è una pratica in cui gli orologi sono impostati un&#39;ora avanti in primavera e un&#39;ora indietro in autunno. Se il fuso orario di una suite di rapporti utilizza l’ora legale, Adobe regola i dati di conseguenza per tale ora.

* **Quando inizia l&#39;ora legale**: in marzo, nei rapporti viene in genere visualizzato un intervallo di un&#39;ora nei dati in cui inizia l&#39;ora legale. L’ora non esiste, quindi non fa parte della raccolta dati. Tieni presente che una piccola quantità di dati può comunque arrivare a quest’ora. I server di raccolta dati di Adobe impiegano diversi secondi (fino a un minuto) per prendere in considerazione le regolazioni dell’ora legale.
* **Al termine dell&#39;ora legale**: in novembre, nei report viene in genere visualizzata un&#39;ora a doppia sovrapposizione in cui termina l&#39;ora legale. L’ora si è verificata due volte, quindi entrambe le ore sono aggregate nei rapporti.
