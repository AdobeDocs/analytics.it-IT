---
title: Collegamento di download
description: Nome del collegamento per il download.
feature: Dimensions
exl-id: 078014a2-1f09-4177-9575-b44c5da25816
TQID: https://experienceleague.adobe.com/vok8Znalf6GBA1N0Z9GE1d31QpaUmD-d0bOsHB2Wehc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
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
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 5%
---
# Collegamento di download

La [dimensione](overview.md) del collegamento di download riporta i nomi dei collegamenti di download implementati nel sito. Questa dimensione è utile quando desideri ulteriori informazioni sul comportamento dei visitatori in merito ai collegamenti di download, ad esempio:

* Quali file vengono scaricati più frequentemente dal sito.
* Indica se alcuni file vengono scaricati più spesso in determinati periodi di tempo.
* Se i visitatori scaricano diversi tipi di file quando vengono offerti.

## Popolare questa dimensione con i dati

Questa dimensione è compilata da [chiamate di tracciamento dei collegamenti (`tl()`)](/help/implement/vars/functions/tl-method.md). Nessuna variabile dedicata da impostare. Inviare invece una richiesta di immagine `tl()` con un argomento del tipo di collegamento di `"d"` e impostare l&#39;argomento del nome del collegamento sul valore desiderato. La stringa di query `pe` indirizza il nome del collegamento alla dimensione di collegamento corretta (`lnk_o` per [collegamenti personalizzati](custom-link.md), `lnk_d` per [collegamenti di download](download-link.md) e `lnk_e` per [collegamenti di uscita](exit-link.md)). Se non viene fornito il nome di un collegamento, viene utilizzato l’URL di collegamento come valore della dimensione e i valori derivati dall’URL non sono soggetti al limite di byte.

```js
s.tl(true,"d","Example download link");
```

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | [`tl()`](/help/implement/vars/functions/tl-method.md) |
| **Campo Web SDK / XDM** | Nessuno |
| **Parametro query** | [`pev2`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Tag XML** | [`<linkName>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite di byte** | 100 byte |
| **Persistenza** | Hit |

## Elementi dimensionali

Poiché questa variabile è basata su una stringa personalizzata nell’implementazione, l’organizzazione determina quali sono gli elementi dimensionali. Adobe consiglia di raggruppare i collegamenti in categorie significative in base alle esigenze di reporting. Se non viene fornito alcun nome di collegamento, gli elementi dimensione vengono visualizzati come URL non elaborati. Questi URL non elaborati sono più difficili da interpretare nei rapporti, quindi fornisci un nome di collegamento descrittivo laddove possibile.
