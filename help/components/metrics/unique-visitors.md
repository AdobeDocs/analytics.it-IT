---
title: Visitatori univoci
description: Il numero di ID visitatore univoci.
feature: Metrics
exl-id: 56e7bad4-4802-49ac-a0f1-ae77441fc016
source-git-commit: f26f406848ab26092738089aac64ed9b4fc08019
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 83%

---

# Visitatori univoci

La [metrica](overview.md) “Visitatori univoci” mostra il numero di ID visitatore per l’elemento dimensione. È una delle metriche più comuni utilizzate per determinare il traffico, in quanto offre una panoramica di alto livello della popolarità di un elemento dimensione. Ad esempio, un visitatore può visitare il tuo sito ogni giorno per un mese, ma continua a contare come un singolo visitatore univoco.

Se usi la funzione [Cross-Device Analytics](../cda/overview.md), questa metrica viene sostituita dalla metrica [Dispositivi univoci](unique-devices.md).

## Visitatori univoci orari, giornalieri, settimanali, mensili, trimestrali, annuali

Analysis Workspace tratta i visitatori univoci in base alla granularità del rapporto. Ad esempio, se utilizzi la dimensione [Giorno](../dimensions/day.md), vedrai visitatori univoci giornalieri per ogni elemento dimensione. Tuttavia, per il totale del rapporto, i visitatori univoci vengono deduplicati per l’intervallo di date della tabella a forma libera.

## Come è calcolata questa metrica

Questa metrica conta il numero di ID visitatore univoci per un dato elemento dimensione. Consulta [Panoramica sull&#39;identificazione dei visitatori](/help/implement/id/overview.md) per ulteriori informazioni su come Adobe Analytics identifica i visitatori univoci.
