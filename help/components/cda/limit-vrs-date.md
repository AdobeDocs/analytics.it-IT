---
title: Limitare una suite di rapporti virtuale a determinate date
description: Scopri come limitare un intervallo di date della suite di rapporti virtuali in modo che si concentri solo sui dati uniti.
exl-id: 421d101d-8c64-47f7-b5a2-da039889f663
feature: CDA
role: Admin
TQID: https://experienceleague.adobe.com/x7zHG4xkSr1yDLZ2dfosn5PaK4JVxiMWC6xksSTLypE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 288
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
