---
title: linkURL
description: Sostituisci l’URL di collegamento generato automaticamente utilizzato da AppMeasurement nelle chiamate di tracciamento dei collegamenti.
feature: Appmeasurement Implementation
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
role: Admin, Developer
source-git-commit: 24101efe2b860734c9d176ba8be8f17e26429442
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 12%

---

# linkURL

Ogni volta che una chiamata di tracciamento dei collegamenti viene inviata ad Adobe, AppMeasurement rileva l’URL su cui hai fatto clic. Questo URL consente di determinare il tipo di collegamento, ad esempio i collegamenti di download e di uscita. Utilizzare la variabile `linkURL` per ignorare l&#39;URL rilevato.

In Analysis Workspace non sono presenti dimensioni che generano rapporti su questa variabile. Popola la colonna `page_event_var1` in [Feed dati](/help/export/analytics-data-feed/data-feed-overview.md). Se desideri tenere traccia dell&#39;URL di un collegamento su cui è stato fatto clic, Adobe consiglia di utilizzare una variabile personalizzata, ad esempio [Prop](../page-vars/prop.md). L&#39;utilizzo di [Activity Map](/help/analyze/activity-map/overview.md) può semplificare la raccolta dati per i collegamenti selezionati.

## Collega URL tramite Web SDK

L’URL del collegamento è mappato alle seguenti variabili:

* [Oggetto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `web.webInteraction.URL`
* [Oggetto dati](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.linkURL` o `data.__adobe.analytics.pev1`

## Collega l’URL tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.linkURL in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.linkURL` è una stringa contenente l&#39;URL completo del collegamento su cui è stato fatto clic. Questa variabile non popola le dimensioni disponibili nel reporting.

```js
s.linkURL = "https://example.com";
```

Se il terzo argomento del metodo [tl()](../functions/tl-method.md) non è impostato, verrà utilizzata la variabile `linkURL`.
