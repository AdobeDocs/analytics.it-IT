---
title: Lingua
description: L’impostazione della lingua preferita nel browser.
feature: Dimensions
exl-id: 590406a4-d336-42c7-8048-e7cd8e611d43
TQID: https://experienceleague.adobe.com/KC8nBiwUbQaE8Wi5OVKdjwP-sTijGYYMBK74M-TnOFs
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
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 8%
---
# Lingua

La [dimensione](overview.md) &quot;Lingua&quot; mostra le lingue principali in cui i visitatori preferiscono visualizzare il contenuto. Questa dimensione è utile quando desideri comprendere le lingue preferite dei visitatori più frequenti per facilitare le attività di localizzazione.

>[!NOTE]
>
>Questa dimensione non raccoglie la lingua del sito. Se desideri raccogliere la lingua del sito in una dimensione, Adobe consiglia di utilizzare una variabile personalizzata, ad esempio un [eVar](evar.md).

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento a una tabella di ricerca interna ad Adobe. Il valore di ricerca si basa sull&#39;intestazione HTTP `Accept-Language` nelle richieste di immagini. Funziona come previsto in qualsiasi implementazione AppMeasurement o Web SDK (tag), senza alcuna variabile da impostare.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (intestazione HTTP) |
| **Campo Web SDK / XDM** | Nessuno (intestazione HTTP) |
| **Parametro query** | Nessuno (utilizza l&#39;intestazione `Accept-Language`) |
| **Tag XML** | [`<language>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite di byte** | N/D |
| **Persistenza** | N/D |

## Elementi dimensionali

Gli elementi di Dimension includono nomi descrittivi delle lingue preferite dei visitatori. Gli esempi includono `"English (United States)"`, `"English (United Kingom)"`, `"Chinese (China)"` e `"Spanish (Spain)"`. Se una richiesta di immagine non contiene una lingua valida nell&#39;intestazione HTTP, l&#39;elemento dimensione è `"None"`.
