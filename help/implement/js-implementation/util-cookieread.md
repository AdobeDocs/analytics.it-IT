---
description: Ottiene il valore di un cookie.
keywords: Implementazione di Analytics
seo-description: Ottiene il valore di un cookie.
seo-title: Util. cookieread
solution: Analytics
subtopic: Javascript appmeasurement
title: Util. cookieread
topic: Sviluppatore e implementazione
uuid: 825 a 75 c 6-b 804-4 bfe-b 23 a -907113 b 8 bfa 6
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Util. cookieread

Ottiene il valore di un cookie.

**Sintassi:**

```
s.Util.cookieRead(key)
```

**Parametri:**

| Parametro | Descrizione |
|---|---|
| key | (obbligatorio) per scrivere il valore per i cookie. |

**Restituisce:**

Valore cookie o una stringa vuota se il cookie non è trovato.

**Esempio:**

```js
var myCookie = s.Util.cookieRead("my_cookie");
```

