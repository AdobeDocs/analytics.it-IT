---
title: Ora
description: L’ora in cui si è verificata la metrica.
feature: Dimensions
exl-id: 323c46dd-87d0-487a-b954-e5ccbc1b919d
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 2%

---

# Ora

La dimensione &quot;Ora&quot; indica l’ora in cui si è verificata una determinata metrica (arrotondata per difetto). Il primo elemento dimensione è la prima ora nell’intervallo di date e l’ultimo elemento dimensione è l’ultima ora nell’intervallo di date. Questa dimensione è utile per i rapporti con tendenze, in quanto consente di visualizzare le metriche nel tempo.

## Popolare questa dimensione con i dati

Questa dimensione funziona come standard per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi Dimension

Gli elementi Dimension includono una data ora nell’intervallo di date di un rapporto accanto alla relativa data. È formattato come `HH:HH YYYY-MM-DD`.

## Ora legale

Il Daylight Savings Time è una pratica in cui gli orologi sono fissati un&#39;ora in avanti in primavera, e rimbalzano un&#39;ora in autunno. Se il fuso orario di una suite di rapporti utilizza DST, Adobe regola i dati di conseguenza per quell’ora.

* **Quando inizia l&#39;ora legale**: A marzo, i rapporti mostrano in genere un intervallo di ore nei dati in cui inizia l’ora legale. L&#39;ora non esiste, quindi non fa parte della raccolta dati. Tieni presente che una piccola quantità di dati può ancora essere inclusa in quest’ora. I server di raccolta dati di Adobe impiegano diversi secondi (fino a un minuto) per tenere conto delle regolazioni DST.
* **Al termine del tempo di risparmio giornaliero**: A novembre, i rapporti mostrano in genere un’ora con doppio stack in cui termina l’ora legale. L&#39;ora è successa due volte, quindi entrambe le ore sono aggregate nei rapporti.
