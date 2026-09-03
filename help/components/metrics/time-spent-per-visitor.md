---
title: Tempo trascorso per visitatore (secondi)
description: La metrica "Tempo trascorso per visitatore (secondi)" mostra il tempo medio in cui i visitatori interagiscono con un dato elemento dimensionale durante l’intera vita di un visitatore.
feature: Metrics
exl-id: 80f38bab-2ee1-4d0d-ba53-9b2c7c85e481
TQID: https://experienceleague.adobe.com/NFmA2Q80h2WOTRwoJ882aFMG60y2HKngR0Ew0qnxb8o
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 177
ht-degree: 2%

---

# Tempo trascorso per visitatore (secondi)

La [!UICONTROL Time spent per visitor (seconds)] [metrica](overview.md) mostra il tempo medio per cui i visitatori interagiscono con un dato elemento della dimensione durante l&#39;intera vita di un visitatore.

Questa metrica non è disponibile in Data Warehouse a causa della diversa architettura di elaborazione.

## Come è calcolata questa metrica

Questa metrica utilizza la formula [`Total seconds spent`](total-seconds-spent.md) `divided by` [`Unique visitors`](unique-visitors.md).

## Percentuali superiori al 100%

Questa metrica contiene spesso percentuali superiori al 100%. Il denominatore è il tempo trascorso dall’intera dimensione per visitatore e il numeratore è il tempo trascorso dall’elemento dimensione per visitatore. Se il tempo trascorso dell’intera dimensione per visitatore è inferiore al tempo trascorso per visitatore di un dato elemento della dimensione, vedrai percentuali superiori al 100%. L’ordinamento dei rapporti classificati in base a questa metrica mostra il tempo di anomalia trascorso per i valori dei visitatori, che in genere non è prezioso. Adobe consiglia di ordinare i rapporti in base a un&#39;altra metrica, ad esempio [Visite](visits.md).

Consulta [Panoramica sul tempo trascorso](time-spent.md) per informazioni più generali sul tempo trascorso.
