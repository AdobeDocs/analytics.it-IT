---
title: Ora del giorno
description: L'ora numerica del giorno, indipendentemente dal giorno.
feature: Dimensions
exl-id: b9361534-7e58-41ed-9a38-c02aeed7a2d8
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 2%

---

# Ora del giorno

La dimensione &quot;Ora del giorno&quot; indica l’ora numerica di un dato giorno come elemento della dimensione. Ad esempio, se disponi di un rapporto che si estende dal 1° gennaio al 7 gennaio, la prima ora di ogni giorno viene raggruppata nello stesso elemento dimensionale. Questo rapporto è utile se desideri che un rapporto venga suddiviso per ora relativa del giorno, ma non desideri che le ore statiche siano come elementi dimensionali. È particolarmente utile come dimensione nei rapporti pianificati, in quanto questa dimensione viene rigenerata con l’intervallo di date selezionato.

Questa dimensione si basa sul fuso orario della suite di rapporti e non sul fuso orario locale del visitatore. Ad esempio, se la suite di rapporti è in orario di montagna e un visitatore in California visita il tuo sito alle 10:00 ora del Pacifico, gli hit si raggruppano sotto la `11:00 AM` elemento dimensione. Se desideri una dimensione che registri l’ora del visitatore locale, Adobe consiglia di utilizzare [getTimeParting](/help/implement/vars/plugins/gettimeparting.md) plug-in.

## Popolare questa dimensione con i dati

Questa dimensione funziona come standard per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi Dimension

Gli elementi del Dimension includono `12:00 AM` - `11:00 PM`, che rappresenta l’ora del giorno in cui si è verificato l’hit (arrotondato per difetto). Ad esempio, se un hit è stato generato alle 15:58, viene raggruppato sotto l’elemento dimensionale di `3:00 PM`.

## Ora legale

Il Daylight Savings Time è una pratica in cui gli orologi sono fissati un&#39;ora in avanti in primavera, e rimbalzano un&#39;ora in autunno. Se il fuso orario di una suite di rapporti utilizza DST, Adobe regola i dati di conseguenza per quell’ora.

* **Quando inizia l&#39;ora legale**: A marzo, i rapporti mostrano in genere un intervallo di ore nei dati in cui inizia l’ora legale. L&#39;ora non esiste, quindi non fa parte della raccolta dati. Tieni presente che una piccola quantità di dati può ancora essere inclusa in quest’ora. I server di raccolta dati di Adobe impiegano diversi secondi (fino a un minuto) per tenere conto delle regolazioni DST.
* **Al termine del tempo di risparmio giornaliero**: A novembre, i rapporti mostrano in genere un’ora con doppio stack in cui termina l’ora legale. L&#39;ora è successa due volte, quindi entrambe le ore sono aggregate nei rapporti.
