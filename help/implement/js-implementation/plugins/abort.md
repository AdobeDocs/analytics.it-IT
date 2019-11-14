---
description: È possibile impostare il flag di interruzione all'interno di doPlugins per impedire l'invio della chiamata di tracciamento corrente.
keywords: Analytics Implementation
solution: Analytics
title: Contrassegno s.abort
topic: Developer and implementation
uuid: 0c6ec8c7-d136-4851-8cb6-6cb1b7f6f0dc
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

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
