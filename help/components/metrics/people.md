---
title: Persone
description: Il numero di singoli utenti univoci, in genere con più dispositivi.
feature: Metrics
exl-id: 0136b843-2a1e-44d5-b5a6-e0fb03b7b995
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 5%

---

# Persone

Ci sono due versioni della metrica &quot;Persone&quot;.

Per i membri del [Device Co-op](https://experienceleague.adobe.com/docs/device-co-op/using/data/people.html?lang=it) che non utilizzano [Analisi multidispositivo](../cda/overview.md), la metrica &quot;Persone&quot; è un conteggio statisticamente derivato del numero di persone rappresentate nel rapporto. È il numero di ID visitatore identificati da Device Co-op e il numero di dispositivi non identificati dalla cooperativa.

All&#39;interno di un [Analisi multidispositivo](../cda/overview.md) suite di rapporti virtuale, la metrica &quot;Persone&quot; non è una derivazione statistica. Si tratta, invece, della somma delle persone identificate nel rapporto e del numero di dispositivi che non sono identificati come appartenenti a una persona.

Se un visitatore viene identificato durante la visita, può contare su 2 Persone (1 persona non identificata e 1 persona identificata). [Riproduci](/help/components/cda/replay.md) attenua questo doppio conteggio a seconda dell’intervallo di reporting, della frequenza di riproduzione e del tasso di successo. Vedi [Dispositivi univoci](unique-devices.md) per ulteriori informazioni.
