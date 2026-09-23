---
title: Ranking di tutte le pagine di ricerca
description: Determina quale pagina di un motore di ricerca un visitatore ha fatto clic sul tuo sito.
feature: Dimensions
exl-id: 58ce54c3-cc45-4e84-a14d-5fec0b70f50f
TQID: https://experienceleague.adobe.com/U7WgtQDXInyD1gXeBntncC9Fao1Rdc9W4AHFgx07T4A
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 12%
---
# Ranking di tutte le pagine di ricerca

La [dimensione](overview.md) di &quot;Classificazione di tutte le pagine di ricerca&quot; fornisce ad insight la pagina dei risultati della ricerca su cui un visitatore ha fatto clic nel sito. Ad esempio, se il sito viene visualizzato nella seconda pagina dei risultati di ricerca di un motore di ricerca, l’elemento dimensionale per questa variabile è &quot;Pagina di ricerca 2&quot;.

## Popolare questa dimensione con i dati

Adobe deriva questa dimensione dal motore di ricerca [referrer](referrer.md) di ogni hit, determinando quale pagina di risultati di ricerca il visitatore ha fatto clic in. Nessuna variabile da impostare. Per far funzionare questa dimensione è necessario che la suite di rapporti disponga di [Filtri per URL interni](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) configurati correttamente.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (derivato dal referrer del motore di ricerca) |
| **Campo Web SDK / XDM** | Nessuno (derivato dal referrer del motore di ricerca) |
| **Parametro query** | N/D |
| **Tag XML** | N/D |
| **Limite di byte** | N/D |
| **Persistenza** | N/D |

## Elementi dimensionali

Se un visitatore fa clic sul tuo sito da un motore di ricerca, il valore di questa dimensione è &quot;Pagina di ricerca&quot; seguito dal numero di pagina in cui ha fatto clic. Se un hit non proviene da un motore di ricerca, il valore di questa dimensione è &quot;Non specificato&quot;.
