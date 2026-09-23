---
title: Java abilitato
description: Determina se Java è abilitato nel browser.
feature: Dimensions
exl-id: 2d4b4ea2-65ba-4d39-a040-f989b5eddc6e
TQID: https://experienceleague.adobe.com/EjiqmqpByH-q9AL-934s5HXAv78JTXpEJZ1Bwk-y5MI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
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
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 6%
---
# Java abilitato

La [dimensione](overview.md) &quot;Java abilitato&quot; determina se nel browser è abilitato Java. È utile nei casi in cui desideri introdurre funzionalità basate su Java sul sito e vuoi sapere quanti visitatori hanno già Java abilitato. Per coloro che hanno Java disabilitato, puoi fornire un’alternativa o istruzioni su come abilitarlo.

## Popolare questa dimensione con i dati

Java abilitato viene raccolto automaticamente, lato client: AppMeasurement rileva se Java è abilitato nel browser e segnala &quot;Y&quot; o &quot;N&quot;. Funziona come previsto in qualsiasi implementazione AppMeasurement o Web SDK (tag), senza alcuna variabile da impostare. Se raccogli dati all’esterno di AppMeasurement o del Web SDK (ad esempio tramite l’API), invia &quot;Y&quot; o &quot;N&quot; per utilizzare questa dimensione.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (raccolta automatica) |
| **Campo Web SDK / XDM** | Nessuno (raccolta automatica) |
| **Parametro query** | [`v`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Tag XML** | [`<javaEnabled>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite di byte** | 1 byte |
| **Persistenza** | N/D |

## Elementi dimensionali

Gli elementi Dimension includono &quot;Enabled&quot; (Abilitato), &quot;Disabled&quot; (Disabilitato) e &quot;Unknown&quot; (Sconosciuto).

* **Abilitato**: Java è abilitato nel browser. La stringa di query `v` contiene il valore &quot;Y&quot;.
* **Disabilitato**: Java è disabilitato nel browser o non supporta Java. La stringa di query `v` contiene il valore &quot;N&quot;.
* **Sconosciuto**: AppMeasurement non è riuscito a determinare il supporto Java. La stringa di query `v` non è presente nella richiesta di immagine.
