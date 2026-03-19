---
title: ID AMO EF
description: L’ID EF di Adobe Media Optimizer, utilizzato nelle integrazioni Adobe Advertising.
feature: Dimensions
source-git-commit: 408d8db0d1e3c8301a066fe54d611ec7b8e3418a
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 4%

---

# ID AMO EF

**[!UICONTROL AMO EF ID]** è un identificatore di ad click utilizzato nelle integrazioni Adobe Advertising. È un token univoco che Adobe Advertising utilizza per associare l’attività a un clic online o a un’esposizione pubblicitaria a livello di visitatore. La dimensione viene creata automaticamente quando si abilita l&#39;integrazione di [Analytics for Advertising](https://experienceleague.adobe.com/en/docs/advertising/integrations/analytics/overview).

## Popolare questa dimensione con i dati

Questa dimensione raccoglie i valori in diversi modi:

* Per il traffico di click-through, i dati vengono raccolti dal parametro della stringa di query `ef_id` nell&#39;[URL pagina](page-url.md), in genere nella pagina attraverso la quale il traffico guidato da annunci entra nel sito.
* Il traffico click-through può essere acquisito anche quando l’URL non contiene codici di tracciamento, ma Adobe Advertising JavaScript rileva un clic nei due minuti precedenti.
* Per il traffico view-through supportato, Adobe Advertising integra i valori sul backend utilizzando un ID supplementare (`SDID`).

>[!NOTE]
>
>Gli ID EF fanno distinzione tra maiuscole e minuscole. Se l’implementazione impone il tracciamento URL in minuscolo, Adobe Advertising non riconosce l’ID EF.

## Elementi dimensionali

Gli elementi Dimension includono gli identificatori di clic degli annunci generati dalle reti pubblicitarie supportate. Il formato della stringa dipende dalla rete e dal canale che l’ha generata.

### Annunci di ricerca di Google Ads

```text
{gclid}:G:{s}
```

* **`gclid`**: ID clic Google (GCLID).
* **`s`**: tipo di rete (`"s"` per la ricerca).

### Microsoft Advertising Search Ads

```text
{msclkid}:G:{s}
```

* **`msclkid`**: ID clic Microsoft (MSCLKID).
* **`s`**: tipo di rete (`"s"` per la ricerca).

### Visualizzare annunci e annunci di ricerca su altri motori di ricerca

```text
{amovid}:{ts}:{channel}
```

* **`amovid`**: l&#39;ID visitatore di Adobe Advertising, noto anche come ID surfista.
* **`ts`**: la marca temporale generata da Adobe Advertising.
* **`channel`**: tipo di canale responsabile del clic o dell&#39;esposizione:
   * **`d`**: clic su un annuncio di visualizzazione DSP (click-through di visualizzazione).
   * **`i`**: impression in un annuncio di visualizzazione DSP (view-through di visualizzazione).
   * **`s`**: clic su un annuncio di ricerca (click-through di ricerca).

### Esempi

```text
CjwKCAiAkbbMBhB2EiwANbxtbb9L573Dys0rjTDqcMo3x7tv2yEfh1RGb8exG9N892NoMqAzMBEGmhoCWxwQAvD_BwE:G:s
06207ca63ae6f4fa832197585547393c:20260301111101:i
WcmibgAAAHJK1RyY:1551968087687:d
```
