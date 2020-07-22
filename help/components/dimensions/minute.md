---
title: Minuto
description: Il minuto in cui si è verificata la metrica.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 0%

---


# Minuto

La dimensione &quot;Minuto&quot; indica il minuto in cui si è verificata una determinata metrica (arrotondato per difetto). Il primo elemento dimensione è il primo minuto nell&#39;intervallo di date e l&#39;ultimo elemento dimensione è l&#39;ultimo minuto nell&#39;intervallo di date. Questa dimensione è importante per i report con tendenze, in quanto consente di visualizzare le metriche nel tempo. Data la granularità di questa dimensione, Adobe consiglia di limitare l’intervallo di date del rapporto a uno o due giorni.

## Compilare questa dimensione con i dati

Questa dimensione funziona automaticamente per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi dimensione

Gli elementi dimensione includono un minuto specificato all&#39;interno dell&#39;intervallo di date di un rapporto accanto alla data. È formattato come `HH:MM YYYY-MM-DD`. Gli elementi dimensione che iniziano con `00:00` uguale a mezzanotte in quel giorno, mentre i valori iniziano con `23:59` uguale a 11:59 PM per quel giorno.
