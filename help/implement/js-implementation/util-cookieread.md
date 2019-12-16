---
description: Ottiene il valore di un cookie.
keywords: Analytics Implementation
subtopic: JavaScript AppMeasurement
title: Util.cookieRead
topic: Developer and implementation
uuid: 825a75c6-b804-4bfe-b23a-907113b8bfa6
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Util.cookieRead

Ottiene il valore di un cookie.

**Sintassi:**

```
s.Util.cookieRead(key)
```

**Parametri:**

| Parametro | Descrizione |
|---|---|
| key | (obbligatorio) chiave per scrivere valore per nei cookie. |

**Restituisce:**

Valore del cookie o una stringa vuota se il cookie non viene trovato.

**Esempio:**

```js
var myCookie = s.Util.cookieRead("my_cookie");
```

