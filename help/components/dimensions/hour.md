---
title: Ora
description: L’ora in cui si è verificata la metrica.
feature: Dimensions
exl-id: 323c46dd-87d0-487a-b954-e5ccbc1b919d
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 13%

---

# Ora

&#39;Ora&#39; [dimensione](overview.md) segnala l’ora in cui si è verificata una particolare metrica (arrotondata per difetto). Il primo elemento dimensione è la prima ora nell’intervallo di date e l’ultimo elemento dimensione è l’ultima ora nell’intervallo di date. Questa dimensione è utile per i rapporti con tendenze, in quanto consente di visualizzare le metriche nel tempo.

## Popola questa dimensione con i dati

Questa dimensione funziona in modo predefinito per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi dimensionali

Gli elementi di Dimension includono una determinata ora nell’intervallo di date di un rapporto insieme alla relativa data. È formattato come `HH:HH YYYY-MM-DD`.

## Ora legale

L&#39;ora legale è una pratica in cui gli orologi sono impostati un&#39;ora avanti in primavera e un&#39;ora indietro in autunno. Se il fuso orario di una suite di rapporti utilizza l’ora legale, Adobe regola i dati di conseguenza per tale ora.

* **Quando inizia l&#39;ora legale**: a marzo, i rapporti in genere mostrano un’ora di ritardo nei dati da cui inizia l’ora legale. L’ora non esiste, quindi non fa parte della raccolta dati. Tieni presente che una piccola quantità di dati può comunque arrivare a quest’ora. I server di raccolta dati di Adobe impiegano diversi secondi (fino a un minuto) per prendere in considerazione le regolazioni dell’ora legale.
* **Quando termina l&#39;ora legale**: a novembre, i rapporti mostrano in genere un’ora in doppio stack in cui termina l’ora legale. L’ora si è verificata due volte, quindi entrambe le ore sono aggregate nei rapporti.
