---
title: ActivityMap.regionExclusions
description: Filtra i dati di Activity Map per area geografica.
role: Admin, Developer
feature: Appmeasurement Implementation
exl-id: 353282aa-860c-45dc-a6b0-8d9f1fa09f13
TQID: 'https://experienceleague.adobe.com/YWC5bRG0JSZBk-iJbBLAv2HjjbtOC2IYkUPXid-EsTM'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 191
ht-degree: 13%

---

# ActivityMap.regionExclusions

La variabile `ActivityMap.regionExclusions` consente di filtrare o escludere in modo selettivo i dati di Activity Map in base agli elementi dimensione raccolti nella dimensione [Area geografica Activity Map](/help/components/dimensions/activity-map-region.md).

## Esclusioni di area nell’estensione Web SDK

Quando **[!UICONTROL Enable click data collection]** è abilitato, utilizzare il blocco del codice di callback **[!UICONTROL Filter click properties]**. All&#39;interno di questo blocco di codice, è possibile controllare il valore di `content.linkRegion` e modificare il valore o abbandonare la raccolta di dati di tracciamento dei collegamenti.

## Esclusioni di area nella libreria JavaScript di Web SDK

Quando [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) è abilitato, utilizzare il callback `filterClickDetails` nell&#39;oggetto `clickCollection`. All&#39;interno di questo callback, è possibile controllare il valore di `linkRegion` e modificare il valore o abbandonare la raccolta di dati di tracciamento dei collegamenti.

```js
alloy("configure", {
  clickCollectionEnabled: true,
  clickCollection: {
    filterClickDetails: function(content) {
      // If the clicked region has personal links in it, don't send click data
      if(content.linkRegion.includes("personal")) {
        return false;
      }
    }
  }
});
```

## Esclusioni di area tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.ActivityMap.regionExclusions tramite AppMeasurement

La variabile `s.ActivityMap.regionExclusions` è una stringa contenente frasi delimitate da virgole da escludere dal tracciamento di Activity Map. Se una delle frasi corrisponde al valore raccolto nella dimensione [Area geografica Activity Map](/help/components/dimensions/activity-map-region.md), tutti i dati di Activity Map vengono rimossi dall&#39;hit.

```html
<script>
  var s = s_gi("examplersid");
  s.ActivityMap.regionExclusions = "contact";
</script>

<!-- Clicking any of these links tracks normally. -->
<!-- While "contact" is present, it is not tracked in region. The region is "nav" -->
<nav>
  <a href="index.html">Home</a>
  <a href="products.html">View our products</a>
  <a href="contact.html">Contact us</a>
</nav>

<!-- Activity Map data is not tracked for any of these links. -->
<!-- All these links belong to the region "Personal contact information" -->
<div id="personal-contact-information">
 <a href="mailto:user@example.com">Example user</a>
 <a href="mailto:user2@example.com">Example user 2</a>
 <a href="mailto:user3@example.com">Example user 3</a>
</div>
```
