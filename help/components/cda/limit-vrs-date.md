---
title: Limita una VRS a determinate date
description: Comprendere come limitare un intervallo di date VRS per concentrarsi solo sui dati uniti.
translation-type: tm+mt
source-git-commit: 954927359420cfdb3d0e908758fc36464e15fee5
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 0%

---


# Limita una VRS a determinate date

Quando si attiva la cucitura, la cucitura inizia in una data specifica. Supponiamo che la data sia il 1° giugno. La VRS CDA conterrà dati non cuciti prima del 1° giugno. È possibile nascondere eventuali dati nella VRS prima del 1° giugno in modo che l&#39;analisi possa concentrarsi sugli intervalli di date dopo l&#39;inizio della cucitura.

Puoi limitare i dati VRS a determinate date effettuando le seguenti operazioni:

## Passaggio 1: Crea VRS con un intervallo di date giornaliero continuo

Quando si configura la VRS, in Componenti, aggiungere un intervallo di date con un inizio fisso, con un intervallo di date giornaliero continuo. L&#39;inizio fisso dovrebbe essere il giorno in cui è iniziato il cuciture.

![](assets/rolling-daily.png)

## Passaggio 2: Creare un segmento &quot;exclude-exclude&quot;

Quindi, crea un segmento hit che inserisce l’intervallo di date in un contenitore di esclusione all’interno di un altro contenitore di esclusione. È un’opzione di esclusione.

Il motivo per cui &quot;escludi&quot; è che gli intervalli di date hanno lo scopo di escludere l&#39;intervallo di date del rapporto. Quindi se includi solo il 1° giugno in avanti, farà sempre avanzare l&#39;intervallo di date del rapporto 1° giugno. Ciò porterà a risultati indesiderati. Quando si &quot;esclude&quot;, questo comportamento ha la priorità e limita i dati che è possibile ricavare dall&#39;intervallo di date appropriato.

![](assets/exclude-exclude.png)

## Passaggio 3: Applica questo segmento alla tua VRS CDA

![](assets/apply-segment.png)

## Passaggio 4: Vedere i risultati nel reporting

Il reporting inizia ora nella data desiderata, lo stesso giorno in cui è stato implementato l&#39;unione:

![](assets/report-limited-dates.png)