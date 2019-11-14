---
description: Seguendo queste linee guida si ottiene l’uso degli stessi domini di cookie, che consente di monitorare le visite tra i vari tipi di implementazioni.
keywords: Analytics Implementation
solution: Analytics
title: Linee guida sull'implementazione
topic: Developer and implementation
uuid: 2917f4af-19bd-4666-ae4b-056e7e33f642
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Linee guida sull'implementazione

Seguendo queste linee guida si ottiene l’uso degli stessi domini di cookie, che consente di monitorare le visite tra i vari tipi di implementazioni.

* **** RSID: Il [!UICONTROL report suite ID]
* **** VNS: Spazio nome visitatore, sottodominio di [!DNL 2o7.net] o [!DNL omtrdc.net] utilizzato per memorizzare il [!UICONTROL visitor ID] cookie
* **** COOKIEDOMAIN: VNS + trackingServer. A seconda del centro dati e della configurazione RDC, questi possono variare notevolmente. [Contatta l’Assistenza](https://helpx.adobe.com/contact/enterprise-support.ec.html#analytics) clienti se non sei sicuro del dominio di raccolta dati.

## Javascript

```javascript
var s_account="RSID" 
s.visitorNamespace="VNS" 
s.trackingServer="VNS.COOKIEDOMAIN.net" 
```

## AppMeasurement

```javascript
var s_account="RSID" 
s.visitorNamespace="VNS" 
s.trackingServer="VNS.COOKIEDOMAIN.net" 
```

## Richiesta immagine hardcoded

```javascript
<img border="0" alt="" src="https://VNS.COOKIEDOMAIN.net/b/ss/RSID/5?ns=VNS" width="1" height="1" /> 

<!-- Note that the visitor namespace is defined twice in hardcoded image requests; once in the http subdomain, and another using the ns= query string parameter! -->
```

Se si utilizza un'implementazione di cookie di prime parti, `VNS.COOKIEDOMAIN.net` è possibile sostituire con il dominio di cookie di prime parti utilizzato. Ad esempio, i cookie first-party su `adobe.com` verrebbero sostituiti con qualcosa di simile a `metrics.adobe.com`.
