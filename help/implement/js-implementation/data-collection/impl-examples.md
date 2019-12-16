---
description: Utilizzando adobe.com come esempio, le implementazioni descritte qui fanno riferimento allo stesso cookie visid.
keywords: Analytics Implementation
title: Esempio di implementazione
topic: Developer and implementation
uuid: 17d8d2b2-2303-495a-b0f9-d8d3c05f3893
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

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

E se vengono utilizzati i cookie di prime parti:

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

