---
description: Determina se iniziare una nuova visita.
keywords: Analytics Implementation
solution: Analytics
title: getVisitStart
topic: Developer and implementation
uuid: 7dd3e51f-2f73-4452-a9fb-cac513cd28eb
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# getVisitStart

Determina se iniziare una nuova visita.

**Variabili di configurazione**

Nessuno

**Parametri**

c = (stringa) nome del cookie per il tracciamento.

**Restituisce**

(integer) 1 nella prima pagina della visita, altrimenti 0.

**Chiamate di esempio**

```
s.eVar50 = s.getVisitStart("s_visit");
```

