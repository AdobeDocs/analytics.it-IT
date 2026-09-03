---
title: Indirizzo IP
description: L’indirizzo IP da cui è stato inviato ogni hit, disponibile in Data Warehouse.
feature: Dimensions
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 106
ht-degree: 10%

---

# Indirizzo IP

Nell&#39;elenco &#39;Indirizzo IP&#39; [dimensione](overview.md) è indicato l&#39;indirizzo IP da cui è stato inviato ogni hit.

>[!IMPORTANT]
>
>Questa dimensione è disponibile solo in Data Warehouse.

## Popolare questa dimensione con i dati

AppMeasurement raccoglie automaticamente l’indirizzo IP dall’intestazione HTTP di ogni richiesta di immagine. Corrisponde alla colonna `ip` nei feed dati. Per ulteriori informazioni, vedere [Riferimento colonna dati](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md).

Se [!UICONTROL IP Obfuscation] è abilitato nelle [Impostazioni account generali](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md) della suite di rapporti, gli indirizzi IP vengono offuscati o rimossi ovunque in Analytics, incluso Data Warehouse.

## Elementi dimensionali

Gli elementi Dimension includono gli indirizzi IP da cui sono stati inviati gli hit.
