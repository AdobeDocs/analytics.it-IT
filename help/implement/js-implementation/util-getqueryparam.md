---
description: Restituisce il valore di un parametro stringa query specificato, se trovato nell'URL della pagina corrente o nella stringa fornita.
keywords: Implementazione di Analytics
seo-description: Restituisce il valore di un parametro stringa query specificato, se trovato nell'URL della pagina corrente o nella stringa fornita.
seo-title: Util. getqueryparam
solution: Analytics
subtopic: Javascript appmeasurement
title: Util. getqueryparam
topic: Sviluppatore e implementazione
uuid: 1 fecd 148-3 e 52-46 f 2-a 73 f -003563 f 7 a 62 c
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Util. getqueryparam

Restituisce il valore di un parametro stringa query specificato, se trovato nell'URL della pagina corrente o nella stringa fornita.

Dato che dati importanti (ad esempio, codici di tracciamento campagna, parole chiave di ricerca interna, ecc.) è disponibile nella stringa query su una pagina, getqueryparam facilita l'acquisizione dei dati nelle variabili Analytics.

This utility replaces the [getQueryParam](../../implement/js-implementation/plugins/getqueryparam.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF) plug-in.

**Sintassi:**

```
s.Util.getQueryParam(key, [url], [delim])
```

>[!NOTE]
>
>La sintassi per l'utility è diversa da quella del plug-in.

**Parametri:**

| Parametro | Descrizione |
|---|---|
| key | (obbligatorio) Il nome del parametro stringa query che desiderate ottenere. Questo parametro fa distinzione tra maiuscole e minuscole. |
| url | (optional) Default url is `s.pageURL` or `window.location`. Specificando un valore per questo parametro, si sostituisce l'URL da cui viene recuperato il parametro query a quello specificato. |
| delim | (facoltativo) Delimitatore parametro nell'URL. Il delimitatore predefinito è " &amp;". Consente di specificare un delimitatore di stringa query alternativo, ad esempio "; ". |

**Restituisce:**

La funzione restituirà una stringa vuota "se non viene fornita alcuna chiave, o se nessuna delle opzioni URL esiste o se la chiave non è trovata nell'URL. Se nell'URL viene trovato un delimitatore di frammento, non viene considerato tutto ciò che segue il delimitatore del frammento. Se la chiave esiste ed è assegnata a un valore, il valore è decodificato e restituito.

**Esempio:**

```js
s.doPlugins = function(s) { 
  s.campaign = s.Util.getQueryParam("cid"); 
};
```

