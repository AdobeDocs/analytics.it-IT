---
title: Ora
description: L’ora in cui si è verificata la metrica.
feature: Dimensions
exl-id: 323c46dd-87d0-487a-b954-e5ccbc1b919d
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 12%

---

# Ora

La [dimensione](overview.md) &quot;Ora&quot; indica l&#39;ora in cui si è verificata una data metrica (arrotondata per difetto). Il primo elemento dimensione è la prima ora nell’intervallo di date e l’ultimo elemento dimensione è l’ultima ora nell’intervallo di date. Questa dimensione è utile per i rapporti con tendenze, in quanto consente di visualizzare le metriche nel tempo.

## Popolare questa dimensione con i dati

Questa dimensione funziona in modo predefinito per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi dimensionali

Gli elementi di Dimension includono una determinata ora nell’intervallo di date di un rapporto insieme alla relativa data. È formattato come `HH:HH YYYY-MM-DD`.

## Ora legale

L&#39;ora legale è una pratica in cui gli orologi sono impostati un&#39;ora avanti in primavera e un&#39;ora indietro in autunno. Se il fuso orario di una suite di rapporti utilizza l’ora legale, Adobe regola i dati di conseguenza per tale ora.

* **Quando inizia l&#39;ora legale**: in marzo, nei rapporti viene in genere visualizzato un intervallo di un&#39;ora nei dati in cui inizia l&#39;ora legale. L’ora non esiste, quindi non fa parte della raccolta dati. Tieni presente che una piccola quantità di dati può comunque arrivare a quest’ora. I server di raccolta dati di Adobe impiegano diversi secondi (fino a un minuto) per prendere in considerazione le regolazioni dell’ora legale.
* **Al termine dell&#39;ora legale**: in novembre, nei report viene in genere visualizzata un&#39;ora a doppia sovrapposizione in cui termina l&#39;ora legale. L’ora si è verificata due volte, quindi entrambe le ore sono aggregate nei rapporti.
