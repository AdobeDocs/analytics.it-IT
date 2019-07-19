---
description: Seguendo queste linee guida si utilizzano gli stessi domini cookie, che consentono di tenere traccia delle visite tra vari tipi di implementazioni.
keywords: Implementazione di Analytics
seo-description: Seguendo queste linee guida si utilizzano gli stessi domini cookie, che consentono di tenere traccia delle visite tra vari tipi di implementazioni.
seo-title: Linee guida sull'implementazione
solution: Analytics
title: Linee guida sull'implementazione
topic: Sviluppatore e implementazione
uuid: 2917 f 4 af -19 bd -4666-ae 4 b -056 e 7 e 33 f 642
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# Linee guida sull'implementazione

Seguendo queste linee guida si utilizzano gli stessi domini cookie, che consentono di tenere traccia delle visite tra vari tipi di implementazioni.

* **RSID:** Il [!UICONTROL report suite ID]
* **VNS:** Spazio del nome visitatore, sottodominio di [!DNL 2o7.net] o [!DNL omtrdc.net] utilizzato per archiviare il [!UICONTROL visitor ID] cookie
* **COOKIEDOMAIN:** Your VNS + trackingserver. A seconda del centro dati e della configurazione RDC, queste possono variare notevolmente. [Contatta l'Assistenza](https://helpx.adobe.com/contact/enterprise-support.ec.html#analytics) clienti se non sei sicuro del dominio di raccolta dati.

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

If using a first-party cookie implementation, `VNS.COOKIEDOMAIN.net` can be replaced with the first-party cookie domain used. For example, first-party cookies on `adobe.com` would be replaced with something similar to `metrics.adobe.com`.
