---
title: Ora del giorno
description: L’ora numerica del giorno, indipendentemente dal giorno.
feature: Dimensions
exl-id: b9361534-7e58-41ed-9a38-c02aeed7a2d8
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 3%

---

# Ora del giorno

La dimensione &quot;Ora del giorno&quot; riporta l’ora numerica di un dato giorno come elemento dimensione. Ad esempio, se un rapporto si estende dal 1° gennaio al 7 gennaio, la prima ora di ogni giorno si raggruppa nello stesso elemento dimensionale. Questo rapporto è utile se desideri un rapporto suddiviso per ora del giorno relativa, ma non vuoi ore statiche come elementi dimensionali. È particolarmente utile come dimensione nei rapporti pianificati, in quanto questa dimensione viene aggregata all’intervallo di date selezionato.

Questa dimensione si basa sul fuso orario della suite di rapporti e non su quello locale del visitatore. Ad esempio, se la suite di rapporti è in tempo di montagna e un visitatore in California visita il tuo sito alle 00:00 ora del Pacifico, i gruppi di hit sotto `11:00 AM` elemento dimensione. Se desideri una dimensione che registri l’ora del visitatore locale, l’Adobe consiglia di utilizzare [getTimeParting](/help/implement/vars/plugins/gettimeparting.md) plug-in.

## Popola questa dimensione con i dati

Questa dimensione funziona in modo predefinito per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi dimensionali

Gli elementi del Dimension includono `12:00 AM` - `11:00 PM`, che rappresenta l’ora del giorno in cui si è verificato l’hit (arrotondata per difetto). Ad esempio, se un hit è stato generato alle 15:58, viene raggruppato sotto l’elemento dimensione di `3:00 PM`.

## Ora legale

L&#39;ora legale è una pratica in cui gli orologi sono impostati un&#39;ora avanti in primavera e un&#39;ora indietro in autunno. Se il fuso orario di una suite di rapporti utilizza l’ora legale, Adobe regola i dati di conseguenza per tale ora.

* **Quando inizia l&#39;ora legale**: a marzo, i rapporti in genere mostrano un’ora di ritardo nei dati da cui inizia l’ora legale. L’ora non esiste, quindi non fa parte della raccolta dati. Tieni presente che una piccola quantità di dati può comunque arrivare a quest’ora. I server di raccolta dati di Adobe impiegano diversi secondi (fino a un minuto) per prendere in considerazione le regolazioni dell’ora legale.
* **Quando termina l&#39;ora legale**: a novembre, i rapporti mostrano in genere un’ora in doppio stack in cui termina l’ora legale. L’ora si è verificata due volte, quindi entrambe le ore sono aggregate nei rapporti.
