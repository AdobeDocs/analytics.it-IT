---
description: È possibile impostare il flag di interruzione all'interno di doPlugins per impedire l'invio della chiamata di tracciamento corrente.
keywords: Implementazione di Analytics
seo-description: È possibile impostare il flag di interruzione all'interno di doPlugins per impedire l'invio della chiamata di tracciamento corrente.
seo-title: Contrassegno s.abort
solution: Analytics
title: Contrassegno s.abort
topic: Sviluppatore e implementazione
uuid: 0c6ec8c7-d136-4851-8cb6-6cb1b7f6f0dc
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Contrassegno s.abort

È possibile impostare il flag di interruzione all'interno di doPlugins per impedire l'invio della chiamata di tracciamento corrente.

Il flag abort viene reimpostato con ogni chiamata di tracciamento, quindi se è necessario interrompere anche una chiamata di tracciamento successiva, il flag dovrà essere nuovamente impostato all’interno di doPlugins.

```js
s.doPlugins = function(s) { 
     s.campaign = s.getQueryParam("cid"); 
     if ((!s.campaign) && (!s.events)) { 
          s.abort = true; 
     } 
};
```

Questo consente di centralizzare la logica utilizzata per identificare l'attività che non si desidera tracciare, ad esempio alcuni collegamenti personalizzati o collegamenti esterni negli annunci visualizzati.
