---
title: Ora
description: L'ora in cui si è verificata la metrica.
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 0%

---


# Ora

La dimensione &quot;Ora&quot; indica l&#39;ora in cui si è verificata una metrica specifica (arrotondata per difetto). Il primo elemento dimensione è la prima ora nell’intervallo di date e l’ultimo elemento dimensione è l’ultima ora nell’intervallo di date. Questa dimensione è importante per i report con tendenze, in quanto consente di visualizzare le metriche nel tempo.

## Compilare questa dimensione con i dati

Questa dimensione funziona automaticamente per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi Dimension

Gli elementi di Dimension includono un&#39;ora specifica all&#39;interno dell&#39;intervallo di date di un rapporto accanto alla data. È formattato come `HH:HH YYYY-MM-DD`.

## Ora legale risparmio

Ora legale è una pratica in cui gli orologi sono impostati con un&#39;ora di anticipo in primavera e riportano indietro di un&#39;ora in autunno. Se il fuso orario di una suite di rapporti utilizza DST,  Adobe regola i dati di conseguenza per quell&#39;ora.

* **Quando inizia** l&#39;ora legale: A marzo, i report mostrano generalmente un intervallo di ore nei dati in cui inizia l&#39;ora legale. L&#39;ora non esiste, quindi non fa parte della raccolta dati. Notate che una piccola quantità di dati può ancora essere inserita in quest&#39;ora.  server di raccolta dei dati di Adobe impiegano alcuni secondi (fino a un minuto) per tenere conto delle regolazioni DST.
* **Al termine** dell&#39;ora legale: A novembre, i report solitamente mostrano un&#39;ora doppia impilata in cui termina l&#39;ora legale. L&#39;ora è successa due volte, quindi entrambe le ore sono aggregate nei rapporti.
