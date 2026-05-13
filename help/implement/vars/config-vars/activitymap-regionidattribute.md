---
title: ActivityMap.regionIDAttribute
description: Modifica l’attributo cercato da Activity Map per determinare la regione.
feature: Appmeasurement Implementation
role: Admin, Developer
exl-id: 4aec045e-1a86-412f-bd37-777ac49ccc7d
TQID: https://experienceleague.adobe.com/4J2esEPxvV-weoNQM9X-ScFa6fIUERWVLCUme9GZygM
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 230
ht-degree: 10%

---

# ActivityMap.regionIDAttribute

La variabile `ActivityMap.regionIDAttribute` consente di modificare l&#39;attributo cercato da Activity Map durante la determinazione della dimensione [Area geografica Activity Map](/help/components/dimensions/activity-map-region.md). Se il sito è strutturato in modo da rendere l&#39;attributo `id` meno utile per l&#39;area geografica di Activity Map, è possibile impostare questa variabile per esaminare un attributo diverso.

## Attributo ID area nell’estensione Web SDK

Quando **[!UICONTROL Enable click data collection]** è abilitato, utilizzare il blocco del codice di callback **[!UICONTROL Filter click properties]**. All&#39;interno di questo blocco di codice, è possibile controllare il valore di `content.clickedElement` e modificare il valore o abbandonare la raccolta di dati di tracciamento dei collegamenti.

## Attributo ID area nella libreria JavaScript di Web SDK

Quando [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) è abilitato, utilizzare il callback `filterClickDetails` nell&#39;oggetto `clickCollection`. All&#39;interno di questo callback, è possibile controllare il valore di `clickedElement` e personalizzare la logica dell&#39;area raccolta.

```js
alloy("configure", {
  clickCollectionEnabled: true,
  clickCollection: {
    filterClickDetails: function(content) {
      // If the clicked element was in a table, set the region to the contents of the data-custom attribute
      // If the clicked element was not in a table, or if the data-custom attribute doesn't exist, leave region as-is
      content.region = content.clickedElement.closest('table')?.getAttribute('data-custom') || content.region;
    }
  }
});
```

## Attributo ID area geografica tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.ActivityMap.regionIDAttribute utilizzando AppMeasurement

La variabile `s.ActivityMap.regionIDAttribute` è una stringa che rappresenta l&#39;attributo per determinare la dimensione [Area geografica Activity Map](/help/components/dimensions/activity-map-region.md). Questa variabile è impostata su `id` per impostazione predefinita. Se si modifica questa variabile, Activity Map non cercherà più l&#39;attributo `id`, ma cercherà comunque altri criteri per determinare l&#39;area geografica (ad esempio gli elementi semantici).

```html
<script>
  var s = s_gi("examplersid");
  s.ActivityMap.regionIDAttribute = "data-custom";
</script>

<!-- Clicking any of these links populates the region dimension with 'left-nav' -->
<div id="676967617A656C6C65" data-custom="left-nav">
  <a href="index.html">Home</a>
  <a href="products.html">View our products</a>
  <a href="contact.html">Contact us</a>
</div>
```
