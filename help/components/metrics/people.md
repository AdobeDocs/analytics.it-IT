---
title: Persone
description: Il numero di singoli utenti univoci, in genere con più dispositivi.
exl-id: 0136b843-2a1e-44d5-b5a6-e0fb03b7b995
source-git-commit: 639897682c9a28df7dc642dd7c68ad992fde40a9
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 5%

---

# Persone

Ci sono due versioni della metrica &quot;Persone&quot;.

Per i membri di [Device Co-op](https://experienceleague.adobe.com/docs/device-co-op/using/data/people.html?lang=it) che non utilizzano [Analisi multidispositivo](../cda/overview.md), la metrica &quot;Persone&quot; è un conteggio statisticamente derivato del numero di persone rappresentate nel rapporto. È il numero di ID visitatore identificati da Device Co-op e il numero di dispositivi non identificati dalla cooperativa.

All&#39;interno di una suite di rapporti virtuali [Analisi multidispositivo](../cda/overview.md), la metrica &quot;Persone&quot; non è una derivazione statistica. Al contrario, si tratta della somma delle persone identificate nel rapporto, più il numero di dispositivi che non sono identificati come appartenenti a una persona.

Se un visitatore viene identificato durante la visita, può contare su 2 Persone (1 persona non identificata e 1 persona identificata). [](/help/components/cda/replay.md) Riproduce attenua questo doppio conteggio a seconda dell’intervallo di reporting, della frequenza di riproduzione e della frequenza di successo. Per ulteriori informazioni, consulta [Dispositivi univoci](unique-devices.md) .
