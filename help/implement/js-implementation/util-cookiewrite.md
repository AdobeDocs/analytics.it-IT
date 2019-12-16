---
description: Scrive un valore in un cookie.
keywords: Analytics Implementation
subtopic: JavaScript AppMeasurement
title: Util.cookieWrite
topic: Developer and implementation
uuid: 8d526e4c-6d7a-4119-9434-d7ce4fbb7577
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Util.cookieWrite

Scrive un valore in un cookie.

**Sintassi:**

```
s.Util.cookieWrite(key, value [,expire])
```

**Parametri:**

| Parametro | Descrizione |
|---|---|
| key | (obbligatorio) chiave per scrivere valore per nei cookie. |
| value | (facoltativo) valore da scrivere sui cookie. |
| expires | (facoltativo) oggetto Date contenente la data di scadenza del cookie. Per impostazione predefinita viene utilizzato un cookie di sessione. |

**Restituisce:**

**Esempio:**

```js
//set a cookie with an expiration 6 months from now 
var date = new Date(); 
date.setMonth(date.getMonth() + 6); 
var success = s.Util.cookieWrite("my_cookie", "my_value", date);
```

