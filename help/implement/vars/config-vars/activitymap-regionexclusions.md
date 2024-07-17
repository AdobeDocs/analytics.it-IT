---
title: ActivityMap.regionExclusions
description: Filtra i dati Activity Map per area geografica.
role: Admin, Developer
feature: Variables
source-git-commit: 05010d58ba2a3376473097e9d4543ee4415e83e1
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 12%

---

# ActivityMap.regionExclusions

La variabile `ActivityMap.regionExclusions` consente di filtrare o escludere in modo selettivo i dati Activity Map in base agli elementi dimensione raccolti nella dimensione [Area geografica Activity Map](/help/components/dimensions/activity-map-region.md).

## Esclusioni di area nell’estensione Web SDK

Quando **[!UICONTROL Enable click data collection]** è abilitato, utilizzare il blocco del codice di callback **[!UICONTROL Filter click properties]**. All&#39;interno di questo blocco di codice, è possibile controllare il valore di `content.linkRegion` e modificare il valore o abbandonare la raccolta di dati di tracciamento dei collegamenti.

## Esclusioni di area nella libreria JavaScript dell’SDK Web

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

La variabile `s.ActivityMap.regionExclusions` è una stringa contenente frasi delimitate da virgole da escludere dal tracciamento Activity Map. Se una delle frasi corrisponde al valore raccolto nella dimensione [Area Activity Map](/help/components/dimensions/activity-map-region.md), tutti i dati Activity Map vengono rimossi dall&#39;hit.

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
