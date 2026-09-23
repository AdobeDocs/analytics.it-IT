---
title: Browser
description: Nome e versione del browser utilizzato.
feature: Dimensions
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
TQID: https://experienceleague.adobe.com/J6rDfVwmRZpRLrultdurQkRih2HcPygjcjwO0bkms5E
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
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
source-wordcount: '307'
ht-degree: 9%
---
# Browser

La [dimensione](overview.md) &#39;[!UICONTROL Browser]&#39; riporta il nome e la versione del browser che invia l&#39;hit. Questa dimensione è utile quando desideri misurare i browser più comuni utilizzati dai visitatori. Quando esegui il test di nuove versioni del sito, puoi eseguirli sui browser principali in questa dimensione per massimizzare le attività di controllo della qualità.

## Popolare questa dimensione con i dati

Adobe deriva questa dimensione dall&#39;intestazione HTTP `User-Agent`, confrontandola con una tabella di ricerca interna gestita da Adobe in collaborazione con [DeviceAtlas](https://deviceatlas.com/). Nessuna variabile da impostare.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (derivato dall’agente utente) |
| **Campo Web SDK / XDM** | Nessuno (derivato dall’agente utente) |
| **Parametro query** | N/D |
| **Tag XML** | N/D |
| **Limite di byte** | N/D |
| **Persistenza** | N/D |

* Per le implementazioni di AppMeasurement, questa dimensione funziona in modo predefinito.
* Per le implementazioni di Web SDK, abilita [!UICONTROL Device Lookup] quando [si configura uno stream di dati](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=it).

## Elementi dimensionali

Gli elementi Dimension includono i nomi e le versioni del browser utilizzati. Versioni diverse dello stesso browser sono elementi dimensionali separati.

Alcuni elementi di dimensione contengono `"(unknown version)"` invece del numero di versione. Questo elemento dimensione fa riferimento a una versione recente del browser che Adobe non ha ancora aggiunto alle proprie tabelle di ricerca. Poiché i browser si aggiornano frequentemente, `"(unknown version)"` per un determinato browser è comune e temporaneo. Adobe in genere aggiorna le tabelle di ricerca durante le versioni di manutenzione mensili.

Alcuni elementi di dimensione contengono `.999` come numero di versione secondario, ad esempio `"Chrome 148.999"`. Questo valore indica che Adobe non è riuscito a determinare in modo affidabile la versione secondaria del browser. Quando i browser Chrome o Edge inviano richieste senza [suggerimenti client](/help/technotes/client-hints.md), la versione secondaria nella stringa dell&#39;agente utente non è considerata attendibile. Invece di gonfiare gli elementi dimensionali con versioni secondarie potenzialmente imprecise, Adobe sostituisce tali versioni secondarie con `.999`. Analogamente, se un browser segnala un numero di versione insolitamente elevato (superiore a 99999), Adobe lo normalizza su `999.999`.
