---
description: La variabile pageType viene utilizzata solo per designare una pagina di errore 404 (Pagina non trovata).
keywords: Analytics Implementation
solution: Analytics
subtopic: Troubleshooting
title: Impostazione errata della variabile PageType
topic: Developer and implementation
uuid: eafaf58e-ba07-416f-89b9-694687cc4802
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Impostazione errata della variabile PageType

La variabile pageType viene utilizzata solo per designare una pagina di errore 404 (Pagina non trovata).

Ha un solo valore possibile, che è errorPage.

```js
pageType="errorPage"
```

In una pagina di errore 404, la *`pageName`* variabile non deve essere compilata. La *`pageType`* variabile deve essere impostata solo su una specifica pagina di errore 404. Qualsiasi pagina contenente contenuto non deve mai avere un valore nella *`pageType`* variabile. Per le pagine contenenti contenuto, potete impostare la variabile come illustrato di seguito:

```js
pageType=""
```

È consigliabile eliminare completamente la variabile dalle pagine contenenti contenuto. Questa procedura è consigliata per evitare confusione circa lo scopo della variabile.
