---
title: Indirizzo IP
description: L’indirizzo IP da cui è stato inviato ogni hit, disponibile in Data Warehouse.
feature: Dimensions
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
source-wordcount: '151'
ht-degree: 11%
---
# Indirizzo IP

Nell&#39;elenco &#39;Indirizzo IP&#39; [dimensione](overview.md) è indicato l&#39;indirizzo IP da cui è stato inviato ogni hit.

>[!IMPORTANT]
>
>Questa dimensione è disponibile solo in Data Warehouse.

## Popolare questa dimensione con i dati

AppMeasurement raccoglie automaticamente l’indirizzo IP dall’intestazione HTTP di ogni richiesta di immagine. Corrisponde alla colonna `ip` nei feed dati. Per ulteriori informazioni, vedere [Riferimento colonna dati](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md).

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (dalla richiesta HTTP) |
| **Campo Web SDK / XDM** | Nessuno (dalla richiesta HTTP) |
| **Parametro query** | Nessuno (dalla richiesta HTTP) |
| **Tag XML** | [`<ipAddress>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite di byte** | N/D |
| **Persistenza** | N/D |

Se [!UICONTROL IP Obfuscation] è abilitato nelle [Impostazioni account generali](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md) della suite di rapporti, gli indirizzi IP vengono offuscati o rimossi ovunque in Analytics, incluso Data Warehouse.

## Elementi dimensionali

Gli elementi Dimension includono gli indirizzi IP da cui sono stati inviati gli hit.
