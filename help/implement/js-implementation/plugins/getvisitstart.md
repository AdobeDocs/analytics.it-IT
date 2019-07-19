---
description: Determina se avviare una nuova visita.
keywords: Implementazione di Analytics
seo-description: Determina se avviare una nuova visita.
seo-title: Getvisitstart
solution: Analytics
title: Getvisitstart
topic: Sviluppatore e implementazione
uuid: 7 dd 3 e 51 f -2 f 73-4452-a 9 fb-cac 513 cd 28 eb
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Getvisitstart

Determina se avviare una nuova visita.

**Variabili di configurazione**

Nessuno

**Parametri**

c = (stringa) nome del cookie per il tracciamento.

**Restituisce**

(integer) 1 nella prima pagina di visita, altrimenti 0.

**Chiamate di esempio**

```
s.eVar50 = s.getVisitStart("s_visit");
```

