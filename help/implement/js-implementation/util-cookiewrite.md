---
description: Scrive un valore in un cookie.
keywords: Implementazione di Analytics
seo-description: Scrive un valore in un cookie.
seo-title: Util. cookiewrite
solution: Analytics
subtopic: Javascript appmeasurement
title: Util. cookiewrite
topic: Sviluppatore e implementazione
uuid: 8 d 526 e 4 c -6 d 7 a -4119-9434-d 7 ce 4 fbb 7577
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Util. cookiewrite

Scrive un valore in un cookie.

**Sintassi:**

```
s.Util.cookieWrite(key, value [,expire])
```

**Parametri:**

| Parametro | Descrizione |
|---|---|
| key | (obbligatorio) per scrivere il valore per i cookie. |
| value | (facoltativo) per scrivere sui cookie. |
| scade | (facoltativo) Oggetto data contenente la data di scadenza del cookie. Il valore predefinito è utilizzare un cookie di sessione. |

**Restituisce:**

**Esempio:**

```js
//set a cookie with an expiration 6 months from now 
var date = new Date(); 
date.setMonth(date.getMonth() + 6); 
var success = s.Util.cookieWrite("my_cookie", "my_value", date);
```

