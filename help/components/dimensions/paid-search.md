---
title: Ricerca a pagamento
description: Distingue le metriche da ricerca a pagamento e naturale.
feature: Dimensions
exl-id: b12665a3-e92f-4fc1-acd3-ea17a316e5e5
TQID: https://experienceleague.adobe.com/s9jhjGeXaOCo-Wz-Jyof951NZdRWfz-9tjrVrjHvTS0
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
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 11%
---
# Ricerca a pagamento

La dimensione [Ricerca a pagamento](overview.md) consente di esaminare qualsiasi metrica e confrontarla tra ricerca a pagamento e ricerca naturale. Tutti gli altri risultati al di fuori dei motori di ricerca vengono omessi. Questa dimensione è utile per comprendere in che modo le attività di ricerca a pagamento si confrontano con la ricerca organica.

## Popolare questa dimensione con i dati

Adobe deriva questa dimensione dal rilevamento di ricerche a pagamento, che classifica il traffico dei motori di ricerca come traffico a pagamento o naturale. Nessuna variabile da impostare. L&#39;unico requisito consiste nell&#39;avere [il rilevamento di ricerche a pagamento](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md) configurato correttamente nelle impostazioni della suite di rapporti. Se il rilevamento di ricerche a pagamento è configurato correttamente e una suite di rapporti contiene dati, questa dimensione funziona sempre.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (derivato dal rilevamento di ricerche a pagamento) |
| **Campo Web SDK / XDM** | Nessuno (derivato dal rilevamento di ricerche a pagamento) |
| **Parametro query** | N/D |
| **Tag XML** | N/D |
| **Limite di byte** | N/D |
| **Persistenza** | N/D |

## Elementi dimensionali

Gli elementi Dimension includono due valori statici: `"Natural"` e `"Paid"`. Se una visita corrisponde ai criteri di un motore di ricerca e anche al rilevamento di ricerche a pagamento, appartiene all&#39;elemento dimensione `"Paid"`. Se una visita soddisfa i criteri di un motore di ricerca e *non* corrisponde al rilevamento di ricerche a pagamento, appartiene all&#39;elemento dimensione `"Natural"`.
