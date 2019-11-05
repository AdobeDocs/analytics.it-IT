---
description: Restituisce il valore di un parametro di stringa di query specificato, se trovato nell’URL della pagina corrente o nella stringa fornita.
keywords: Implementazione di Analytics
seo-description: Restituisce il valore di un parametro di stringa di query specificato, se trovato nell’URL della pagina corrente o nella stringa fornita.
seo-title: Util.getQueryParam
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Util.getQueryParam
topic: Sviluppatore e implementazione
uuid: 1fecd148-3e52-46f2-a73f-003563f7a62c
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# Util.getQueryParam

Restituisce il valore di un parametro di stringa di query specificato, se trovato nell’URL della pagina corrente o nella stringa fornita.

Perché dati importanti (come codici di tracciamento campagna, parole chiave di ricerca interne, ecc.) è disponibile nella stringa di query su una pagina, getQueryParam consente di acquisire i dati nelle variabili di Analytics.

Questa utility sostituisce il plug-in [getQueryParam](/help/implement/js-implementation/plugins/getqueryparam.md) .

**Sintassi:**

```
s.Util.getQueryParam(key, [url], [delim])
```

> [!NOTE] La sintassi dell'utility è diversa da quella del plug-in.

**Parametri:**

| Parametro | Descrizione |
|---|---|
| key | (obbligatorio) Il nome del parametro della stringa di query che si desidera ottenere. Questo parametro fa distinzione tra maiuscole e minuscole. |
| url | (facoltativo) L’URL predefinito è `s.pageURL` o `window.location`. Se si specifica un valore per questo parametro, l'URL da cui il parametro di query viene recuperato viene sostituito da quello specificato. |
| delizia | (facoltativo) Delimitatore di parametri nell’URL. Il delimitatore predefinito è "&amp;". Questo consente di specificare un delimitatore di stringa di query alternativo, ad esempio ";". |

**Restituisce:**

La funzione restituisce una stringa vuota "" se non viene fornita alcuna chiave, se non esiste alcuna opzione URL, o se la chiave non è trovata nell'URL. Se nell’URL viene trovato un delimitatore di frammento #, non vengono presi in considerazione tutti gli elementi che seguono il delimitatore di frammento. Se la chiave esiste e viene assegnata a un valore, il valore è URL decodificato e restituito.

**Esempio:**

```js
s.doPlugins = function(s) { 
  s.campaign = s.Util.getQueryParam("cid"); 
};
```

