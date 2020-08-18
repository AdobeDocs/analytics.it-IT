---
title: Ora del giorno
description: L'ora numerica del giorno, indipendentemente da quale giorno.
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 1%

---


# Ora del giorno

La dimensione &quot;Ora del giorno&quot; riporta l&#39;ora numerica di un dato giorno come elemento dimensione. Ad esempio, se disponi di un rapporto che si estende dal 1° gennaio al 7 gennaio, la prima ora di ogni giorno raggrupperà nello stesso elemento dimensione. Questo rapporto è utile se desiderate che un rapporto venga suddiviso per l&#39;ora relativa del giorno, ma non desiderate un&#39;ora statica come elementi dimensione. È particolarmente utile come dimensione nei report pianificati, in quanto questa dimensione viene riprodotta con l&#39;intervallo di date selezionato.

Questa dimensione è basata sul fuso orario della suite di rapporti e non sul fuso orario locale del visitatore. Ad esempio, se la suite di rapporti è in Mountain time e un visitatore in California visita il sito alle 10:00 AM Pacific time, i gruppi di hit sotto l’elemento `11:00 AM` dimensione. Se desiderate una dimensione che registri l&#39;ora del visitatore locale,  Adobe consiglia di utilizzare il plug-in [getTimeParting](/help/implement/vars/plugins/gettimeparting.md) .

## Compilare questa dimensione con i dati

Questa dimensione funziona automaticamente per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi Dimension

Gli elementi del Dimension includono `12:00 AM` - `11:00 PM`, che rappresenta l&#39;ora del giorno in cui si è verificato l&#39;hit (arrotondato per difetto). Ad esempio, se un hit è stato generato alle 3:58 PM, viene raggruppato sotto l’elemento dimensione di `3:00 PM`.

## Ora legale risparmio

Ora legale è una pratica in cui gli orologi sono impostati con un&#39;ora di anticipo in primavera e riportano indietro di un&#39;ora in autunno. Se il fuso orario di una suite di rapporti utilizza DST,  Adobe regola i dati di conseguenza per quell&#39;ora.

* **Quando inizia** l&#39;ora legale: A marzo, i report mostrano generalmente un intervallo di ore nei dati in cui inizia l&#39;ora legale. L&#39;ora non esiste, quindi non fa parte della raccolta dati. Notate che una piccola quantità di dati può ancora essere inserita in quest&#39;ora.  server di raccolta dei dati di Adobe impiegano alcuni secondi (fino a un minuto) per tenere conto delle regolazioni DST.
* **Al termine** dell&#39;ora legale: A novembre, i report solitamente mostrano un&#39;ora doppia impilata in cui termina l&#39;ora legale. L&#39;ora è successa due volte, quindi entrambe le ore sono aggregate nei rapporti.
