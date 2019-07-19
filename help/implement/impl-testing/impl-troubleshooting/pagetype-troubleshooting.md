---
description: La variabile pagetype viene utilizzata solo per designare una pagina di errore 404 (Pagina non trovata).
keywords: Implementazione di Analytics
seo-description: La variabile pagetype viene utilizzata solo per designare una pagina di errore 404 (Pagina non trovata).
seo-title: Impostazione errata della variabile pagetype
solution: Analytics
subtopic: 'Risoluzione dei problemi   '
title: Impostazione errata della variabile pagetype
topic: Sviluppatore e implementazione
uuid: eafaf 58 e-ba 07-416 f -89 b 9-694687 cc 4802
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Impostazione errata della variabile pagetype

La variabile pagetype viene utilizzata solo per designare una pagina di errore 404 (Pagina non trovata).

Dispone di un solo valore possibile, errorpage.

```js
pageType="errorPage"
```

On a 404 error page, the *`pageName`* variable should not be populated. The *`pageType`* variable should be set only on a designated 404 error page. Any page containing content should never have a value in the *`pageType`* variable. Per le pagine contenenti contenuto, potete impostare la variabile come mostrato di seguito:

```js
pageType=""
```

È consigliabile eliminare completamente la variabile dalle pagine contenenti contenuto. Si consiglia di evitare confusione riguardo allo scopo della variabile.
