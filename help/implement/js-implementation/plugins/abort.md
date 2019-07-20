---
description: Il flag di interruzione può essere impostato all'interno di doplugins per evitare l'invio della chiamata di tracciamento corrente.
keywords: Implementazione di Analytics
seo-description: Il flag di interruzione può essere impostato all'interno di doplugins per evitare l'invio della chiamata di tracciamento corrente.
seo-title: flag s. abort
solution: Analytics
title: flag s. abort
topic: Sviluppatore e implementazione
uuid: 0 c 6 ec 8 c 7-d 136-4851-8 cb 6-6 cb 1 b 7 f 6 f 0 dc
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# flag s. abort

Il flag di interruzione può essere impostato all'interno di doplugins per evitare l'invio della chiamata di tracciamento corrente.

Il flag di interruzione viene reimpostato con ogni chiamata di tracciamento; pertanto, se occorre interrompere una chiamata di tracciamento successiva, il flag dovrà essere impostato nuovamente all'interno di doplugins.

```js
s.doPlugins = function(s) { 
     s.campaign = s.getQueryParam("cid"); 
     if ((!s.campaign) && (!s.events)) { 
          s.abort = true; 
     } 
};
```

Questo consente di centralizzare la logica utilizzata per identificare l'attività che non desideri tracciare, ad esempio alcuni collegamenti personalizzati o collegamenti esterni negli annunci visualizzati.
