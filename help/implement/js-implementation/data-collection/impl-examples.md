---
description: Utilizzando adobe.com come esempio, le implementazioni descritte qui fanno riferimento allo stesso cookie visid.
keywords: Implementazione di Analytics
seo-description: Utilizzando adobe.com come esempio, le implementazioni descritte qui fanno riferimento allo stesso cookie visid.
seo-title: Esempio di implementazione
solution: Analytics
title: Esempio di implementazione
topic: Sviluppatore e implementazione
uuid: 17 d 8 d 2 b 2-2303-495 a-b 0 f 9-d 8 d 3 c 05 f 3893
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Esempio di implementazione

Utilizzando adobe.com come esempio, le implementazioni descritte qui fanno riferimento allo stesso cookie visid.

**Javascript:**

```js
var s_account="omniturecom" 
s.visitorNamespace="omniture" 
s.trackingServer="omniture.112.2o7.net"
```

**Richiesta immagine hardcoded:**

```
<img border="0" alt="" src="https://omniture.112.2o7.net/b/ss/omniturecom/5?ns=omniture" width="1" height="1" /> 
```

**Appmeasurement:**

```js
s.account="omniturecom"; 
s.visitorNamespace="omniture"; 
s.trackingServer="omniture.112.2o7.net";
```

E se i cookie di prime parti sono utilizzati:

**Javascript:**

```js
var s_account="omniturecom" 
s.visitorNamespace"omniture" 
s.trackingServer="metrics.omniture.com"
```

**Richiesta immagine hardcoded:**

```
<img border="0" alt="" src="https://metrics.omniture.com/b/ss/omniturecom/5" width="1" height="1" />
```

**Appmeasurement:**

```js
s.account="omniturecom"; 
s.visitorNamespace="omniture"; 
s.trackingServer="metrics.omniture.com";
```

