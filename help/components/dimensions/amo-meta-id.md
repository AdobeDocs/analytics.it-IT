---
title: AMO Meta Ads Click ID
description: ID clic di Adobe Media Optimizer Meta Ads, utilizzato nelle integrazioni Adobe Advertising.
feature: Dimensions
exl-id: c1def73a-51b9-46bf-9dc7-0fbd46fd6e17
TQID: 'https://experienceleague.adobe.com/3J-pLiOz4QwUewRSmEFsJCg0v-PbEmksUzGKOI0hHoA'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 171
ht-degree: 4%

---

# AMO Meta Ads Click ID

**[!UICONTROL AMO Meta Ads Click ID]** è un identificatore di ad click utilizzato nelle integrazioni Adobe Advertising. La dimensione viene creata automaticamente quando si abilita l&#39;integrazione di [Analytics for Advertising](https://experienceleague.adobe.com/it/docs/advertising/integrations/analytics/overview). È utile principalmente come identificatore di tracciamento non elaborato, anziché come dimensione di reporting leggibile dagli utenti.

## Popolare questa dimensione con i dati

Questa dimensione raccoglie i valori in diversi modi:

* Per il traffico di click-through, i dati vengono raccolti dal parametro della stringa di query `fbclid` nell&#39;[URL pagina](page-url.md), in genere nella pagina attraverso la quale il traffico guidato da annunci entra nel sito.
* Il traffico click-through può essere acquisito anche quando l’URL non contiene codici di tracciamento, ma Adobe Advertising JavaScript rileva un clic nei due minuti precedenti.

## Elementi dimensionali

Gli elementi di Dimension includono gli identificatori di clic degli annunci generati dalle reti pubblicitarie Meta (Facebook). La lunghezza di questi valori con hash può variare, ma in genere è di centinaia di caratteri. I valori di esempio (troncati) includono:

```text
IwY2xjawP0bVtleHRuA2FlbQIxMAB[...]AVp_aem_l5TPw-muraFjBGOq8l1w0g
PAb21jcAQB1LNleHRuA2FlbQIxMQB[...]PoFocE1FH44g_aem_FNMJG5EydJ_59aBwKIf4uA
```
