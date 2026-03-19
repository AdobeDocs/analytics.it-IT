---
title: ID clic degli annunci Meta AMO
description: ID clic di Adobe Media Optimizer Meta Ads, utilizzato nelle integrazioni Adobe Advertising.
feature: Dimensions
source-git-commit: 408d8db0d1e3c8301a066fe54d611ec7b8e3418a
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 10%

---

# ID clic degli annunci Meta AMO

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
