---
title: Gerarchia
description: (Ritirato) Una dimensione personalizzata che puoi utilizzare nei rapporti.
feature: Dimensions
exl-id: f9bd3ae1-3578-44c5-a540-ea93feac5bef
TQID: https://experienceleague.adobe.com/7WnYvaE3qCfYGWcX6IuvMZiF0MJq50Izz6i2LNg4h6c
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 167
ht-degree: 86%

---

# Gerarchia

>[!IMPORTANT]
>
>Questa dimensione è stata ritirata e non è una [dimensione](overview.md) disponibile in Analysis Workspace. Al suo posto, Adobe consiglia di utilizzare le [eVar](evar.md) e le classificazioni.

Le gerarchie sono variabili personalizzate che puoi utilizzare come preferisci. Non persistono oltre l’hit impostato. Se il contratto con Adobe lo supporta, sono disponibili fino a 5 gerarchie.

## Popolare le gerarchie con i dati

Ogni gerarchia raccoglie dati dalla stringa di query [`h1` - `h5` &#x200B;](/help/implement/validate/query-parameters.md) nelle richieste di immagini. Ad esempio, il parametro della stringa di query `h1` raccoglie i dati per la gerarchia 1, mentre il parametro della stringa di query `h4` raccoglie i dati per la gerarchia 4.

AppMeasurement, che compila variabili JavaScript in una richiesta di immagine per la raccolta dati, utilizza le variabili `hier1` - `hier5`. Per le linee guida per l’implementazione, consulta [qui](/help/implement/vars/page-vars/hier.md) nella Guida utente di implementazione.

## Elementi dimensionali

Poiché le gerarchie contengono stringhe personalizzate nell’implementazione, l’organizzazione determina gli elementi dimensionali di ciascuna gerarchia. Assicurati di registrare lo scopo di ogni gerarchia e degli elementi dimensionali tipici in un [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md).
