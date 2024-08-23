---
title: Limitare una suite di rapporti virtuale a determinate date
description: Scopri come limitare un intervallo di date della suite di rapporti virtuali in modo che si concentri solo sui dati uniti.
exl-id: 421d101d-8c64-47f7-b5a2-da039889f663
feature: CDA
role: Admin
source-git-commit: cfa5cc02ba3a7349b51a904f29bab533c0f1c603
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 5%

---

# Limitare una suite di rapporti virtuale a determinate date

{{available-existing-customers}}

Quando attiviamo l’unione, questa inizia in una data specifica. Supponiamo che la data sia il 1° giugno. La suite di rapporti virtuale di CDA conterrà i dati non uniti precedenti al 1° giugno. Puoi nascondere eventuali dati nella suite di rapporti virtuali precedenti al 1° giugno, in modo che l’analisi possa concentrarsi sugli intervalli di date successivi all’inizio dell’unione.

Puoi limitare i dati della suite di rapporti virtuale a determinate date effettuando le seguenti operazioni:

## Passaggio 1: creare una suite di rapporti virtuale con un intervallo di date giornaliero continuo

Quando configuri la suite di rapporti virtuale, in Componenti aggiungi un intervallo di date con un inizio fisso e un intervallo di date giornaliero continuo. L’inizio fisso deve essere il giorno in cui è iniziata l’unione.

![](assets/rolling-daily.png)

## Passaggio 2: creare un segmento &quot;exclude-exclude&quot;

Quindi, crea un segmento di hit che inserisce l’intervallo di date in un contenitore di esclusione all’interno di un altro contenitore di esclusione. È una &quot;esclusione esclusa&quot;.

Il motivo dell’&quot;esclusione&quot; è che gli intervalli di date hanno lo scopo di sostituire l’intervallo di date del rapporto. Pertanto, se includi semplicemente il 1° giugno in avanti, l’intervallo di date del rapporto sarà sempre il 1° giugno in avanti. Questo porterà a risultati indesiderati. Quando &quot;escludi escludi&quot;, questo comportamento sovrascrive e limita i dati da cui puoi trarre all’intervallo di date appropriato.

![](assets/exclude-exclude.png)

## Passaggio 3: applicare questo segmento alla suite di rapporti virtuali di Analytics tra dispositivi

![](assets/apply-segment.png)

## Passaggio 4: visualizzare i risultati nel reporting

Il reporting ora inizia nella data desiderata, lo stesso giorno in cui l’unione è stata implementata per la prima volta:

![](assets/report-limited-dates.png)
